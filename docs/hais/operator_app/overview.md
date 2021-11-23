**Repo** : https://bitbucket.org/drona-footloose/drona.operator_webapp/ <br/>
**Branch**: operator-friendly-v1b


``` mermaid
graph LR
  SO>Store-Operator-Human] --->|dispense otc| OA(Operator App);
  SO--->|pick item| OA;
```

###Structure of the app : 

>####Root dir:
```
doc/

src/
                         |  -------//common-project-devops-files//-------
.babelrc                 |  
.gitignore               |
gulpfile.js              |  //this is used to build, concat & minify everything (html, css, es6 js & regular js)
package.json             |  
README.md                |  
rollup.config.js         |  //this is used from gulp to build all the es6 scripts 
run.js                   |  //this is used by `npm run dev` for cleaning ports & running dev-server

```
<br/>

>####'src/' dir:
*- `src/` is the root development directory. it contains the entire scope of development* <br/>
*- the root URL / in the app corresponds to this dir* <br/>

```
src/
  assets/                | this folder contains all the static files viz - 
  
  components/            | this folder contains all the <web Component>.js files
  
  scripts/               | this folder contains any regular js other than dom_components that needs to included in the app
  
  styles/                | this folder contains all the global css
  
  index.src.html         | this file contains the head & body markup that is used to build the app
  
  
  //if any root-level worker scripts - they are placed here
```
<br/>

>####'components/' dir:
*- `components/` dir is where all the web components are written.* <br/>
```
components/           
  common/              | this folder contains all the common web components used at multiple places in the app (viz. clock, countdown, notification)
  
  drona/               | this folder contains all the drona-store related web components
    agent/             | drona-store web components responsible for function other than connection
      ioa/
      roa/
      ooa/
    connection/        | drona-store web components responsible for connection

  userAssistant/       | this folder contains all the userAssistance related web components (viz voice-interface, any in-app guides (not added in this case))
  
  index.js             | this file contains/references everything that is to be built
```