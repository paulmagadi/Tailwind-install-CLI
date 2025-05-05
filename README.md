# Installing Tailwind CSS  | Tailwind CLI

## 1. Create your project folder

bash

`mkdir myapp`

`cd myapp`

shell

`New-Item myapp -ItemType Directory`
`cd myapp`

## 2. Initialize npm
bash

`npm init -y`

This creates a package.json file.

## 3. Install Tailwind CSS and required tools
bash

`npm install tailwindcss @tailwindcss/cli`

## 4. Create Project Structure
In your myapp folder, create these:

pgsql
```
myapp/
├── index.html
├── src/
│   └── input.css
├── dist/
│   └── output.css
```

## 5. Add Tailwind Directives to src/input.css
Open src/input.css and add:

css
```
@import "tailwindcss";
```

## 6. Add Build Script in package.json
Open your package.json and update the "scripts" section like this:

json

```
"scripts": {
    "dev": "tailwindcss -i ./src/input.css -o ./dist/output.css --watch",
    "build": "tailwindcss -i ./src/input.css -o ./dist/output.css --minify"
}
```

# 7. Create a simple index.html

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My Tailwind App</title>
  <link rel="stylesheet" href="dist/output.css" />
</head>
<body class="bg-gray-100 text-center p-10">
  <h1 class="text-3xl font-bold text-blue-600">Hello Tailwind v4!</h1>
</body>
</html>
```

## 8. Run Tailwind CSS Compiler

bash

`npm run dev  # Development (watch mode)`

or

`npm run build # Production (minified)`


# Deployment
Install the gh-pages package:

bash

`npm install --save-dev gh-pages`


##  Update Build Script in package.json
```
"scripts": {
  ...
  "deploy": "npm run build && gh-pages -d ."
}
```

## Deploy the project:
bash

`npm run deploy`

Push the codes to github, the website will be deployed to github pages using  *branch* **gh-pages**