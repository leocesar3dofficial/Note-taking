# FastAPI

## Features

### Automatic Docs (Swagger UI and ReDoc)

- [Swagger UI](http://127.0.0.1:8000/docs)
- [ReDoc](http://127.0.0.1:8000/redoc)
- [OpenAPI JSON](http://127.0.0.1:8000/openapi.json)

### Validation (Pydantic)

#### Number (placed in function properties within Path and Query classes)

##### Expressions

- `gt`: greater than
- `ge`: greater than or equal
- `lt`: less than
- `le`: less than or equal

##### Example

```python
async def read_items(
    *,
    item_id: int = Path(title="The ID of the item to get", ge=0, le=1000),
    q: str,
    size: float = Query(gt=0, lt=10.5)
):
```

#### Examples of the data using `schema_extra` (inside model class)

```python
class Config:
    schema_extra = {
        "example": {
            "name": "Foo",
            "description": "A very nice Item",
            "price": 35.4,
            "tax": 3.2,
        }
    }
```

### Security (Starlette)

### Authentication (OAuth2)

#### Needed Libraries

```bash
pip install "python-jose[cryptography]"
pip install "passlib[bcrypt]"
pip install emails  # to send emails from the app
```

#### Handle JWT Tokens

1. Generate in terminal: `openssl rand -hex 32`
2. Copy the output to the variable `SECRET_KEY`
3. Test in the auto docs with: Username: `johndoe` Password: `secret`

## Suggested Project File Structure

```python
.
├── app                  # "app" is a Python package
│   ├── __init__.py      # this file makes "app" a "Python package"
│   ├── main.py          # "main" module, e.g. import app.main
│   ├── dependencies.py  # "dependencies" module, e.g. import app.dependencies
│   └── routers          # "routers" is a "Python subpackage"
│       ├── __init__.py  # makes "routers" a "Python subpackage"
│       ├── items.py     # "items" submodule, e.g. import app.routers.items
│       └── users.py     # "users" submodule, e.g. import app.routers.users
└── internal             # "internal" is a "Python subpackage"
    ├── __init__.py      # makes "internal" a "Python subpackage"
    └── admin.py         # "admin" submodule, e.g. import app.internal.admin
```

## Static Files

```python
from fastapi.staticfiles import StaticFiles
app.mount("/static", StaticFiles(directory="static"), name="static")
```

## Guide

### 1. Install

#### FastAPI + Uvicorn

```bash
pip install "fastapi[all]"
```

#### Separate

```bash
pip install fastapi
pip install "uvicorn[standard]"
pip install sqlalchemy
```

### 2. Basic Setup (`main.py`)

```python
from fastapi import FastAPI

app = FastAPI()  # framework instance
```

### 3. Define Endpoints

#### Conventions

- Order matters
- No overwrite/redefine of a path operation

#### Syntax

```python
@app.get("/")  # path operation decorator
async def root():
    return {"message": "Hello World"}
```

#### Operations

- GET: `@app.get()`
- POST: `@app.post()`
- PUT: `@app.put()`
- PATCH: `@app.patch()` (partial update)
- DELETE: `@app.delete()`

#### Parameters

##### Path (typed)

```python
@app.get("/items/{item_id}")
async def read_item(item_id: int):
    return {"item_id": item_id}
```

##### Predefined Values

```python
from enum import Enum
from fastapi import FastAPI

class ModelName(str, Enum):  # predefined values
    alexnet = "alexnet"
    resnet = "resnet"
    lenet = "lenet"

app = FastAPI()

@app.get("/models/{model_name}")
async def get_model(model_name: ModelName):
    if model_name is ModelName.alexnet:
        return {"model_name": model_name, "message": "Deep Learning FTW!"}
    if model_name.value == "lenet":
        return {"model_name": model_name, "message": "LeCNN all the images"}
    return {"model_name": model_name, "message": "Have some residuals"}
```

##### Query

###### Conventions

- URL: [http://127.0.0.1:8000/items/?skip=2&limit=20](http://127.0.0.1:8000/items/?skip=2&limit=20)

```python
@app.get("/items/")
async def read_item(skip: int = 0, limit: int = 10):  # skip and limit are query parameters
    return fake_items_db[skip: skip + limit]
```

###### Optional

```python
# q is an optional parameter
async def read_item(item_id: str, q: str | None = Query(default=None, min_length=3, max_length=50, regex="^fixedquery$"):
    # default and optional
    async def read_items(q: str = Query(default="fixedquery", min_length=3)):
```

###### Required

```python
# just not declare any default value and the parameter will be required
# URL: http://127.0.0.1:8000/items/foo-item?needy=sooooneedy
@app.get("/items/{item_id}")
async def read_user_item(item_id: str, needy: str):
    # another example
    async def read_items(q: str = Query(min_length=3)):
    # required with ellipsis, q is explicitly required now
    async def read_items(q: str = Query(default=..., min_length=3)):
    # required with None
    async def read_items(q: str | None = Query(default=..., min_length=3)):
    # Pydantic's Required instead of Ellipsis
    from pydantic import Required
    async def read_items(q: str = Query(default=Required, min_length=3)):
```

##### Parameter List / Multiple Values

- URL: [http://localhost:8000/items/?q=foo&q=bar](http://localhost:8000/items/?q=foo&q=bar)

```python
from fastapi import FastAPI, Query

async def read_items(q: list[str] | None = Query(default=None)):
    # default list
    async def read_items(q: list = Query(default=["foo", "bar"])):
    # default empty list
    async def read_items(q: list = Query(default=[])):
```

##### Alias

- URL: [http://127.0.0.1:8000/items/?item-query=foobaritems](http://127.0.0.1:8000/items/?item-query=foobaritems)

```python
async def read_items(q: str | None = Query(default=None, alias="item-query")):
```

##### Exclude

```python
async def read_items(hidden_query: str | None = Query(default=None, include_in_schema=False)):
```

##### Metadata

```python
async def read_items(
    q: str | None = Query(
        default=None,
        title="Query string",
        description="Query string for the items in the database",
        deprecated=True,
        min_length=3,
    )
):
```

##### Type Conversion

```python
# short parameter will be converted to bool
async def read_item(item_id: str, q: str | None = None, short: bool = False):
```

##### Multiple Path and Query Parameters

```python
@app.get("/users/{user_id}/items/{item_id}")
async def read_user_item(
    user_id: int, item_id: str, q: str | None = None, short: bool = False
):
    item = {"item_id": item_id, "owner_id": user_id}
    if q:
        item.update({"q": q})
    if not short:
        item.update(
            {"description": "This is an amazing item that has a long description"}
        )
    return item
```

##### Cookies

Características

- Cookies são gravados no lado cliente.
- O cabeçalho/header HTTP de resposta “Set-Cookie” envia cookies do servidor para o cliente.
- A diretiva “Max-Age” define o número de segundos até o cookie expirar.
- Diretiva HttpOnly
  - Usado para prevenir de ataques cross-site scripting (XSS).
  - São inacessíveis para a API JavaScript Document.cookie.
  - São enviados só para o servidor.
  - Exemplo: cookies que persistem sessões de servidor.

Como usar:

```python
from fastapi import Cookie, FastAPI

async def read_items(ads_id: str | None = Cookie(default=None)):
```

##### Header

```python
from fastapi import FastAPI, Header

async def read_items(user_agent: str | None = Header(default=None)):
```

##### Return Type (Examples)

```python
@app.post("/items/", response_model=Item)
async def create_item(item: Item) -> Item:
@app.get("/items/", response_model=list[Item])
async def read_items() -> list[Item]:
```

### 4. Request Body (Model)

```python
# Import Pydantic's BaseModel
from pydantic import BaseModel

# Create the data model
class Item(BaseModel):
    name: str  # required
    description: str | None = None  # optional
    price: float
    tax: float | None = None

# Can have list, set, and custom model types as model data
# Can define arbitrarily deeply nested models

# Define endpoint with the model as a parameter
@app.post("/items/")
async def create_item(item: Item):
    return item

# Request body + path parameters
@app.put("/items/{item_id}")
async def create_item(item_id: int, item: Item):
    return {"item_id": item_id, **item.dict()}

# Request body + path + query parameters
@app.put("/items/{item_id}")
async def create_item(item_id: int, item: Item, q: str | None = None):
    result = {"item_id": item

_id, **item.dict()}
    if q:
        result.update({"q": q})
    return result

# Other data types: UUID, datetime, date, time, timedelta, frozenset, bytes, Decimal

# Singular values in body
from fastapi import Body, FastAPI

async def update_item(item_id: int, item: Item, user: User, importance: int = Body(gt=0)):
```

##### Field

```python
from pydantic import BaseModel, Field

class Item(BaseModel):
    name: str
    description: str | None = Field(
        default=None, title="The description of the item", max_length=300
    )
```

##### Form Data

```python
# Needed library to deal with HTML form/file data
# pip install python-multipart
from fastapi import FastAPI, Form

@app.post("/login/")
async def login(username: str = Form(), password: str = Form()):
```

##### File Upload

###### Single

```python
from fastapi import FastAPI, File, UploadFile

@app.post("/files/")
async def create_file(file: bytes | None = File(default=None)):
    return {"file_size": len(file)}

@app.post("/uploadfile/")
async def create_upload_file(file: UploadFile):
    return {"filename": file.filename}
```

###### Multiple

```python
async def create_files(files: list[bytes] = File()):
async def create_upload_files(files: list[UploadFile]):
```

### 5. Handling Errors

```python
from fastapi import FastAPI, HTTPException

# Inside function
raise HTTPException(status_code=404, detail="Item not found")
```

### 6. Database

#### Create the Database Models (SQLAlchemy)

#### Create the Pydantic Models

#### SQLite

##### Install

```bash
sudo apt install sqlite3
sqlite3 --version
sudo apt-get install sqlitebrowser
```

##### Create a Database

```bash
sqlite3 database.db
; + Enter  # create an empty database
Ctrl + d  # exit console
```

### 7. Start App

```bash
uvicorn main:app --reload
```

```bash
python3 -m uvicorn main:app --reload
```

- `main`: the file `main.py` (the Python "module")
- `app`: the object created inside `main.py` with the line `app = FastAPI()`
- `--reload`: make the server restart after code changes. Only use it for development

### 8. Stop Uvicorn (web server)

Press `Ctrl + c`
