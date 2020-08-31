# System Architecture

<img src="https://raw.githubusercontent.com/dstar-design-gallery/dstar-docs/master/media/roundtrip.png" />

***

## Overview

DStar suite employs a 4-tier architecture: the traditional 3 tiers correspond to **dstar-client** (presentation), **dstar-server** (application), **dstar-database** (data), while the connection between server and parametric modeller adds a 4th tier, **dstar-connector** (model), that allows direct interaction between the aspect and the model. Each tier is developed with different tools and can be hosted on separate locations -ideally on the cloud.

### Client

* React-D3 Integration

* Concept of View

* Large-Screen-First  

### Server

* REST API & WebSockets

* API Doc

### Database

* Why NoSQL?

### Connector

* CAD-Neutrality

<img src="https://raw.githubusercontent.com/dstar-design-gallery/dstar-docs/master/media/roundtrip2.png" />