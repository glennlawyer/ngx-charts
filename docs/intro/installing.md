# Installing

You can grab the latest release from the [Releases Page](https://github.com/swimlane/ngx-charts/releases) in Github or via NPM.

* `npm install @swimlane/ngx-charts --save`

Also, the release code is checked in and resides [here](https://github.com/swimlane/ngx-charts/tree/master/release).

You will also need to install the peer dependencies of the project:

* `npm install d3 --save`

Check the `package.json` file for the required versions of these dependencies.

### JavaScript
- `release/index.js` - UMD Version
- `release/index.min.js` - UMD Version Minified

## Developing
If you want to run the demos locally, just do:

- `npm i`
- `npm start`
- Browse to [http://localhost:9999](http://localhost:9999)

## Adding to an Angular/Ionic project

Several additional steps are required to incorporate ngxcharts into an Ionic project.

Install browswer animations
```
npm install --save @angular/animations
```

Include both `browser animations` and `ngx-charts` in your app.module.ts.
```
import { BrowserModule } from '@angular/platform-browser';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations'; // <---
import { IonicApp, IonicErrorHandler, IonicModule } from 'ionic-angular';
...

@NgModule({
  declarations: [
    MyApp,
  ],
  imports: [
    BrowserModule,
		BrowserAnimationsModule, // <---
    IonicModule.forRoot(MyApp),
		NgxChartsModule, // <---
    ...
  ],
  ```
  
Additionaly, if you are lazy-loading a page, `NgxChartsModule` needs to be included in that page's module. For example, if the page is "AboutPage", then the file `About.module.ts` should read:
```
import { NgModule } from '@angular/core';
import { IonicPageModule } from 'ionic-angular';
import { AboutPage } from './about';
import { NgxChartsModule } from "@swimlane/ngx-charts/"; // <---

@NgModule({
  declarations: [
    AboutPage,
  ],
  imports: [
    IonicPageModule.forChild(AboutPage),
		NgxChartsModule // <---
  ],
	exports:[
		AboutPage
	]
})
export class AboutPageModule {}
```


