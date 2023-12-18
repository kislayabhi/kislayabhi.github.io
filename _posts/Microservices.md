What are microservices?

* Microservices are independently releasable services that are modeled around a business domain.
* They are a type of service-oriented architecture, albeit one that is opinionated about how service boundaries should be drawn, and one in which independent deployability is key.
* They are technology agnostic, which is one of the advantages they offer.

Key concepts of Microservices?
* Independent deployability
  * To ensure this, we need to make sure our microservices are loosely coupled. That is, we must be able to change one service without having to change anything else. One implementation choice that makes it difficult is - the sharing of databases.
* Modeled around a business domain
  * By modeling services around business domains, we can make it easier to roll out new functionality and recombine microservices in different ways to deliver new functionality to our users.  


This stood apart to me so much: The now famous Conway’s law states the following:

Organizations that design systems...are constrained to produce designs that are copies of the communication structures of these organizations.

Melvin Conway, “How Do Committees Invent?”

References: https://learning.oreilly.com/library/view/building-microservices-2nd/9781492034018/ch01.html#idm45699546607360
