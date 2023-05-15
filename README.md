# Tailwind Simple Template

This is a basic Tailwind starting template, there were some configurations when starting Tailwind that will be described below as a reminder.

## About Node version

In order to run TailwindCSS we have to install / update our node to v14 our higher.

## Install or update NodeJS version

We can run the following commands in order to install or update NodeJS and NPM packages

> $ sudo npm cache clean -f

> $ sudo npm install -g n

> $ sudo n stable

> $ sudo n latest

**TO FIX PATH**

> $ sudo apt-get install --reinstall nodejs-legacy

**TO UNDO**

> $ sudo n rm **version**

> $ sudo npm uninstall -g n

## Steps taken to install Tailwind CLI

First of all i created a package.json file, to do that run the following command:

> $ npm init -y

Then we run the following command to install Tailwind as a DEV dependence:

> $ npm i -D tailwindcss

After that we create **tailwind.config.js** file by running the following command:

> $ npx tailwind init

The official Tailwind DOCs says that inside **tailwind.config.js** in **content:** we should copy the following string *"./src/**/*.{html,js}"* however what we do in this template is:

    module.exports = {
        content: [
            './build/*.html'
        ],
        theme: {
            screens: {
                sm: '640px',
                md: '768px',
                lg: '1024px',
                xl: '1444px',
            },
            extend: {
                colors: {
                    primaryColor: 'hsl()',
                    secondaryColor: 'hsl()',
                    tertiaryColor: 'hsl()',
                    lightGray: 'hsl(0, 0%, 77%)',
                    mediumGray: 'hsl(0, 0%, 50%)',
                    darkGray: 'hsl(0, 0%, 23%)',
                },
                fontFamily: {
                    title: ['', ''],
                    body: ['', ''],
                }
            },
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

**OBS**: There is a possibility of a warning sign is showed because of the **@** to fix that just go to **configuration** on VSCode than in the search area type in **unknown**, there will
be a area with the following description **CSS > Lint: Unknown At Rules**, choose **ignore**, that will fix it.

Now we create NPM scripts so that we can run our TailwindCSS. Inside the *package.json* file are going to replace line 7 for these 2(two) command scripts:

> "build": "tailwindcss -i ./src/input.css -o ./build/assets/css/style.css",
>
>"watch": "tailwindcss -i ./src/input.css -o .build/assets/css/style.css --watch"

The first one will build our CSS directory and the *style.css* file, the second we run to keep Tailwind under watch to compile structures changes.

To run those we use **npm run**:

> $ npm run build
>
> $ npm run watch