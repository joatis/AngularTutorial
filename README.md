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

## Master/Detail Component
* Separated the hero-detail from the hero component by using the CLI to generate a new component.
* Cut the hero-detail portion of the template from the Heroes template and pasted it in the newly generated heroes-detail template.
* Added the import module of the angular core to the heroes-detail module.
* Added the @Input decorator to the hero-detail class to add a input property to the heroes-detail class. This allows the parent component to send inputs to the child components via one-way binding.
* Updated the heroes-detail template to use that comonent's hero property instead of the selected hero property of the parent class.

## Services
Services are singletons that get instantiated on start up and are shared by components, modules and apps through injection.

Services can be created using the 'ng create service <service name>' This creates the files <name>.service, <name>.service.ts, <name>.service.spec.ts in the app directory.

Services can be provided in the sub-component, root-component and module level. It is customary to provide it at the module level. This is why the CLI has a --module=app option when creating a service.

### Providers Array 
By adding the service name to the providers: array in app.module.ts a single instance of the service is created and injected into any class of the app that asks for it.

### Injecting Services Into Components
Instead of importing services, they are injected. Injecting them is as easy as passing the service as a parameter to the components constructor signature:
`constructor(private heroService: HeroService) { } 

### Calling it on ngOnInit
Calling a service in the constructor is not good practice. Constructors should not *do* anything. Constructors should only assign properties to parameters. Instead you should create a wrapper function that calls the service. This wrapper function should be called in the ngOnInit() function. 

### Observable Data
When you make a call to a service you don't want stop execution, waiting to return so you want to make sure that the call is asynchronous (returning a promise, callback or observable.) By default the ng HTTP service returns an observable.

In the sub component you call the subscribe method on the returned value. When the service is finished the result can be assigned to the classes property. 
* The Observable class is from the RxJS/Observable library
* of() from 'rxjs/observable/of' allows you mock getting data from a server.


### Message Service
In the tutorial they used the Message Service to show how often services are injeced into other services. 
  

