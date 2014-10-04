# Inspector Gadget

Better AngularJS Popover with HTML content. I frequently need a richer popover experience than the one [angular-ui bootstrap](http://angular-ui.github.io/bootstrap/) provides. So I thought I'd open source our implementation! See a [few demos](http://softwaredoug.github.io/inspector-gadget/).

[![Build Status](https://travis-ci.org/softwaredoug/inspector-gadget.svg?branch=master)](https://travis-ci.org/softwaredoug/inspector-gadget)

## Dependencies
You'll need all the dependencies of bootstrap's popover plus angular:

- required:
    - bootstrap (js and css)
    - angular
    - jquery

## Install

    bower install inspector-gadget --save

## Documentation

### Add the minified JS:

	<script type="text/javascript" src="bower-components/inspector-gadget/inspector-gadget.min.js"></script>

### Add the directive to your app's module:
    
    angular.module('myApp', [
        'ngRoute', 'ngSanitize', ...
        'swd.inspector-gadget'  // ADD ME!
    ]).


### Use the directive:

    <inspector-gadget>
        <a href="#">Hover Me!</a>
        <inspector-title>
          I'm the popover's <em>title</em>!
        </inspector-title>
        <inspector-content>
          <ul>
          	Hello <em>World!</em>
          	<li ng-repeat="i in [1,2,3]">{{i}}</li>
          </ul>
        </inspector-content>
    </inspector-gadget>


We support most paramaters supported by [bootstap's popover](http://getbootstrap.com/javascript/#popovers). Simply apply the corresponding parameter to the inspector-gadget tag:

    <inspector-gadget data-placement="bottom" data-container="body">
    ...

Simply apply normal two-way data binding to the popover's, and let Angular do its magic!

### Limitations 

My boss calls these "opportunities for improvement".

#### Hovers Only

Currently, inspector-gadget only responds to hovers. We built this in part to do smarter hovering. So we currently only implement our own custom hovering style, which keeps the popover open even as you hover the popover. I plan on looking into getting other bootstrap triggers implemented.

#### A note on styling

Dont style using inspector-* tags, use the bootstrap popover classes (.popover, .popver-title, .popover-content) if you need to style or otherwise interact with that whole div. Or add your own classes/ids/etc to content within the popover.

### Sponsors

This project was developed for our search relevancy tuning tools [Quepid](http://quepid.com) and [Splainer](http://splainer.io) -- all while doing work for our Solr and Elasticsearch consulting firm [OpenSource Connections](http://opensourceconnections.com)
