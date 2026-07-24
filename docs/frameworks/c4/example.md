# Scneario

![Image](https://www.archimatetool.com/wp-content/uploads/2020/04/c4-overview.png)

This is the scenario that we are going to talk about

<br/>

## Level 1: System context diagram

Level 1, a system context diagram, shows the software system you are building and how it fits into the world in terms of the people who use it and the other software systems it interacts with. Here is an example of a system context diagram that describes an Internet banking system that you may be building:

![Image](https://imgopt.infoq.com/fit-in/3000x4000/filters:quality(85)/filters:no_upscale()/articles/C4-architecture-model/en/resources/c4-4-1529935843626.jpg)

Personal customers of the bank use the Internet banking system to view information about their bank accounts and to make payments. The Internet banking system uses the bank's existing mainframe banking system to do this, and uses the bank's existing e-mail system to send e-mail to customers. Colour coding in the diagram indicates which software systems already exist (the grey boxes) and those to be built (blue).

<br/>

## Level 2: Container diagram

Level 2, a container diagram, zooms into the software system, and shows the containers (applications, data stores, microservices, etc.) that make up that software system. Technology decisions are also a key part of this diagram. Below is a sample container diagram for the Internet banking system. It shows that the Internet banking system (the dashed box) is made up of five containers: a server-side web application, a client-side single-page application, a mobile app, a server-side API application, and a database.

![Image](https://imgopt.infoq.com/fit-in/3000x4000/filters:quality(85)/filters:no_upscale()/articles/C4-architecture-model/en/resources/c4-5-1529934730161.jpg)

The web application is a Java/Spring MVC web application that simply serves static content (HTML, CSS, and JavaScript), including the content that makes up the single-page application. The single-page application is an Angular application that runs in the customer's web browser, providing all of the Internet banking features. Alternatively, customers can use the cross-platform Xamarin mobile app to access a subset of the Internet banking functionality. Both the single-page application and mobile app use a JSON/HTTPS API, which another Java/Spring MVC application running on the server side provides. The API application gets user information from the database (a relational-database schema). The API application also communicates with the existing mainframe banking system, using a proprietary XML/HTTPS interface, to get information about bank accounts or make transactions. The API application also uses the existing e-mail system if it needs to send e-mail to customers.

<br/>

## Level 3: Component diagram

Level 3, a component diagram, zooms into an individual container to show the components inside it. These components should map to real abstractions (e.g., a grouping of code) in your codebase. Here is a sample component diagram for the fictional Internet banking system that shows some (rather than all) of the components within the API application.

![Image](https://imgopt.infoq.com/fit-in/3000x4000/filters:quality(85)/filters:no_upscale()/articles/C4-architecture-model/en/resources/c4-6-1529935329999.jpg)

Two Spring MVC Rest Controllers provide access points for the JSON/HTTPS API, with each controller subsequently using other components to access data from the database and mainframe banking system.

<br/>

## Level 4: Code

Finally, if you really want or need to, you can zoom into an individual component to show how that component is implemented. This is a sample (and partial) UML class diagram for the fictional Internet banking system that, showing the code elements (interfaces and classes) that make up the MainframeBankingSystemFacade component.

![Image](https://imgopt.infoq.com/fit-in/3000x4000/filters:quality(85)/filters:no_upscale()/articles/C4-architecture-model/en/resources/c4-7-1529935331734.jpg)

It shows that the component is made up of a number of classes, with the implementation details directly reflecting the code. I wouldn't necessarily recommend creating diagrams at this level of detail, especially when you can obtain them on demand from most IDEs.
