# Tableau API JS

A version of the [JS API for Tableau](https://help.tableau.com/current/api/js_api/en-us/JavaScriptAPI/js_api.htm) wrapped as an NPM module.

## Node.js (Install)

Requirements:

- Node.js
- npm (Node.js package manager)

```bash
npm install tableau-api-js
```

## Usage

To use this package:

app.component.ts:

```javascript
  import { Component, OnInit } from '@angular/core';
  import * as Tableau from 'tableau-api-js';

  @Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.scss']
  })
  export class AppComponent implements OnInit {
    constructor() {}

    public initViz(): void {
      const containerDiv = document.getElementById('vizContainer');
      const vizUrl = 'https://public.tableau.com/views/WorldIndicators/GDPpercapita';
      const options = {
        width: containerDiv.offsetWidth,
        height: 700
      };

      const viz = new Tableau.Viz(containerDiv, vizUrl, options);
    }

    public ngOnInit(): void {
      this.initViz();
    }
  }
```

app.component.html:

```html
<div id="vizContainer"></div>
```

This will provide you with the most up-to-date functionality in the API.

## Using a JS library in a TS project

To use the library (without type declarations) in a TypeScript project follow the steps in [the following post](https://medium.com/@steveruiz/using-a-javascript-library-without-type-declarations-in-a-typescript-project-3643490015f3)


More details in [the API documentation](http://onlinehelp.tableau.com/current/api/js_api/en-us/help.htm)
