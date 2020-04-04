# angularObjective
# Angular Questions & Answers

> Click :star:if you like the project. Pull Request are highly appreciated.

### Table of Contents

| No. | Questions |
|---- | ---------
|1 | [What is Angular Framework?](#what-is-angular-framework)|
|2 | [Write a pictorial diagram of Angular architecture?](#write-a-pictorial-diagram-of-angular-architecture)|
|3 | [What are the key components of Angular?](#what-are-the-key-components-of-angular)|
|4 | [What are directives ,different types of directives?](#what-are-directives)|
|5 | [What is module?](#what-is-module?)|
|6 | [What are life cycle methods in Angular?](#what-are-life-cycle-methods-in-Angular?)|
1. ### What is Angular Framework?
Angular is a **TypeScript-based open-source** front-end platform that makes it easy to build applications with in web/mobile/desktop. The major features of this framework such as declarative templates, dependency injection, end to end tooling, and many more other features are used to ease the development.


2. ### Write a pictorial diagram of Angular architecture?
    The main building blocks of an Angular application is shown in the below diagram
    ![ScreenShot](overview2.png)

3. ### What are the key components of Angular?
    Angular has the below key components,|
    1. **Component:** These are the basic building blocks of angular application to control HTML views.|
    2. **Modules:** An angular module is set of angular basic building blocks like component, directives, services etc.| An application is divided into logical pieces and each piece of code is called as "module" which perform a single| task.
    3. **Templates:** This represent the views of an Angular application.|
    4. **Services:** It is used to create components which can be shared across the entire application.|
    5. **Metadata:** This can be used to add more data to an Angular class. |
    The metadata for a component class associates it with a template that defines a view. A template combines ordinary HTML with Angular directives and binding markup that allow Angular to modify the HTML before rendering it for display.
    The metadata for a service class provides the information Angular needs to make it available to components through dependency injection (DI).
  **[⬆ Back to Top](#table-of-contents)**
4. ### What are directives? different type of directives?
    Directives add behaviour to an existing DOM element or an existing component instance.|
   
    
    ```typescript
    import { Directive, ElementRef, Input } from '@angular/core';
    @Directive({ selector: '[myHighlight]' })
    export class HighlightDirective {
        constructor(el: ElementRef) {
          el.nativeElement.style.backgroundColor = 'yellow';
        }
    }
    ```
     Now this directive extends HTML element behavior with a yellow background as below
    ```html
    <p myHighlight>Highlight me!</p>
    ```

    Different type of directives are:|

    1. Components—directives with a template.|

    2. Structural directives—change the DOM layout by adding and removing DOM elements.e.g  NgFor and NgIf. |

    3. Attribute directives—change the appearance or behavior of an element, component, or another directive.e.g- NgStyle|
5. ### What is module?
  Modules are logical boundaries in your application and the application is divided into separate modules to separate the functionality of your application. Lets take an example of app.module.ts root module declared with @NgModule decorator as below,
      ```typescript
    import { NgModule }      from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';
    import { AppComponent }  from './app.component';

    @NgModule ({
       imports:      [ BrowserModule ],
       declarations: [ AppComponent ],
       bootstrap:    [ AppComponent ]
    })
    export class AppModule { }
    ```
    The NgModule decorator has three options
    1. The imports option is used to import other dependent modules. The BrowserModule is required by default for any web based angular application
    2. The declarations option is used to define components in the respective module
    3. The bootstrap option tells Angular which Component to bootstrap in the application
6. ### What are life cycle methods in Angular?
    Hook	Purpose and Timing
    ngOnChanges()	
      Respond when Angular (re)sets data-bound input properties. The method receives a SimpleChanges object of current and previous property values.
      Called before ngOnInit() and whenever one or more data-bound input properties change.

    ngOnInit()	
      Initialize the directive/component after Angular first displays the data-bound properties and sets the directive/component's input properties.
      Called once, after the first ngOnChanges().

    ngDoCheck()	
      Detect and act upon changes that Angular can't or won't detect on its own.
      Called during every change detection run, immediately after ngOnChanges() and ngOnInit().

    ngAfterContentInit()	
      Respond after Angular projects external content into the component's view / the view that a directive is in.
      Called once after the first ngDoCheck().

    ngAfterContentChecked()	
      Respond after Angular checks the content projected into the directive/component.
      Called after the ngAfterContentInit() and every subsequent ngDoCheck().

    ngAfterViewInit()	
      Respond after Angular initializes the component's views and child views / the view that a directive is in.
     Called once after the first ngAfterContentChecked().

    ngAfterViewChecked()	
      Respond after Angular checks the component's views and child views / the view that a directive is in.
      Called after the ngAfterViewInit() and every subsequent ngAfterContentChecked().

    ngOnDestroy()	
      Cleanup just before Angular destroys the directive/component. Unsubscribe Observables and detach event handlers to avoid memory leaks.
      Called just before Angular destroys the directive/component.
  **[⬆ Back to Top](#table-of-contents)**

