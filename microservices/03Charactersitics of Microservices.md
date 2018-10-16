# Charactersitics of Microservices

**Multiple Components**

Software built as microservices can, by definition, be broken down into multiple component services.  Why?  So that each of these services can be deployed, tweaked, and then redeployed independently without compromising the integrity of an application.  As a result, you might only need to change one or more distinct services instead of having to redeploy entire applications.  But this approach does have its downsides, including expensive remote calls (instead of in-process calls), coarser-grained remote APIs, and increased complexity when redistributing responsibilities between components.2)

**Built For Business**

The microservices style is usually organized around business capabilities and priorities.  Unlike a traditional monolithic development approach—where different teams each have a specific focus on, say, UIs, databases, technology layers, or server-side logic—microservice architecture utilizes cross-functional teams.  The responsibilities of each team are to make specific products based on one or more individual services communicating via message bus.  In microservices, a team owns the product for its lifetime, as in Amazon’s oft-quoted maxim “[You build it, you run it](http://www.strehle.de/tim/weblog/archives/2010/11/09/1320).3)

**Simple Routing**

Microservices act somewhat like the classical UNIX system: they receive requests, process them, and generate a response accordingly.  This is opposite to how many other products such as ESBs (Enterprise Service Buses) work, where high-tech systems for message routing, choreography, and applying business rules are utilized.  You could say that microservices have smart endpoints that process info and apply logic, and dumb pipes through which the info flows.4)

**Decentralized**

Since microservices involve a variety of technologies and platforms, old-school methods of centralized governance aren’t optimal.  Decentralized governance is favored by the microservices community because its developers strive to produce useful tools that can then be used by others to solve the same problems.  Just like decentralized governance, microservice architecture also favors decentralized data management.  Monolithic systems use a single logical database across different applications.  In a microservice application, each service usually manages its unique database.5)

### Decentralized Data Management

 Decentralization of data management presents in a number of different ways. At the most abstract level, it means that the conceptual model of the world will differ between systems. This is a common issue when integrating across a large enterprise, the sales view of a customer will differ from the support view. Some things that are called customers in the sales view may not appear at all in the support view. Those that do may have different attributes and (worse) common attributes with subtly different semantics. This issue is common between applications, but can also occur within applications, particular when that application is divided into separate components. A useful way of thinking about this is the Domain-Driven Design notion of [Bounded Context](https://martinfowler.com/bliki/BoundedContext.html). DDD divides a complex domain up into multiple bounded contexts and maps out the relationships between them. This process is useful for both monolithic and microservice architectures, but there is a natural correlation between service and context boundaries that helps clarify, and as we describe in the section on business capabilities, reinforce the separations.

 As well as decentralizing decisions about conceptual models, microservices also decentralize data storage decisions. While monolithic applications prefer a single logical database for persistant data, enterprises often prefer a single database across a range of applications - many of these decisions driven through vendor's commercial models around licensing. Microservices prefer letting each service manage its own database, either different instances of the same database technology, or entirely different database systems - an approach called [Polyglot Persistence](https://martinfowler.com/bliki/PolyglotPersistence.html). You can use polyglot persistence in a monolith, but it appears more frequently with microservices.

Decentralizing responsibility for data across microservices has implications for managing updates. The common approach to dealing with updates has been to use transactions to guarantee consistency when updating multiple resources. This approach is often used within monoliths.

Using transactions like this helps with consistency, but imposes significant temporal coupling, which is problematic across multiple services. Distributed transactions are notoriously difficult to implement and as a consequence microservice architectures [emphasize transactionless coordination between services](http://www.eaipatterns.com/ramblings/18_starbucks.html), with explicit recognition that consistency may only be eventual consistency and problems are dealt with by compensating operations.

Choosing to manage inconsistencies in this way is a new challenge for many development teams, but it is one that often matches business practice. Often businesses handle a degree of inconsistency in order to respond quickly to demand, while having some kind of reversal process to deal with mistakes. The trade-off is worth it as long as the cost of fixing mistakes is less than the cost of lost business under greater consistency.

**Failure Resistant**

Like a well-rounded child, microservices are designed to cope with failure.  Since several unique and diverse services are communicating together, it’s quite possible that a service could fail, for one reason or another (e.g., when the supplier isn’t available).  In these instances, the client should allow its neighboring services to function while it bows out in as graceful a manner as possible. However, [monitoring microservices](https://smartbear.com/en-us/learn/performance-monitoring/monitoring-microservices/) can help prevent the risk of a failure. For obvious reasons, this requirement adds more complexity to microservices as compared to monolithic systems architecture.  6)

**Evolutionary**

Microservices architecture is an evolutionary design and, again, is ideal for evolutionary systems where you can’t fully anticipate the types of devices that may one day be accessing your application..  Many applications start based on monolithic architecture, but as several unforeseen requirements surfaced, can be slowly revamped to microservices that interact over an older monolithic architecture through APIs.