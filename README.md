# Polymer App Toolbox - Demo template for PRPL pattern

This template, along with the `polymer-cli` toolchain, demonstrates use of the
"PRPL pattern."  This pattern allows fast first delivery and interaction of the
content at the initial route requested by the user, along with fast subsequent
navigation by pre-caching the remaining components required by the app and
progressively loading them on demand as the user navigates through the app.

The PRPL pattern, in a nutshell:

* **Push** components required for the initial route
* **Render** initial route ASAP
* **Pre-cache** components for remaining routes
* **Lazy-load** and progressively upgrade next routes on-demand

### Setup

##### Prerequisites

Install [polymer-cli](https://github.com/Polymer/polymer-cli):

    npm install -g polymer-cli

##### Setup

    git clone https://github.com/PolymerLabs/app-toolbox.git
    cd app-toolbox
    bower install

### Start the development server

This serves the app at `http://localhost:8080` and provides basic URL
routing for the app:

    polymer serve


### Build

    polymer build

### Test the build

This serves the minified version of the app in an unbundled state, as it would
be served by a push-compatible server:

    polymer serve src/unbundled

This serves the minified version of the app using fragment bundling, suitable
for serving from non H2/push-compatible servers or to clients that do not
support H2/Push:

    polymer serve src/bundled

### Extend

You can extend the app by adding more elements that will be demand-loaded
e.g. based on the route, or to progressively render non-critical sections
of the application.  Each new demand-loaded fragment should be added to the
list of `fragments` in the included `polymer.json` file.  This will ensure
those components and their dependencies are added to the list of pre-cached
components.


