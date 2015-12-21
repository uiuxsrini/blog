---
layout: post
title: Angular Vs Polymer
description: "The difference between Polymer and Angular"
modified: 2015-12-21
author: Adhikari Srinivasa Kumar
---

A year after pulling back the curtains on the Polymer Project, Google’s taken part of I/O 2014 to demo what the code can do. Right on cue, the web is abuzz with discussion comparing Polymer to other popular web frameworks, and it’s no surprise since it bears some resemblance to Google’s very own AngularJS. Join me after the break as I introduce Polymer and explore just how it relates to Angular.

#####What is Polymer?

Polymer is a library for creating Web Components, which are a set of W3C standards and upcoming browser APIs for defining your own custom HTML elements. With the help of polyfills and sugar, it can create these custom elements and bring Web Component support to browsers that don’t play nice with the standard just yet.

Custom elements? Huh? They look like this:

{% highlight css %}
<google-map lat="37.790" long="-122.390"></google-map>
{% endhighlight %}

Seem familiar? They’re are very similar to Angular directives. As you’d expect, the result would be a Google Map plugged directly into your webpage.

#####So, how does Polymer differ from Angular?

Angular is a complete framework for building webapps, whereas Polymer is a library for creating Web Components. Those components, however, can then be used to build a webapp.

Angular has high-level APIs for things like services, routing, server communication and the like. Polymer, on the other hand, doesn’t provide these things except as separate web components from their core library. Instead, it focuses on allowing you to create rich, powerful, reusable web components, which could be used to build webapps like those built with Angular. In the future, the lines could be blurred further as frameworks like Angular may leverage Web Components.

Even though Angular and Polymer aim to do different things, there is currently some overlap. Web components and Angular’s element directives are very similar, and if there’s a comparison to be made it should be between Polymer’s Custom Elements and Angular’s directives.

#####Angular directives vs. Custom Elements

Polymer (more specifically Shadow DOM) provides the ability to compose encapsulated JS, CSS, and HTML as Custom Elements, much like Angular element directives.

Angular directives are conceptually similar to Custom Elements but they are implemented without the use of the Web Components APIs. Angular directives are a way to build custom elements, but Polymer and the Web Components specification are the standards-based way to do it.

Similar to Angular, Polymer elements provide templating and bi-directional data binding. However, they also provide new functionality such as the Shadow DOM, which enables encapsulation of CSS. Angular directives don’t have any notion of style encapsulation, but Angular is expected incorporate that functionality eventually.

In the future, both will be used together. Because custom elements will be the DOM, they’ll work seamlessly with frameworks like Angular. The Angular team has said they will eventually use the underlying Web Components APIs (Custom Elements, Shadow DOM, etc.).

Polymer Custom Element:

{% highlight css %}
<polymer-element name="user-gravatar" attributes="email">
  <template>
    <img src="https://secure.gravatar.com/avatar/{{gid}}" />
  </template>
  <script>
    Polymer('user-gravatar', {
      ready: function() {
        this.gid = md5(this.email);
      }
    });
  </script>
</polymer>
{% endhighlight %}



Angular directive:

{% highlight css %}
  app.directive('user-gravatar', ['md5', function() {
  return {
    restrict: 'E',
    link: function(scope, element, attrs) {
      scope.gid = md5(attrs.email);
    },
    template: '<img src="https://gravatar.com/avatar/{{gid}}" />'
  };
  }]);
{% endhighlight %}

As you can see, Polymer uses a declarative syntax (another element!) to create custom elements. Both accomplish the same thing but using different approaches.

#####Can Angular and Polymer be used together?

Yes! You can use Polymer custom elements inside of an Angular app. Web components are just regular DOM elements, so they have attributes, emit events, and can contain child elements.

#####What about the future of both projects?

Angular and Polymer will remain separate projects with their own goals. That said, Angular has announced they’ll eventually move to use the Web Components APIs in their underlying architecture.

For Angular 2.0, Web Components will work seamlessly within Angular apps and directives, and components written in Angular will export to Web Components to be used by Polymer or other libraries.

As the Web Components specification matures and browsers implement the various APIs, Polymer elements will utilize native browser functionality instead of
polyfills. Eventually, once browser support has improved, Polymer’s polyfill layer can be gracefully removed.
