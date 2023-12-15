Main points

* Ubiqoutously used. Any client/server application is a distributed system.
* Vertical scaling of software is not possible. Rather horizontal scaling is the only viable approach.
  * That is to run software on multiple machines connected over a network and working as a single logical entity.
* Distributed systems might differ both:
  * In size, from a handful to hundreds of machines.
  * And in characteristics of their participants, from small handheld or sensor devices to high-performance computers.
  * Eg: databases - initially they used to run on a single node and over time most modern database systems have multiple nodes connected in clusters
    * To increase storage capacity
    * Improve performance
    * And enhance availability
* Most research in this field is related to the fact that nothing is reliable
    * communication channels may delay, reorder, or fail to deliver the messages,
    * processes may pause, slow down, crash, go out of control, or suddenly stop responding.
* The parallels between concurrent and distributed programming
    * CPUs are tiny distributed systems. Read more through [Consistency Models](https://learning.oreilly.com/library/view/database-internals/9781492040330/ch11.html#consistency_models).
      * Every concurrent program has some properties of a distributed system.
      * Threads access the shared state, perform some operations locally, and propagate the results back to the shared variables.
      * The main difference between a concurrent system and a distributed system:
        * In a concurrent system, we can have a shared memory, which processors can use to exchange information.
        * But in a distributed system, each processor has its local state, and participants communicate by passing messages.
        * But wait! What if you introduce a Database in a distributed system? Doesn't that introduce a shared state similar to a concurrent system?
          *  We need to build systems with reliable components, and eliminating a single point of failure in the form of the aforementioned single-node database can be the first step in this direction.
          *  We can do this by introducing some redundancy and adding a backup database.
          *  However, now we face a different problem: how do we keep multiple copies of the shared state in sync?
          *  We now know that sharing state is not as simple as just introducing a database, and have to take a more granular approach and describe interactions in terms of independent processes and passing messages between them.
          *  
      * The main difference between concurrent and parallel computing:
        * When two sequences of steps execute concurrently, both of them are in progress but only one of them is executed at any moment.
        * If two sequences execute in parallel, their steps can be executed simultaneously.
        * Concurrent operations overlap in time, while parallel operations are executed by multiple processors.
        * Concurrent execution is like having two queues for a single coffee machine while parallel execution is like having two queues for two coffee machines.
    * Though the ideas are not portable. Since most of the primitives can't be reused directly. Explore why?
* We need a different class of algorithms - called - "distributed algorithms"
    *  They describe the local behavior and interaction of multiple independent nodes.
    *  Nodes communicate by sending messages to each other.
    *  Algorithms define participant roles, exchanged messages, states, transitions, executed steps, properties of the delivery medium, timing assumptions, failure models, and other characteristics that describe processes and their interactions.
    *  Distributed algorithms serve many different purposes:
       * Coordination: A process that supervises the actions and behavior of several workers.
       * Cooperation: Multiple participants rely on one another to finish their tasks.
       * Dissemination: Processes cooperating in spreading the information to all interested parties quickly and reliably.
       * Consensus: Achieving agreement among multiple processes.   
* Communication pattern:
       * UDP
         * The sender doesn't have guarantees on whether or not its message has reached its destination.
       * Consensus generation
         *  
