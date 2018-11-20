---
layout: page
title: "NorJS"
---

### NorJS

NorJS is a full stack AngularJS / NodeJS project template for commercial 
projects.

### Features

*Click* titles below for more details.

<details><summary><strong>Development environment.</strong> Full working development setup.</summary><div markdown="1">

You can instantly start writing your app instead of boilerware to run your app.

Pre-configured Webpack, Babel, ES6, NodeJS, Mocha, Jasmine, etc.

Automatic reload from changes in the file system for fast development cycle.

</div></details>


<details><summary><strong>Unit test environment.</strong> Well designed unit testing environment.</summary><div markdown="1">

Karma & Jasmine pre-configured.

Including both unit & system tests.

</div></details>


<details><summary><strong>REST backend and micro services.</strong> Sample architecture and usable micro services.</summary><div markdown="1">

Multiple REST API services available and ready to use. 

<section style="padding-left:2em;padding-bottom:1em">


<details><summary><strong>ExpressJS + NodeJS example.</strong> Sample REST service.</summary><div markdown="1">

Authentication backend using standard Node.js and ExpressJS.

</div></details>


<details><summary><strong>Usable Micro Services.</strong> Ready to use production ready micro services.</summary><div markdown="1">

Working micro services built with [Sendanor Cloud-Backend](https://github.com/sendanor/cloud-backend).

<section style="padding-left:2em;padding-bottom:1em">

<details><summary><strong>Email Authentication Service</strong> Verify and authenticate users using only their email addresses.</summary><div markdown="1">

Verify and authenticate users into your system using only email addresses.

</div></details>


<details><summary><strong>SMTP Service</strong> Send email messages.</summary><div 
markdown="1">

Simple REST interface to a SMTP server for sending email.

</div></details>


</section>


</div></details>




</section>

</div></details>


<details><summary><strong>Good practices demostrated.</strong> Example implementations for ES6, AngularJS and NodeJS.</summary><div markdown="1">

Learn how to take full advance from ES6 while writing AngularJS and NodeJS.

We also provide easy to use utilities like abstract classes, interfaces, views,
components, and services which automate common tasks for all classes.

</div></details>


<details><summary><strong>Data model implementation.</strong> Shallow-CoW data models.</summary><div markdown="1">

Our implementation for JSON-configurable, shallow copy on write, data models 
-- with web based interface to manage it.

You may create your own data models using traditional abstract classes in ES6
 or use our dynamic JSON-style configuration file, which comes with a web 
interface to edit it.

These models have immutable getters and optional setters for properties. 

These setters will create shallow copies of the original object and only from 
the parts that actually changed. We gurantee that the original data object 
passed to the Model class will not be changed, and only shallow copies are 
made when inner properties change.

</div></details>


<details><summary><strong>Interface support.</strong> Protocols style 
implementation for ES6.</summary><div markdown="1">

Our utilities rely on our implementation of object interfaces. It is similar to
 the proposed Protocols feature in EcmaScript, which also uses Symbols.

```js
const listInterface = Interface.create({
  name: 'list', // This is just for prettier error messages.
  methods:{

    // Function arguments are not verified yet. As of now there can be anything here. 
    // You can also use your own Symbol here.
    getList: 'function (arg1, arg2)'

  }
});

class FooList {

  [listInterface.getList] (arg1, arg2) {
    return [];
  }
  
}
Interface.assert(listInterface, FooList);
```

</div></details>



<details><summary><strong>Component library.</strong> Build apps with our well designed, fast and scalable components.</summary><div markdown="1">

Easy to use UI components for most general use cases.

<section style="padding-left:2em;padding-bottom:1em">



<details><summary><strong>Table view.</strong> Generic component for pageable table views.</summary><div markdown="1">

This is a generic view component to create pageable table UI views for any 
resources implementing our interfaces.

You start by implementing a service -- like our `modelService` -- which 
implements `pageableInterface` and `tableRowInterface` for items, and then only 
thing left for you to do is to configure a state like:

```json
{
    "name": "models",
    "options": {
      "url": "/models",
      "component": "tableView",
      "resolve": {
        "content": "modelService"
      }
    }
}
```

You may also use it directly as a component:

```html
<table-view content="$ctrl.modelService"></table-view>
```

</div></details>


<details><summary><strong>Navigation component.</strong> Easy menu component.</summary><div markdown="1">

```html
<nr-nav collection="$ctrl.nav.items" options="$ctrl.nav"></nr-nav>
```

```js
$onInit () {
    super.$onInit();
    this.nav = {
      items: [
        {
          id: "main",
          icon: "home",
          label: "Home",
          isVisible: () => this.hasSession()
        }
      ],
      isVisible: item => item.isVisible()
    };
  }
```

</div></details>


<details><summary><strong>Input components.</strong> Common input components.</summary><div markdown="1">

All of our input components require AngularJS `ng-model`, so you can use
 `ng-disabled`, `ng-readonly`, etc.
 
```html
<nr-form submit="$ctrl.login($ctrl.model)">
    <section>
        <nr-text label="Username" ng-model="$ctrl.model.username"></nr-text>
    </section>
    <section>
        <nr-password label="Password" ng-model="$ctrl.model.password"></nr-password>
    </section>
    <section>
        <nr-submit-button label="Login"></nr-submit-button>
        <nr-reset-button label="Reset"></nr-reset-button>
    </section>
</nr-form>
``` 

<section style="padding-left:2em;padding-bottom:1em">

<details><summary><strong>Text input component.</strong> Text input component.</summary><div markdown="1">

```html
<nr-text label="Username" name="username" ng-model="$ctrl.model.username"></nr-text>
```

</div></details>


<details><summary><strong>Textarea input component.</strong> Textarea component.</summary><div markdown="1">

```html
<nr-textarea label="Description" name="description" ng-model="$ctrl.model.description"></nr-textarea>
```

</div></details>


<details><summary><strong>Password input component.</strong> Password input component.</summary><div markdown="1">

```html
<nr-password label="Password" name="password" ng-model="$ctrl.model.password"></nr-password>
```

</div></details>


<details><summary><strong>Checkbox input component.</strong> Checkbox input component.</summary><div markdown="1">

```html
<nr-checkbox label="Remember me" name="checkbox" ng-model="$ctrl.model.rememberMe"></nr-checkbox>
```

</div></details>


</section>

</div></details>


<details><summary><strong>Icon component</strong> powered with Font-Awesome.</summary><div markdown="1">

Create icons with `<nr-icon type="home 2x"></nr-icon>`.

</div></details>


<details><summary><strong>Custom components.</strong> Your specification, our implementation.</summary><div markdown="1">

We can implement custom components for your specific needs. Contact us.

</div></details>


</section>

</div></details>


<details><summary><strong>Event-based directives.</strong> Like AngularJS directives, but without watchers.</summary><div markdown="1">

Scope event based equivalent of `ng-if`, `ng-show`, `ng-class`, etc.

Our versions will not need watchers to operate when an event name is configured.

Usage: 

```html
<div nr-if="$ctrl.hasData()"
     nr-if-on="$ctrl.HAS_DATA_EVENT"
     nr-if-scope="$ctrl.$scope">{{$ctrl.data}}</div>
```

* `nr-if="..."` -- This expression works exactly like `ng-if` but supports additional opt-in features.
* `nr-if-on="eventName"` -- You can opt-in to use Scope event listener instead of Scope watcher to detect when the expression must be evaluated again. The expression will be evaluated once when the directive is first initialized and  again only when this event is broadcast on the scope.
* `nr-if-scope="$ctrl.$scope"` -- You can specify where this listener or watcher is installed

</div></details>


<details><summary><strong>Improve performance with faster digest loops.</strong> Suspend watchers for hidden scopes.</summary><div markdown="1">

This is a equivalent of `ng-show` and `ng-hide`, which will suspend scope 
watchers for this element if it is hidden, and resume watchers after the element 
becomes visible again. 

```html
<div ng-if="true"
     nr-show="$ctrl.hasData()"
     nr-show-on="$ctrl.HAS_DATA_EVENT"
     nr-show-scope="$ctrl.$scope"
     nr-show-suspend-watchers>{{$ctrl.data}}</div>
```

**Note!** You need to create a child scope with `ng-if="true"`, otherwise 
this would suspend current scope (eg. parent).

</div></details>


<details><summary><strong>Project website sample.</strong> Publish and blog about your project using Github Pages.</summary><div markdown="1">

Project website sample using Github Pages and jekyll.

Push your changes to the master branch and your project website is automatically
updated and hosted at Github. (It's actually this website.)

</div></details>


<details><summary><strong>No vendor lock-in.</strong> Everything is published with a free open source license.</summary><div markdown="1">

The project template (client, server and the website) material is provided 
under a MIT license.

Please contact us for other licensing options.

</div></details>


<details><summary><strong>Agile development.</strong> You can participate, too.</summary><div markdown="1">

This project is in active development. We have a small team of professionals 
working on it. 

Our customers can also participate on Github and affect the path we're taking.

</div></details>


<details><summary><strong>Commercial support.</strong> We are available to help you.</summary><div markdown="1">

We have years of experience working on world class AngularJS applications and we 
can help you, too. 

Without a general agreement contract our hourly fee is <strong>200 euros/hour</strong>.

</div></details>
