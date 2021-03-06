Angular course
==============

Lesson 2
--------------

#### Source and references
- https://angular.io/guide/architecture
- https://angular.io/guide/architecture-components
- https://angular.io/guide/attribute-directives
- https://angular.io/guide/structural-directives
- https://angular.io/guide/pipes

### Binding
![Angular architecture](https://angular.io/generated/images/guide/architecture/overview2.png)

...Without a framework, you would be responsible for pushing data values into the HTML controls and turning user responses into actions and value updates. Writing such push and pull logic by hand is tedious, error-prone, and a nightmare to read, as any experienced jQuery programmer can attest.

Angular supports two-way data binding, a mechanism for coordinating the parts of a template with the parts of a component. Add binding markup to the template HTML to tell Angular how to connect both sides.

The following example shows the four forms of data binding markup. Each form has a direction: to the DOM, from the DOM, or both...

```typescript
@Component({
    ...
    templateUrl: './template.html'
    ...
})
export class BindingExample {
    public title = 'Hello World';
    public subtitle = 'Simple example';
    public user = '';

    sayHello() {
        if (!user) {
            return;
        }

        alert(`Hello ${this.user}!`);
    }
}
```

```html
<!-- property binding [subtitle] and interpolation {{title}} -->
<awesome-component [subtitle]="subtitle">{{title}}</awesome-component>
<!-- two way binding -->
<input [(ngModel)]="user" />
<!-- event binding -->
<button (click)="sayHello()"></button>
```


##### usage
```html
<!-- quote pipe -->
<p>{{ "learn to swim" | quote}}</p>

<!-- quote pipe with by parameter. To use a parameter just add the : symbol before the value -->
<p>{{ "learn to swim" | quote:'Tool'}}</p>

```


### Directives
...Angular templates are dynamic. When Angular renders them, it transforms the DOM according to the instructions given by directives. A directive is a class with a @Directive() decorator...


There are two other kinds of directives: structural and attribute. 

#### Structural directives

Structural directives alter layout by adding, removing, and replacing elements in the DOM. The example template uses two built-in structural directives to add application logic to how the view is rendered...

```html
<!-- repeats the div element for every value inside the dataArray-->
<div *ngFor="let data of dataArray">{{data}}</div>
<!-- shows the title on if showTitle is true-->
<div *ngIf="showTitle">{{title}}</div>
```

#### Attribute directives

Attribute directives alter the appearance or behavior of an existing element. In templates they look like regular HTML attributes, hence the name.

```html
<div [ngClass]="'awesome-class big-title-class'">...</div>

<div [ngClass]="anyStringOrObject">...</div>
```
