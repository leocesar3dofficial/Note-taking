# generator-api

- Tool to quickly scaffold out an API project.
- Save time and effort in setting up the project structure and boilerplate code.

1. **Install Yeoman and the `generator-api` package**:

   Before using the `generator-api`, you need to have Yeoman installed globally on your system. You can install Yeoman using npm:

   ```
   npm install -g yo
   ```

   Then, install the `generator-api` package:

   ```
   npm install -g generator-api
   ```

2. **Run the generator**:

   Navigate to the directory where you want to generate your API project (e.g., an empty directory for your new project) and run the generator:

   ```
   yo api
   ```

   This command will start the Yeoman generator and prompt you to answer a series of questions to configure your API project.

3. **Provide project details**:

   You'll be asked to provide details about your project, such as project name, description, database type, authentication method, etc. Make sure to choose appropriate options based on your requirements. For example:

   - Project name: My API
   - Description: An API for managing owners and dogs
   - Database type: MongoDB (assuming you're using MongoDB for your project)
   - Authentication: None (or choose a desired authentication method)

4. **Define models**:

   After configuring the project details, the generator will prompt you to define models for your API. You'll need to specify the name of each model (e.g., `owner`, `dog`) and its attributes (e.g., name, age, breed). Provide the necessary information for both the `owner` and `dog` models.

5. **Generate the API**:

   Once you've defined the models, the generator will generate the API code based on your inputs. It will create the necessary files and folder structure for your project, including routes, controllers, models, and other configurations.

6. **Review and customize**:

   Review the generated code to ensure that it meets your requirements. You can customize the generated code further if needed, such as adding validation logic, additional routes, or middleware.

7. **Run and test the API**:

   After customizing the generated code, you can run your API project and test it to ensure that it functions correctly. You can use tools like Postman or Insomnia to send requests to your API endpoints and verify the responses.
   