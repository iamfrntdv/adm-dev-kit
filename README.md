<img title="Dev Kit" src="http://adm-designhouse.com/adm-dev-kit-logo.svg">  
# ADM DEV KIT
ADM-DEV-KIT is static web server and build tool built with plugins and tools like Node.js, JSPM, Express.js, Browser-Sync, Gulp.js, PostHTML, PostCSS and others. Main goal of ADM-DEV-KIT is to give ability to develop in component driven way. It is also focused on web standards and optimisation.

## FEATURES
- Component driven development with independent components;
- No need to use HTML or CSS inside JS for components;
- HTML, JS, CSS is compiled separately;
- Development and build environment;
- Project Init Tool [ADM DEV KIT INIT PROJECT](https://github.com/iamfrntdv/adm-dev-kit-init-project) - initialise project with ease;
- PostHtml;
- PostCSS - use future css today;
- JSPM - install third party libraries, bundle JS;
- Browser-Sync - automatically reload browser on file changes;
- EsLint - check your JS code;
- StyleLint - check you CSS code;
- Pre-commit;
- Default CSS;
- MY-IP-UI - helps to open project on other devices;
- and much more…

## DOCUMENTATION
- [Introduction](https://github.com/iamfrntdv/adm-dev-kit/blob/2.5.0/_docs/introduction.md)
- Server and Build
- Project Source
- Examples (coming soon)

## QUICK START

### Manual Project Setup
In project’s folder run command:
```
npm i —save adm-dev-kit
```

#### Example of Project Structure
```
adm-dev-kit-project-example/
	|- src/
		|- index/
		|- index.pug
	|- views
	|- gulpfiles.js
	|- server.js
```

#### Create server file:
```js
//server.js
const app = require('adm-dev-kit');

app.server({
    src: './src',       // working directory
    views: './views'    // express views folder
});
```

#### Create build file: 
```js
//gulpfile.js
const app = require('adm-dev-kit');

app.build({
    src: './src',       // working directory
    dest: './dest'      // build directory
});
```

#### Project’s Source Files
In project’s root folder create ```src/``` folder for project’s source files and ```view/``` folder for view.

Create ```index.pug``` inside ```src/``` folder it will represent main page of the project.

#### Adding JavaScript
JSPM is used as main JS bundler. To add any JS file use JSPM’s ```System.import```:
```
p.hello-world Hello, World!
script System.import('hello-world.js')
```
Important to know path to any js file should be relative to ```src/``` folder:
```
src/
    |- index
        |- hello-world
            |- hello-world.pug
            |- hello-world.js
    |- index.pug
    
index.pug:
...
include index/hello-world/hello-world.pug
...

hello-world.pug:
script System.import('index/hello-world/hello-world/hello-world.js')
```

#### Adding CSS
PostCSS is used as main pre and post processor for CSS.
To add CSS just use ```link``` tag:
```
link(href="hello-world.css" type="text/css" rel="stylesheet")
p.hello-world Hello, World!
```
Important to know path in ```href``` should be relative to ```src/``` folder:
```
src/
    |- index
        |- hello-world
            |- hello-world.pug
            |- hello-world.css
    |- index.pug
    
index.pug:
...
include index/hello-world/hello-world.pug
...

hello-world.pug:
link(href="index/hello-world/hello-world/hello-world.css" type="text/css" rel="stylesheet")
```

#### Running Server
To run server use:
```
npm start
```
After server has started jspm file will be generated automatically to ```src/``` folder. Don’t delete this file, it is required for the build.

#### Build
To build project just run:
```
gulp
```
Gulp will build everything automatically, no worry! 


### Setting up project using ADM DEV KIT INIT PROJECT
Initialise your project in few simple steps using [ADM DEV KIT INIT PROJECT](https://github.com/iamfrntdv/adm-dev-kit-init-project). You can create project automatically or proceed through question form to get
##### Automatically:
![ADM DEV KIT INIT AUTOMATICALLY](https://raw.githubusercontent.com/iamfrntdv/adm-dev-kit-init-project/master/images/adm-dev-kit-auto-project-init.gif)
##### Manual:
![ADM DEV KIT INIT MANUALLY](https://raw.githubusercontent.com/iamfrntdv/adm-dev-kit-init-project/master/images/adm-dev-kit-manual-project-init.gif)
