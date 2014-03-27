addDOMLoadEvent
===============

Cross-browser method of adding DOMContentLoaded events.
By Jesse Skinner, June 2006

Original blog post: [http://www.thefutureoftheweb.com/blog/adddomloadevent](http://www.thefutureoftheweb.com/blog/adddomloadevent)

There has been a problem with using window.onload in JavaScript. This event handler waits until all the images and other files load before executing. If you need some JavaScript to execute when the page loads, you usually only need the HTML to be downloaded, not all the images.

The event to use for this is "DOMContentLoaded", but only Firefox (and recently, Opera 9) support this. There are different ways to do this in every other browser, and people have been working on finding a complete solution to this for some time.

Very recently, this problem [has been solved](http://dean.edwards.name/weblog/2006/06/again/) by Dean Edwards, Matthias Miller and John Resig. There is a unique solution for Internet Explorer, Safari, and for W3C-compatible browsers (Firefox and Opera 9).

Very soon after, Dan Webb adapted the solution to prototype. Unlike the original solution, this code allows you to add more than one function to be executed when the DOM loads.

Inspired by [Simon Willison's addLoadEvent](http://blog.simonwillison.net/post/57956760515/addloadevent) function, I wanted to create a standalone generic solution that anyone could use without needing a specific framework.