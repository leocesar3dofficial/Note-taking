# Jupyter Notebook

## Install library
```bash
!pip install <library_name> --upgrade --quiet
```

## Introspection
- Place a `?` after the object/function for general information.
- Use `Shift + Tab` in a cell/function to show its parameters.

## Markdown
- Header: Use the character `#` one to four times.
- List:
  - Ordered: `1.`
  - Unordered: `*`
- Link: [link text](link url)
- Image: `![](image url)`
- Code block: 
  ```
  code text lines
  ```

## Calculate the time to process the cell
Use: `%%time`

## Show output not as a popup
Use: `%<library_name> inline`

## Remove info header from output
Just place a semicolon at the end of the line: `series.plot();`
