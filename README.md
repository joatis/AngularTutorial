# AngularTutorial
Angular2 Tutorial from angular.io

## Creating the Heroes Editor
* Create a new comonent using $ ng new component <componentName>
* This will create a new component, css and template for the component.
* However you still have to create a class for the model to refer to.
* When you need 2-way binding be aware that the FormsModule is not enabled
by default. You need to import the Forms Module into the app.module.ts and 
add it to the NgModules array.
* When you create components using the CLI it automatically adds it to the APP shell for you.

## Displaying a Heroes List
* Created a mock data set and imported it to the heroes component model.
* In TypeScript you can export and import variables, functions, classes and interfaces across files but within a name-space.
* In TypeScript, declaring a variable with the 'let' keyword gives it block scope.
* Added a list to the template and populate it with the items from the mock objects using the *ngFor iterator.
* Changed the hero class property to an undefined instance of a Hero object.
* Wrapped the Hero detail block in a div with the *ngIf property to show the element only when there is a defined selectedHero property.
* Added a binding to each element that applies the 'selected' class to a hero item if that hero is the selected hero.

### Things to look Up:
* What is the meaning of the different syntax for different types of bindings?
    * A * prefix for conditionals like *ngIf, *ngFor?
    * () surrounding events like 'click'?
    * [] for binding a class based on an expression?
    