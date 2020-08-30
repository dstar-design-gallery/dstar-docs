# Introduction

***

Welcome to **D.Star Internal Documentation**. The following is primarily
intended for a technical audience, and it contains information regarding aspects of the D.Star
application, including its *goals*, *methods* and *usage*, as well as
specifics about its *installation*, *terminology*, *features*, and *system architecture*.

To suggest an addition or correction, contact the system administrator.

## What?

D.Star is a novel user interface (UI) to explore the *design space*. To do so, it offers a
suite of direct interactions with which designers can interact with large number of design
alternatives.

D.Star runs on any modern web browser.

## Why?

To explore the design space, designers create many design alternatives, consider
their properties, adjust them as they see fit, and repeat this process
as many times as needed, until they reach to a solution that they find satisfactory.
While existing CAD software is good for modelling, they are cumbersome to use for *exploring*.
Yet exploring is indispensible for creativity. This is where D.Star comes in.

## How?

D.Star is built with the core web technologies i.e. HTML, CSS and JavaScript.
More specifically, D.Star relies on the **MERN** stack ([MongoDB](https://www.mongodb.com/), [Express](https://expressjs.com/), [React](https://reactjs.org/) and [Node](https://nodejs.org/en/)).

This has several advantages. For one, since everything is ultimately in JavaScript, developers
can focus on a single language ecosystem. For another, developers can take advantage of the
powerful features that comes with **ES6** and **V8**.

D.Star system has four main components:

### 1) D.Star Client {docsify-ignore}

**D.Star Client** is built with **React**, an open source javascript framework tailor-made
for user interface development, and can handle complex user interaction scenarios.
Additionally, we use [Redux](https://redux.js.org/) and [Immutable](https://github.com/immutable-js/immutable-js) for state management, and [D3.js](https://d3js.org/) for creating interactive data visualizations.

D.Star is a **Single Page Application (SPA)**.

### 2) D.Star Server {docsify-ignore}

**D.Star Server** is built with **Node** -an open source javascript
framework that gives the power of javascript to use at the back-end. Additionally,
we use **Express** -a framework for Node that makes common back-end tasks
more streamlined (e.g. *browser routing*, *user authentication* etc.).

### 3) D.Star Database {docsify-ignore}

**D.Star Database** is built with **MongoDB**, which is based on a
*NoSQL*-type database scheme. Because of their flexibility, *NoSQL* type databases
are particularly useful when it is not clear what the data structure will look
like in the end, which is currently the case with D.Star.

### 4) D.Star Connector {docsify-ignore}

Finally, **D.Star Connector** is a *modeller-specific* plug-in script that facilitates communication
with an external parametric modeller to apply changes on a model and
get the resulting views. At the moment, we are using [Grasshopper 3D](https://www.grasshopper3d.com/) –a visual
programming language and environment that runs on the [Rhinoceros 3D](https://www.rhino3d.com/).
Our choice is due the popularity of Grasshopper among students and professionals alike.
However, D.Star can be easily adapted to other parametric modellers, requiring only a customized script.
