---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: true
info: |
  ## Angular Basics
  Presentation slides for developers.
drawings:
  persist: false
title: An overview of Angular
---

# An overview of Angular

Quick talk about angular basics

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs] (https://sli.dev/guide/syntax.html#notes)
-->

---

# What is Angular?

Angular is a platform and framework for building single-page client applications using HTML and TypeScript. 

- ✨ **High Speed & Optimum Performance** - Angular redefines the modern JavaScript virtual machine by turning templates into code. 
- 🎨 **CDK and Angular Material** - It helps in dynamic loading as well as unloading of the DOM to create a large list of high-performing data.
- 🧑‍💻 **Developer Friendly** - code highlighting, live coding with autocompletion
- 🎥 **Dependency Injection** -The built-in dependency injection of Angular makes application development easier for developers. It just asks your dependencies.
- 📤 **Cross-Platform** - You can develop progressive web applications (PWA). Also you can deploy an app as native as well as progressive. In addition, you can develop apps for the desktop with Angular  
- 🛠 **TypeScript** - With TypeScript, Angular offers a seamless experience to the developers. And TypeScript is the top choice for frontend development in 2019. It is highly efficient in detecting bugs and thereby, reduces developing time.d

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

---
layout: image-right

# the image source
image: ./reactive-programming.png
---

# Thinking in reactiveness

-  Reactive Programming is programming with asynchronous data streams  that can be CREATED,CHANGED or COMBINED on the go.
   -  When using reactive programming, data streams are going to be the spine of your application. Events, messages, calls, and even failures are going to be conveyed by a data stream. With reactive programming, you observe these streams and react when a value is emitted.


 

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# First steps angular


### Set up your environment

<p>&nbsp;</p>

1.  Install Angular CLI
```yaml 
npm install -g @angular/cli
``` 
2. Create a workspace and initial application

```yaml 
ng new my-app
``` 

3. Run the application

```yaml 
cd my-app
ng serve --open
``` 
The ng serve command launches the server, watches your files, and rebuilds the app as you make changes to those files. The --open (or just -o) option automatically opens your browser to http://localhost:4200/.


---
class: px-20
---

# Schematics

chematics are part of the Angular ecosystem. The Angular CLI uses schematics to apply transforms to a web-app project. 
Schematics that are included in the @schematics/angular collection are run by default by the commands ng generate and ng add.
<p>&nbsp;</p>

```yaml
ng generate my-schematic-collection:my-schematic-name
```

or

```yaml
ng generate my-schematic-collection:my-schematic-name

```
---

# @schematics/angular

|||
|---|---|
|app-shell|Generates an app shell for running a server-side version of an app|
|application|	Generates a new basic app definition in the "projects" subfolder of the workspace|
|class|	Creates a new, generic class definition in the given or default project|
|component|	Creates a new, generic component definition in the given or default project|
|directive|	Creates a new, generic directive definition in the given or default project|
|enum|	Generates a new, generic enum definition for the given or default project|
|guard|	Generates a new, generic route guard definition in the given or default project|
|interceptor|	Creates a new, generic interceptor definition in the given or default project|
|interface|	Creates a new, generic interface definition in the given or default project|


---

#### @schematics/angular

|||
|---|---|
|library|	Creates a new, generic library project in the current workspace|
|module|	Creates a new, generic NgModule definition in the given or default project|
|ng-new|	Creates a new project by combining the workspace and application schematics|
|pipe|	Creates a new, generic pipe definition in the given or default project|
|resolver|	Creates a new, generic resolver definition in the given or default project|
|service|	Creates a new, generic service definition in the given or default project|
|service-worker|	Pass this schematic to the "run" command to create a service worker|
|web-worker|	Creates a new, generic web worker definition in the given or default project|
|workspace|	Initializes an empty workspace and adds the necessary dependencies required by an Angular application|



---
layout: image-right
image: https://source.unsplash.com/collection/94734567/1920x1080
---

# Components

Components are the main building block for Angular applications.[^1]

```yaml
ng generate component
```



##### FlatComponent:

```ts {all|4|5|6|all}
import { Component } from '@angular/core';

@Component({
  selector: 'app-component-overview',
  template: '<h1>Hello World!</h1>',
  styles: ['h1 { font-weight: normal; }']
})

export class ComponentOverviewComponent {

}

```

<arrow v-click="4" x1="400" y1="500" x2="230" y2="410" color="#564" width="3" arrowSize="1" />

[^1]: [Learn More](https://angular.io/guide/component-overview)

<style>
h5{
  @apply mt-4
}
.footnotes-sep {
  @apply mt-10 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---
layout: image-left
image: https://source.unsplash.com/collection/94734567/1920x1080
---

# Components


#### SplitComponents:

```ts {all|4|5|6|all}
import { Component } from '@angular/core';

@Component({
  selector: 'app-component-overview',
  templateUrl: './component-overview.component.html',
  styleUrls: ['./component-overview.component.css']
})

export class ComponentOverviewComponent {

}

```

<arrow v-click="4" x1="900" y1="390" x2="730" y2="300" color="#564" width="3" arrowSize="1" />



<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>



---

# Modules

<div grid="~ cols-2 gap-2" m="-t-2">

Angular applications are modular and Angular has its own modularity system called NgModules. NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities They can contain components, service providers, and other code files whose scope is defined by the containing NgModule. They can import functionality that is exported from other NgModules, and export selected functionality for use by other NgModules.[^1]

```ts {all|4|5|6|7|8|all}
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
@NgModule({
  imports:      [ BrowserModule ],
  providers:    [ Logger ],
  declarations: [ AppComponent ],
  exports:      [ AppComponent ],
  bootstrap:    [ AppComponent ]
})
export class AppModule { }
```

</div>



[^1]: [Learn More](https://angular.io/guide/architecture-modules)

<style>
h1{
  @apply mt-4
}

.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}

</style>


---


# Angular libraries

<div grid="~ cols-2 gap-4">
<div>

Angular loads as a collection of JavaScript modules. You can think of them as library modules. Each Angular library name begins with the @angular prefix. Install them with the node package manager npm and import parts of them with JavaScript import statements.

In this way, you're using the Angular and JavaScript module systems together. Although it's easy to confuse the two systems, which share the common vocabulary of "imports" and "exports", you will become familiar with the different contexts in which they are used. [^1]

</div>
<div class="image-lib">
  <img  src="/libraries.svg" />

</div>
</div>

[^1]: [Learn More](https://angular.io/guide/ngmodules)

<style>
.image-lib{
  display:flex;
  justify-content: end;
}
img{  
  width: 80%
}
.footnotes-sep {
  @apply mt-0 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}

</style>



---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Directives

Directives are classes that add additional behavior to elements in your Angular applications.[^1]

The different types of Angular directives are as follows:

|||
|---|---|
|<Link to="8">Components</link>|Used with a template. This type of directive is the most common directive type.|
|<Link to="13">Attribute directives</link>| Change the appearance or behavior of an element, component, or another directive.|
|<Link to="14">Structural directives </link>|Change the DOM layout by adding and removing DOM elements.|






[^1]: [Learn More](https://angular.io/guide/component-overview)

<style>

.footnotes-sep {
  @apply mt-15 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Attribute directives

Change the appearance or behavior of DOM elements and Angular components with attribute directives.[^1]

- To create a directive, use the CLI command

```yaml
ng generate directive highlight
```

```ts {monaco}
import { Directive } from '@angular/core';

@Directive({
  selector: '[apphighlight]'
})
export class HighlightDirective {
  constructor() {    
   }
}
```

```html {monaco}
<p appHighlight>Highlight me!</p>
```



[^1]: [Learn More](https://angular.io/guide/attribute-directives)

<style>

.footnotes-sep {
  @apply mt-4 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 Add the next code in constructor to show how to modify
   constructor(private el: ElementRef) {
       this.el.nativeElement.style.backgroundColor = 'yellow';
    }
-->


---
layout: image-left
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Structural directives

Structural directives are directives which change the DOM layout by adding and removing DOM element.[^1]

Angular provides a set of built-in structural directives (such as NgIf, NgForOf, NgSwitch and others) which are commonly used in all Angular projects. [^2]

```html
<div *ngIf="hero" class="name">{{hero.name}}</div>
```

[^1]: [Learn More](https://angular.io/guide/structural-directives)
[^2]: [Built-in directives](https://angular.io/guide/built-in-directives)

<style>
p{
  opacity:0.5;
}
.footnotes-sep {
  @apply mt-4 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 Explain about change dom behavior with viewcontainer ref
-->


---
layout: 30-percent-img
image: https://source.unsplash.com/collection/94734577/1920x1080
---

# Understanding Pipes

Pipes are simple functions to use in template expressions to accept an input value and return a transformed value. Pipes are useful because you can use them throughout your application, while only declaring each pipe once. [^1]

- To create a pipe, use the CLI command

```yaml
ng generate pipe [name]
```

```ts {all|3|5-7|all}{monaco}
import {Pipe, PipeTransform} from '@angular/core';

@Pipe({name: 'truncate'})
export class TruncatePipe implements PipeTransform {
  transform(value: string) {
    return value.split(' ').slice(0, 2).join(' ') + '...';
  }
}
```

```html {monaco}
<p>The hero's birthday is {{ birthday | date:"MM/dd/yy" }} </p>
```

[^1]: [Learn More](https://angular.io/guide/pipes-overview)

<style>

.footnotes-sep {
  @apply mt-4 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 Mention advantages of Pipes, like dont be followed by the tree detector
-->


---
layout: default
---

# Services
Angular services are objects that get instantiated just once during the lifetime of an application. They contain methods that maintain data throughout the life of an application, i.e., data is available all the time. 

Components shouldn't fetch or save data directly and they certainly shouldn't knowingly present fake data. They should focus on presenting data and delegate data access to a service. [^1]

<div class="img-services">
  <img src="/Angular_Services.png" />
</div>

- To create a service, use the CLI command

```yaml
ng generate service [name]
```
[^1]: [Learn More](https://angular.io/tutorial/toh-pt4)

<style>
.img-services{
  display: flex;
  justify-content: center;

}
.img-services img{
  width: 70%;
  opacity: 1
}

p{
  opacity:0.5;
  font-size: 14;
}

.footnotes-sep {
  @apply mt-0 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 
-->



---
layout: image-right
image: https://source.unsplash.com/collection/94734560/1920x1080
---

# Service Structure

###### service:

```ts {all|4|all}{monaco}
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class HeroService {

  constructor() { }

}
```

###### component:

```ts {monaco}
constructor(private heroService: HeroService) {}
```

[^1]: [Learn More](https://angular.io/tutorial/toh-pt4)

<style>
.footnotes-sep {
  @apply mt-0 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 
-->


---
layout: image-right
image: https://source.unsplash.com/collection/94734570/1920x1080
---

# Data binding

Data binding automatically keeps your page up-to-date based on your application's state. You use data binding to specify things such as the source of an image, the state of a button, or data for a particular user. [^1]

<br>

```html {monaco}
<button type="button" [disabled]="isUnchanged">Save</button>
```

<br>
```html {monaco}
<input [disabled]="condition ? true : false">
<input [attr.disabled]="condition ? 'disabled' : null">
```

[^1]: [Learn More](https://angular.io/guide/binding-syntax)

<style>
.footnotes-sep {
  @apply mt-30 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 
-->


---
layout: image-right
image: https://source.unsplash.com/collection/94734570/1920x1080
---

# Types of Data binding

Angular provides three categories of data binding according to the direction of data flow:

- From source to view
- From view to source
- In a two-way sequence of view to source to view

||||
|---|---|---|
|Interpolation Property Attribute Class Style| <code>{{expression}} [target]="expression"</code>|One-way from data source to view target |
|Event| <code> (target)="statement" </code>| One-way from view target to data source|
|Two-way| <code>[(target)]="expression"</code>|Two-way|



[^1]: [Learn More](https://angular.io/guide/binding-syntax)

<style>
.footnotes-sep {
  @apply mt-30 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
table{
  font-size: 12px
}
</style>

<!--
 
-->



---
layout: two-cols
---

# Conditionals

<div class="column">

  ___*ngIf___ 

  Is the main Built-in directive that conditionally includes a template based on the value of an expression coerced to Boolean.

  ```html 
  <div *ngIf="condition">
    Content to render when condition is true.
  </div>
  ```

  ```html
  <ng-template [ngIf]="condition">
    <div>Content to render when condition is true.</div>
  </ng-template>
  ```

  ```html
  <div *ngIf="condition; else elseBlock">
    Content to render when condition is true.
  </div>
  <ng-template #elseBlock>
    Content to render when condition is false.
  </ng-template>
  ```
</div>


::right::

# Loops
<div class="column">

  __NgForOf__

  A structural directive that renders a template for each item in a collection. The directive is placed on an element, which becomes the parent of the cloned templates.

  ```html
  <li *ngFor="let item of items; index as i; trackBy: trackByFn">
    ...
  </li>
  ```

  ```html
  <ng-template ngFor let-item [ngForOf]="items" let-i="index" [ngForTrackBy]="trackByFn">
    <li>...</li>
  </ng-template>
  ```
</div>


<style>
  .column{
    padding-right: 1em;
  }
  
</style>


---
layout: two-cols
---

# Basic Routing

In a single-page app, you change what the user sees by showing or hiding portions of the display that correspond to particular components, rather than going out to the server to get a new page. As users perform application tasks, they need to move between the different views that you have defined.
To handle the navigation from one view to the next, you use the Angular Router. The Router enables navigation by interpreting a browser URL as an instruction to change the view. [^1]

::right::

<div class="big-code">

```ts {all|1-8|11-15|16-20|21-25|26|27|32-38|all}{monaco}
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

import { ComposeMessageComponent } from './compose-message/compose-message.component';
import { PageNotFoundComponent } from './page-not-found/page-not-found.component';

import { AuthGuard } from './auth/auth.guard';
import { SelectivePreloadingStrategyService } from './selective-preloading-strategy.service';

const appRoutes: Routes = [
  {
    path: 'compose',
    component: ComposeMessageComponent,
    outlet: 'popup'
  },
  {
    path: 'admin',
    loadChildren: () => import('./admin/admin.module').then(m => m.AdminModule),
    canLoad: [AuthGuard]
  },
  {
    path: 'crisis-center',
    loadChildren: () => import('./crisis-center/crisis-center.module').then(m => m.CrisisCenterModule),
    data: { preload: true }
  },
  { path: '',   redirectTo: '/superheroes', pathMatch: 'full' },
  { path: '**', component: PageNotFoundComponent }
];

@NgModule({
  imports: [
    RouterModule.forRoot(
      appRoutes,
      {
        enableTracing: false, // <-- debugging purposes only
        preloadingStrategy: SelectivePreloadingStrategyService,
      }
    )
  ],
  exports: [
    RouterModule
  ]
})
export class AppRoutingModule { }
```

</div>

[^1]: [Learn More](https://angular.io/guide/routing-overview)

<style>
.big-code{
  max-height: 60%;   
  display: flex;
  overflow-y: auto;
}
blockquote {
  code {
    @apply text-teal-500 dark:text-teal-400;
  }
}
</style>


---
layout: image-left
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Dependency injection

Dependencies are services or objects that a class needs to perform its function. Dependency injection, or DI, is a design pattern in which a class requests dependencies from external sources rather than creating them.
<br>
Angular's DI framework provides dependencies to a class upon instantiation. Use Angular DI to increase flexibility and modularity in your applications. [^1]



[^1]: [Learn more](https://angular.io/guide/dependency-injection)



<style>
.footnotes-sep {
  @apply mt-45 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>


---
layout: center
class: text-center
---

# Learn More

[Documentations](https://angular.io/docs) · [GitHub](https://github.com/angular/angular) · [Showcases](https://github.com/oscarandrespabonestrella/playground_angular)
