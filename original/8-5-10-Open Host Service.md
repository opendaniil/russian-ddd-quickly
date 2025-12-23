### Open Host Service

When we try to integrate two subsystems, we usually create a translation layer between them. This layer acts as a buffer between the client subsystem and the external subsystem we want to integrate with. This layer can be a consistent one, depending on the complexity of relationships and how the external subsystem was designed. If the external subsystem turns out to be used not by one client subsystem, but by several ones, we need to create translation layers for all of them. All those layers will repeat the same translation task, and will contain similar code.

When a subsystem has to be integrated with many others, customizing a translator for each can bog down the team. There is more and more to maintain, and more and more to worry about when changes are made.

The solution is to see the external subsystem as a provider of services. If we can wrap a set of Services around it, then all the other subsystems will access these Services, and we won’t need any translation layer. The difficulty is that each subsystem may need to interact in a specific way with the external subsystem, and to create a coherent set of Services may be problematic.

Define a protocol that gives access to your subsystem as a set of Services. Open the protocol so that all who need to integrate with you can use it. Enhance and expand the protocol to handle new integration requirements, except when a single team has idiosyncratic needs. Then, use a one-off translator to augment the protocol for that special case so that the shared protocol can stay simple and coherent.