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

Unlike other frameworks and libraries which abstract the DOM, Aurelia is closer to the metal. There is no virtual DOM, nothing custom whatsoever. Templating in Aurelia relies on the browsers templating engine to parse and execute our templates.

Want to listen to a click event on a button? `<button type="button" click.trigger="myCallback()"></button>` and `myCallback` gets defined inside of your view-model.
