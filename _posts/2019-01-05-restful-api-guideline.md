---
layout: post
title: RESTful API Guideline
subtitle: Best practices on how to design REST APIs. 
tags: [RESTful API]
image: /img/2019-01-05-restful-api-guideline/restful-api-logo-256.png
gh-repo: hardyscheel/hardyscheel.github.io
gh-badge: [follow]
---

<!--
RESTful API Guideline
Best practices on how to design REST APIs.
-->

As of the end of 2018 there were many discussions and implementations about REST APIs. Because I need some APIs for some projects, I decided to summon some of the best practices to realize REST APIs. This topic is very huge and the research very time consuming. There is also no standardization, but de facto standards and some very important recommendations that belong to the thematic of API usage and design. This document will be constantly revised.
HTTP/1.1 in combination with REST and such similar hacks will still be needed in the future for older devices/clients. HTTP/2 solves many of this workarounds, but it has to be more widely supported by clients.

There are two views of an API. In front (frontend) and behind (backend). We have to take into account these sight of views, especially when we define resources as API endpoints at the backend.

### Table of content

- [Definitions and Terminologies](#definitions-and-terminologies)
- [API endpoints](#api-endpoints)
- [Roles](#roles)

----

## Definitions and Terminologies
When designing RESTful APIs the following few terms are the most relevant to understand.

- **Resource** is an object or the representation of something. It has associated data and there can be methods to operate on it. E.g. *Spaceships*, *Animals* and *Employees* are resources. The methods we want to use on them are get, update, add or delete.
- **Collections** are set of resources, e.g. *Space Agencies* is the collection of *Space Agency* resource. *Companies* is the collection of *Company*.
- **URL** (Uniform Resource Locator) is a path through which a resource can be located and some actions can be performed on it.
- HTTPS **methods**: The most used and most useful to build powerful APIs are GET, POST, DELETE and PUT. But there are more.

----

## API endpoints
The meaning of RESTful APIs at the API endpoint could be explained as, that the paths declaration at the API endpoints should contain plural forms of resources. And the HTTP methods define the type of action to be performed on the resource.
Below are some example API endpoints we use (request) with HTTP methods. As an practical example we use *Spaceships* which has *Astronauts* and we use some HTTP methods on these *Astronauts*:

- method `GET` path `/astronauts` returns a list of all *astronauts* (this is a collection)
- method `GET` path `/astronauts/21` returns details of *astronaut* with the number *21*
- method `POST` path `/astronauts` creates a new *astronaut* and returns the details of the new *astronaut*
- method `DELETE` path `/astronauts/21` deletes the *astronaut* of number *21*
- method `DELETE` path `/astronauts` will delete all *astronauts* that belong to this collection
- method `PUT` path `/astronauts/21` updates the details of *astronaut* number *21*

Let's combine a resource under a resource where our *astronauts* belong to certain *space ships*:
	
- method `POST` path `/spaceships` creates a new resource in *spaceship* collection and returns the newly added resource
- method `GET` path `/spaceships/2/astronauts` returns a list of all *astronauts* belonging to *spaceship* number *2*
- method `GET` path `/spaceships/3/astronauts` returns a collection of a resource that contains a list of resources
- method `GET` path `/spaceships/3/astronauts/21` returns the details of *astronaut* number *21* belonging to *spaceship* number *3*
- method *DELETE* path `/spaceships/3/astronauts/21` deletes *astronaut* number *21* belonging to *spaceship* *3*

To interact with these APIs we use the form of a natural language. We use collections and also single resources as API endpoints to declare URLs. These resources are nouns and plural. To perform actions on a collection or resource we use the HTTP methods (GET, POST, DELETE, PUT). These methods are our verbs and we combine them.
Don't use ~~/addNewAstronaut~~ as an API endpoint or something similar which has a combination of resource (noun) and method (verb) to interact with the resource. Because the number of APIs will become massive on greater projects. They will also perform redundant actions.

----

## Roles
The API endpoint should never tell the type of data it will provide. Is the request data the data for admins, certain clients or users? The API has to decide if a client call is eligible to perform an action. A role base authorization system has to be implement first. The handler of the API should decide what data can be provided and what actions/methods are allowed. The roles are retrieved from the authentication token, or similar depending on your implemented authorization system. The API take the role of the requesting client and only provides the functionality and data that matches the role.