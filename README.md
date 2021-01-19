# Why Aurelia 2

Why you should choose Aurelia 2 for your next Web application in 2021 (and beyond).

## Introduction

More often than not, when developers and companies start a new Web application project, they will lean for React in most cases.

And React has proven itself to be a reasonable choice for front-end development (and other platforms). However, there is no denying that React of 2021 has a bit of a learning curve when you start throwing in additional packages like routers and state management solutions like Redux.

This overheard can slow down the developer experience substantially. 

If you have ever had to train someone in your architecture or help upskill members of your team who might not be front-end oriented, React itself is simple, but many of the packages the community have unofficially chosen as the "go to" packages for features are not. 

What if I told you there is an easier more modern solution that is actually a better option in many scenarios you might find yourself building for?

I have been working with Aurelia since 2015. Version 1 launched in 2015 and sadly, it just didn't take off. Quite a few developers fell in love with it (myself included) and I have been fortunate to sustain a career for six years (and counting) both working on Aurelia applications full-time as well as consulting for companies using Aurelia. 

It wasn't the fact Aurelia was terrible, it was quite forward thinking and the message of conventions + web standards resonated with a lot of people. It just unfortunately came at a time when React was taking off and developers had bought into React promoting simplicity and lack of features. Developers were also quite scarred from AngularJS, so frameworks were not the hot thing in 2015.

Before I worked with Aurelia, I too, had worked with React and fell under its spell. React at the time compared to everything else was blazingly fast, compared to the likes of AngularJS, Backbone and other now outdated options, React was revolutionary.

The original vision of Aurelia as it enters its second major version is still the same, the syntax for templating and its core philopshy of convention over configuration as well as abidance by web standards remains the same. Rob Eisenberg the creator of Aurelia envisioned a future of development where frameworks were accompanients of web standards, not custom template parsers or anything else too foreign.

This is not to say that Aurelia is perfect, nor is it to say that Aurelia is better than everything else. I truly believe that no matter what you choose to work with, what matters most is whether your chosen framework or library does everything you want it too and if it makes the developer experience better.

## Advantages

Aurelia doesn't offer anything new or revolutionary when you truly break down what makes it great. Many of my favourite things about Aurelia are things that are not proprietary to Aurelia at all. How its templating is just HTML, your components are Javascript classes, its support for Web Components and Shadow DOM.

### Write Less, Do More

Since version 1, Aurelia has strongly adhered to the principle: write less, do more. This is because Aurelia follows a convention over configuration approach. If you have worked with Angular before, then you might know what I am talking about. Aurelia will assume some things by default about how you might want to build your apps and in about 95% of the cases I have encountered, you never have to change them.

A lot of other options out there love to make this claim, but then they make you configure modules, they make you learn some obscure templating language or HTML variant, then you have to become familiar with their CLI and way of architecting your apps. With Aurelia, it gives you the basics you need and then just gets out of your way. No gimmicks, just a simple development experience.

Aurelia is intuitive and I have first-hand experience training junior developers as well as senior developers in Aurelia. More often than not, you will see developers regardless of their skill level pushing code to production in a matter of days not months or weeks. There is just so much less to learn with Aurelia than other frameworks or libraries.

### Easy to learn

I am not just talking about a simple hello world app here. All frameworks and libraries promote that they are easy to learn, leaving out the fact that many of these options don't give you everything you need out-of-the-box, requiring you to install packages to give you basic features like routing or ability to make API requests. There are no custom component formats with non-standard file extensions, Aurelia components are Javascript and HTML out-of-the-box.

This is a simple component that displays a first and last name (whatever we provide to the component), without even needing any Javascript whatsoever. This component is called `display-name.html`:

```
<bindable name="firstName"></bindable>
<bindable name="lastName"></bindable>

<h2>${firstName} ${lastName}</h2>
```

To use this component we can write: ``<display-name first-name="John" last-name="Smith"></display-name>``

As you can see, no HTML supersets to be found. This is HTML with one difference, the string interpolation syntax ``${}`` which you might be familiar if you have ever worked with [template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) before. It's the same dollar sign and curly braces, you can even use expressions inside of them like this ``${2 + 2}``

Unlike other frameworks and libraries which abstract the DOM, Aurelia is closer to the metal. There is no virtual DOM, nothing custom whatsoever. Templating in Aurelia relies on the browsers templating engine to parse and execute our templates. Want to listen to a click event on a button? `<button type="button" click.trigger="myCallback()"></button>` and `myCallback` gets defined inside of your view-model.

### Beginner friendly 

Aurelia is one of the most beginner friendly frameworks around today. Because you can leverage existing CSS, HTML and JavaScript knowledge, learning to build Aurelia applications is so much easier.

If you are familiar with React, then you would know if differs from conventional HTML in some ways (className instead of class) 

### Syntax

What all frameworks and libraries boil down to is their syntax, how flexible is the templating system? Do I need a PhD to understand how to loop through some data and react to some changes?  This is where Aurelia sets itself apart from other frameworks and libraries. Aurelia is built from the ground up with developer experience (DX) in mind, from how you build applications to how you ship them.

#### Reactive Assignments

When a value changes, you want that change to be reflected in your view.

```
export class MyComponent {
  count = 0;
  
  increment() {
    this.count = this.count + 1;
  }
}
```

```html
<button type="button">Clicked ${count} ${count == 1 ? 'time' : 'times'}</button>
```

#### HTML Syntax

I don't know about you, but I find a lot of templating syntax in other frameworks and libraries to be kind of ugly. Why do we need to use colons and hashes all over the place? Why can't our HTML just resemble HTML with a few little enhancements to make certain features (like binding) work?

**Repeating over a collection of data using repeat.for**

```
<ul>
  <li repeat.for="item of items">${item.name}</li>
</ul>
```

**If statements using if.bind**

```
<h1 if.bind="booleanValue">I am truthy</h1>
```

```
<h1 if.bind="!booleanValue">I am falsy</h1>
```

```
<h1 if.bind="booleanValue">I am truthy</h1>
<h1 else>I am falsy</h1>
```

#### Computed Properties

If you have worked with Vue before, you might be familiar with the concept of computed properties. A getter function that returns a value and inside of it, can deal with multiple concatenated values returned as a string. In Aurelia, dependencies are automatically tracked, so you can write getter functions like the following and not have to worry about specifying dependencies.

```
export class MyComponent {
    private firstName = 'John';
    private lastName = 'Smith';
    
    // Whenever firstName or lastName change, this getter will be updated
    get myName() {
      return `${this.firstName} ${this.lastName}`;
    }
}
```

#### Two-way Binding

For those who have worked with React, you will already know that it doesn't support two-way binding. While two-way binding isn't always needed and better options exist, two-way binding which also exists in Svelte, Angular and Vue can be a gamechanger when working with forms. Instead of littering your template with callbacks, you bind to properties. By default, form elements are two-way binding.

```
export class MyComponent {
  name = '';
}
```

```html
<input value.bind="name" placeholder="What should we call you?">
<p>Hello ${name != '' ? name : 'Mysterious being'}!</p>
```

### It's Fast!

While Aurelia doesn't focus on trying to win benchmarks which are more often than not, not truly reflective of real world development environments, Aurelia is no slouch. Despite the fact it is a fully-featured batteries included framework, it is fast. You won't find any DOM abstractions like Virtual DOM's here. Aurelia works closer to the metal than some other options and as a result, it offers the kind of performance you can visibly see.

This is not to say that Aurelia is the fastest and best performing out there. However, it's not slow and there are no perceived issues with performance. Look beyond vanity benchmarks for the real story.

### Alignment With Web Standards

While other frameworks and libraries persue their own ways of doing things, ignoring the problems that web bodies like WHATWG and W3C have already solved, Aurelia leans into them. The less that Aurelia can do and more the web can do, the better things will be for everyone.

Whether it's support for Shadow DOM or Web Components, Aurelia supports it. Make requests to your API using Fetch, write components that are compatible with non-framework like approaches. Writing Aurelia apps will never feel like coding inside of a walled garden.

### Makes No Assumptions

Don't you hate it when framework and library authors tell you that things have to be done a specific way? I have never been one for rules, but sometimes rigid options (despite providing consistency) can slow you down. Aurelia doesn't tell you the right or wrong way to do things, like every flexible tool in the ecosystem, a set of sensible defaults should be provided, but shouldn't be strictly forced onto users.

This is why every aspect of Aurelia offers flexibility for when you want and need it, but doesn't force you to write things a certain way or use specific API's.
