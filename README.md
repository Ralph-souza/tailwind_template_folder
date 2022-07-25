# Tailwind Simple Template

This is a basic Tailwind starting template, there were some configurations when starting Tailwind that will be described below as a reminder.

## About Node version

In order to run TailwindCSS we have to install / update our node to v14 our higher.

## Steps taken to install Tailwind CLI

First of all i created a package.json file, to do that run the following command:

> $ npm init -y

Then we run the following command to install Tailwind as a DEV dependence:

> $ npm i -D tailwindcss

After that we create **tailwind.config.js** file by running the following command:

> $ npx tailwind init

The official Tailwind DOCs says that inside **tailwind.config.js** in **content:** we should copy the following string *"./src/**/*.{html,js}"* however what we do in this template is:

    module.exports = {
        content: ['./*.html'],
        theme: {
            extend: {},
        },
        plugins: [],
    }

That way we are setting every .html file into the root directory (./).

After that we create a input.css file with the following:

>@tailwind base;
>
>@tailwind components;
>
>@tailwind utilities;

Now we create NPM scripts so that we can run our TailwindCSS. Inside the *package.json* file are going to replace line 7 for these 2(two) command scripts:

> "build": "tailwindcss -i ./input.css -o ./css/style.css",
>
>"watch": "tailwindcss -i ./input.css -o ./css/style.css --watch"

The first one will build our CSS directory and the *style.css* file, the second we run to keep Tailwind under watch to compile structures changes.

To run those we use **npm run**:

> $ npm run build
>
> $ npm run watch