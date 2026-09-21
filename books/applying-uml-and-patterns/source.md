
# Chapter 9. Domain Models


<<<PDF_PAGE 218>>>
 
Chapter 9. Domain Models
It's all very well in practice, but it will never work in theory.
anonymous management maxim
Objectives
Identify conceptual classes related to the current iteration.
Create an initial domain model.
Model appropriate attributes and associations.
 

<<<PDF_PAGE 219>>>
 
Introduction
A domain model is the most importantand classicmodel in OO analysis.[1]
 It illustrates noteworthy
concepts in a domain. It can act as a source of inspiration for designing some software objects
and will be an input to several artifacts explored in the case studies. This chapter also shows the
value of OOA/D knowledge over UML notation; the basic notation is trivial, but there are subtle
modeling guidelines for a useful modelexpertise can take weeks or months. This chapter explores
basic skills in creating domain models.
[1] Use cases are an important requirements analysis artifact, but are not object-oriented. They emphasize an activity view.
more advanced domain modeling
 p. 507
[View full size image]
As with all things in an agile modeling and UP spirit, a domain model is optional. UP artifact
influence emphasizing a domain model is shown in Figure 9.1
. Bounded by the use case scenarios
under development for the current iteration, the domain model can be evolved to show related
noteworthy concepts. The related use case concepts and insight of experts will be input to its
creation. The model can in turn influence operation contracts, a glossary, and the Design Model,
especially the software objects in the domain layer of the Design Model.
Figure 9.1. Sample UP artifact influence.
[View full size image]
<<<PDF_PAGE 220>>>
domain layer
 p. 136
 

<<<PDF_PAGE 221>>>
 
9.1. Example
Figure 9.2
 shows a partial domain model drawn with UML class diagram notation. It illustrates
that the conceptual classes of Payment and Sale are significant in this domain, that a Payment
is related to a Sale in a way that is meaningful to note, and that a Sale has a date and time,
information attributes we care about.
Figure 9.2. Partial domain modela visual dictionary.
[View full size image]
Applying the UML class diagram notation for a domain model yields a conceptual perspective
model.
conceptual perspective
 p. 12
Identifying a rich set of conceptual classes is at the heart of OO analysis. If it is done with skill
and short time investment (say, no more than a few hours in each early iteration), it usually pays
off during design, when it supports better understanding and communication.
<<<PDF_PAGE 222>>>
Guideline
Avoid a waterfall-mindset big-modeling effort to make a thorough or "correct" domain
modelit won't ever be either, and such over-modeling efforts lead to analysis
paralysis, with little or no return on the investment.
 

<<<PDF_PAGE 223>>>
 
9.2. What is a Domain Model?
The quintessential object-oriented analysis step is the decomposition of a domain into noteworthy
concepts or objects.
A domain model is a visual representation of conceptual classes or real-situation objects in a
domain [MO95
, Fowler96
]. Domain models have also been called conceptual models (the term
used in the first edition of this book), domain object models, and analysis object models.[2]
[2] They are also related to conceptual entity relationship models, which are capable of showing purely conceptual views of
domains, but that have been widely re-interpreted as data models for database design. Domain models are not data models.
Definition
In the UP, the term "Domain Model" means a representation of real-situation
conceptual classes, not of software objects. The term does not mean a set of
diagrams describing software classes, the domain layer of a software architecture, or
software objects with responsibilities.
The UP defines the Domain Model[3]
 as one of the artifacts that may be created in the Business
Modeling discipline. More precisely, the UP Domain Model is a specialization of the UP Business
Object Model (BOM) "focusing on explaining 'things' and products important to a business
domain" [RUP
]. That is, a Domain Model focuses on one domain, such as POS related things. The
more broad BOM, not covered in this introductory text and not something I encourage creating
(because it can lead to too much up-front modeling), is an expanded, often very large and difficult
to create, multi-domain model that covers the entire business and all its sub-domains.
[3] Capitalization of "Domain Model" or terms is used to emphasize it as an official model name defined in the UP, versus the
general well-known concept of "domain models."
Applying UML notation, a domain model is illustrated with a set of class diagrams in which no
operations (method signatures) are defined. It provides a conceptual perspective. It may show:
domain objects or conceptual classes
associations between conceptual classes
attributes of conceptual classes
Definition: Why Call a Domain Model a "Visual Dictionary"?
Please reflect on Figure 9.2
 for a moment. See how it visualizes and relates words or concepts in
the domain. It also shows an abstraction of the conceptual classes, because there are many other
things one could communicate about registers, sales, and so forth.
<<<PDF_PAGE 224>>>
The information it illustrates (using UML notation) could alternatively have been expressed in
plain text (in the UP Glossary). But it's easy to understand the terms and especially their
relationships in a visual language, since our brains are good at understanding visual elements and
line connections.
Therefore, the domain model is a visual dictionary of the noteworthy abstractions, domain
vocabulary, and information content of the domain.
Definition: Is a Domain Model a Picture of Software Business Objects?
A UP Domain Model, as shown in Figure 9.3
, is a visualization of things in a real-situation domain
of interest, not of software objects such as Java or C# classes, or software objects with
responsibilities (see Figure 9.4
). Therefore, the following elements are not suitable in a domain
model:
Software artifacts, such as a window or a database, unless the domain being modeled is of
software concepts, such as a model of graphical user interfaces.
Responsibilities or methods.[4]
[4] In object modeling, we usually speak of responsibilities related to software objects. And methods are purely a
software concept. But, the domain model describes real-situation concepts, not software objects. Considering object
responsibilities during design work is very important; it is just not part of this model.
Figure 9.3. A domain model shows real-situation conceptual classes,
not software classes.
Figure 9.4. A domain model does not show software artifacts or
classes.
<<<PDF_PAGE 225>>>
Definition: What are Two Traditional Meanings of "Domain Model"?
In the UP and thus this chapter, "Domain Model" is a conceptual perspective of objects in a real
situation of the world, not a software perspective. But the term is overloaded; it also has been
used (especially in the Smalltalk community where I did most of my early OO development work
in the 1980s) to mean "the domain layer of software objects." That is, the layer of software
objects below the presentation or UI layer that is composed of domain objectssoftware objects
that represent things in the problem domain space with related "business logic" or "domain logic"
methods. For example, a Board software class with a getSquare method.
Which definition is correct? Well, all of them! The term has long established uses in different
communities to mean different things.
I've seen lots of confusion generated by people using the term in different ways, without
explaining which meaning they intend, and without recognizing that others may be using it
differently.
In this book, I'll usually write domain layer to indicate the second software-oriented meaning of
domain model, as that's quite common.
Definition: What are Conceptual Classes?
The domain model illustrates conceptual classes or vocabulary in the domain. Informally, a
conceptual class is an idea, thing, or object. More formally, a conceptual class may be
considered in terms of its symbol, intension, and extension [MO95
] (see Figure 9.5
).
Symbol words or images representing a conceptual class.
Intension the definition of a conceptual class.
Extension the set of examples to which the conceptual class applies.
Figure 9.5. A conceptual class has a symbol, intension, and extension.
<<<PDF_PAGE 226>>>
[View full size image]
For example, consider the conceptual class for the event of a purchase transaction. I may choose
to name it by the (English) symbol Sale. The intension of a Sale may state that it "represents the
event of a purchase transaction, and has a date and time." The extension of Sale is all the
examples of sales; in other words, the set of all sale instances in the universe.
Definition: Are Domain and Data Models the Same Thing?
A domain model is not a data model (which by definition shows persistent data to be stored
somewhere), so do not exclude a class simply because the requirements don't indicate any
obvious need to remember information about it (a criterion common in data modeling for
relational database design, but not relevant to domain modeling) or because the conceptual class
has no attributes. For example, it's valid to have attributeless conceptual classes, or conceptual
classes that have a purely behavioral role in the domain instead of an information role.
 

<<<PDF_PAGE 227>>>
 
9.3. Motivation: Why Create a Domain Model?
I'll share a story that I've experienced many times in OO consulting and coaching. In the early
1990s I was working with a group developing a funeral services business system in Smalltalk, in
Vancouver (you should see the domain model!). Now, I knew almost nothing about this business,
so one reason to create a domain model was so that I could start to understand their key
concepts and vocabulary.
We also wanted to create a domain layer of Smalltalk objects representing business objects and
logic. So, we spent perhaps one hour sketching a UML-ish (actually OMT-ish, whose notation
inspired UML) domain model, not worrying about software, but simply identifying the key terms.
Then, those terms we sketched in the domain model, such as Service (like flowers in the funeral
room, or playing "You Can't Always Get What You Want"), were also used as the names of key
software classes in our domain layer implemented in Smalltalk.
domain layer
 p. 206
This similarity of naming between the domain model and the domain layer (a real "service" and a
Smalltalk Service) supported a lower gap between the software representation and our mental
model of the domain.
Motivation: Lower Representational Gap with OO Modeling
This is a key idea in OO: Use software class names in the domain layer inspired from names in
the domain model, with objects having domain-familiar information and responsibilities. Figure
9.6
 illustrates the idea. This supports a low representational gap between our mental and
software models. And that's not just a philosophical nicetyit has a practical time-and-money
impact. For example, here's a source-code payroll program written in 1953:
1000010101000111101010101010001010101010101111010101 …
Figure 9.6. Lower representational gap with OO modeling.
[View full size image]
<<<PDF_PAGE 228>>>
As computer science people, we know it runs, but the gap between this software representation
and our mental model of the payroll domain is huge; that profoundly affects comprehension (and
modification) of the software. OO modeling can lower that gap.
Of course, object technology is also of value because it can support the design of elegant, loosely
coupled systems that scale and extend easily, as will be explored in the remainder of the book. A
lowered representational gap is useful, but arguably secondary to the advantage objects have in
supporting ease of change and extension, and managing and hiding complexity.
 

<<<PDF_PAGE 229>>>
 
9.4. Guideline: How to Create a Domain Model?
Bounded by the current iteration requirements under design:
Find the conceptual classes (see a following guideline).1.
Draw them as classes in a UML class diagram.2.
Add associations
 and attributes
. See p. 149
 and p. 158
.3.
 

<<<PDF_PAGE 230>>>
 
9.5. Guideline: How to Find Conceptual Classes?
Since a domain model shows conceptual classes, a central question is: How do I find them?
What are Three Strategies to Find Conceptual Classes?
Reuse or modify existing models. This is the first, best, and usually easiest approach, and
where I will start if I can. There are published, well-crafted domain models and data models
(which can be modified into domain models) for many common domains, such as inventory,
finance, health, and so forth. Example books that I'll turn to include Analysis Patterns by
Martin Fowler, Data Model Patterns by David Hay, and the Data Model Resource Book
(volumes 1 and 2) by Len Silverston.
1.
Use a category list.2.
Identify noun phrases.3.
Reusing existing models is excellent, but outside our scope. The second method, using a category
list, is also useful.
Method 2: Use a Category List
We can kick-start the creation of a domain model by making a list of candidate conceptual
classes. Table 9.1
 contains many common categories that are usually worth considering, with an
emphasis on business information system needs. The guidelines also suggest some priorities in
the analysis. Examples are drawn from the 1) POS, 2) Monopoly, and 3) airline reservation
domains.
Table 9.1. Conceptual Class Category List.
Conceptual Class Category
Examples
business transactions
Guideline: These are critical (they involve money), so
start with transactions.
Sale, Payment
Reservation
transaction line items
Guideline: Transactions often come with related line
items, so consider these next.
SalesLineItem
<<<PDF_PAGE 231>>>
Conceptual Class Category
Examples
product or service related to a transaction or
transaction line item
Guideline: Transactions are for something (a product or
service). Consider these next.
Item
Flight, Seat, Meal
where is the transaction recorded?
Guideline: Important.
Register, Ledger
FlightManifest
roles of people or organizations related to the
transaction; actors in the use case
Guideline: We usually need to know about the parties
involved in a transaction.
Cashier, Customer, Store
MonopolyPlayer Passenger, Airline
place of transaction; place of service
Store
Airport, Plane, Seat
noteworthy events, often with a time or place we
need to remember
Sale, Payment MonopolyGame Flight
physical objects
Guideline: This is especially relevant when creating
device-control software, or simulations.
Item, Register Board, Piece, Die
Airplane
descriptions of things
Guideline: See p. 147
 for discussion.
ProductDescription
FlightDescription
catalogs
Guideline: Descriptions are often in a catalog.
ProductCatalog
FlightCatalog
containers of things (physical or information)
Store, Bin Board Airplane
things in a container
Item Square (in a Board) Passenger
other collaborating systems
CreditAuthorizationSystem
AirTrafficControl
records of finance, work, contracts, legal matters
Receipt, Ledger
MaintenanceLog
financial instruments
Cash, Check, LineOfCredit
TicketCredit
schedules, manuals, documents that are regularly
referred to in order to perform work
DailyPriceChangeList
RepairSchedule
Method 3: Finding Conceptual Classes with Noun Phrase
Identification
product or service related to a transaction or
transaction line item
Guideline: Transactions are for something (a product or
service). Consider these next.
Item
Flight, Seat, Meal
where is the transaction recorded?
Guideline: Important.
Register, Ledger
FlightManifest
roles of people or organizations related to the
transaction; actors in the use case
Guideline: We usually need to know about the parties
involved in a transaction.
Cashier, Customer, Store
MonopolyPlayer Passenger, Airline
place of transaction; place of service
Store
Airport, Plane, Seat
noteworthy events, often with a time or place we
need to remember
Sale, Payment MonopolyGame Flight
physical objects
Guideline: This is especially relevant when creating
device-control software, or simulations.
Item, Register Board, Piece, Die
Airplane
descriptions of things
Guideline: See p. 147
 for discussion.
ProductDescription
FlightDescription
catalogs
Guideline: Descriptions are often in a catalog.
ProductCatalog
FlightCatalog
containers of things (physical or information)
Store, Bin Board Airplane
things in a container
Item Square (in a Board) Passenger
other collaborating systems
CreditAuthorizationSystem
AirTrafficControl
records of finance, work, contracts, legal matters
Receipt, Ledger
MaintenanceLog
financial instruments
Cash, Check, LineOfCredit
TicketCredit
schedules, manuals, documents that are regularly
referred to in order to perform work
DailyPriceChangeList
RepairSchedule
Method 3: Finding Conceptual Classes with Noun Phrase
Identification
<<<PDF_PAGE 232>>>
Another useful technique (because of its simplicity) suggested in [Abbot83
] is linguistic
analysis: Identify the nouns and noun phrases in textual descriptions of a domain, and consider
them as candidate conceptual classes or attributes.[5]
[5] Linguistic analysis has become more sophisticated; it also goes by the name natural language modeling. See
[Moreno97
] for example.
Guideline
Care must be applied with this method; a mechanical noun-to-class mapping isn't
possible, and words in natural languages are ambiguous.
Nevertheless, linguistic analysis is another source of inspiration. The fully dressed use cases are
an excellent description to draw from for this analysis. For example, the current scenario of the
Process Sale use case can be used.
Main Success Scenario (or Basic Flow):
Customer arrives at a POS checkout with goods and/or services to purchase.1.
Cashier starts a new sale.2.
Cashier enters item identifier.3.
System records sale line item and presents item description, price, and running total.
Price calculated from a set of price rules.
4.
Cashier repeats steps 2-3 until indicates done.
System presents total with taxes calculated.5.
Cashier tells Customer the total, and asks for payment.6.
Customer pays and System handles payment.7.
System logs the completed sale and sends sale and payment information to the external
Accounting (for accounting and commissions) and Inventory systems (to update
inventory).
8.
System presents receipt.9.
Customer leaves with receipt and goods (if any).10.
Extensions (or Alternative Flows):
. . .
7a. Paying by cash:
<<<PDF_PAGE 233>>>
Cashier enters the cash amount tendered.1.
System presents the balance due, and releases the cash drawer.
Cashier deposits cash tendered and returns balance in cash to Customer.
System records the cash payment.
The domain model is a visualization of noteworthy domain concepts and vocabulary. Where are
those terms found? Some are in the use cases. Others are in other documents, or the minds of
experts. In any event, use cases are one rich source to mine for noun phrase identification.
Some of these noun phrases are candidate conceptual classes, some may refer to conceptual
classes that are ignored in this iteration (for example, "Accounting" and "commissions"), and
some may be simply attributes
 of conceptual classes. See p. 160
 for advice on distinguishing
between the two.
A weakness of this approach is the imprecision of natural language; different noun phrases may
represent the same conceptual class or attribute, among other ambiguities. Nevertheless, it is
recommended in combination with the Conceptual Class Category List technique.
 

<<<PDF_PAGE 234>>>
 
9.6. Example: Find and Draw Conceptual Classes
Case Study: POS Domain
From the category list and noun phrase analysis, a list is generated of candidate conceptual
classes for the domain. Since this is a business information system, I'll focus first on the category
list guidelines that emphasize business transactions and their relationship with other things. The
list is constrained to the requirements and simplifications currently under consideration for
iteration-1, the basic cash-only scenario of Process Sale.
iteration-1 requirements
 p. 124
Sale
Cashier
CashPayment
Customer
SalesLineItem
Store
Item
ProductDescription
Register
ProductCatalog
Ledger
 
There is no such thing as a "correct" list. It is a somewhat arbitrary collection of abstractions and
domain vocabulary that the modelers consider noteworthy. Nevertheless, by following the
identification strategies, different modelers will produce similar lists.
In practice, I don't create a text list first, but immediately draw a UML class diagram of the
conceptual classes as we uncover them. See Figure 9.7
.
Figure 9.7. Initial POS domain model.
<<<PDF_PAGE 235>>>
Adding the associations and attributes is covered in later sections.
Case Study: Monopoly Domain
From the Category List and noun phrase analysis, I generate a list of candidate conceptual classes
for the iteration-1 simplified scenario of Play a Monopoly Game (see Figure 9.8
). Since this is a
simulation, I emphasize the noteworthy tangible, physical objects in the domain.
Figure 9.8. Initial Monopoly domain model.
iteration-1 requirements
 p. 124
 

<<<PDF_PAGE 236>>>
 
9.7. Guideline: Agile ModelingSketching a Class
Diagram
Notice the sketching style in the UML class diagram of Figure 9.8
keeping the bottom and right
sides of the class boxes open. This makes it easier to grow the classes as we discover new
elements. And although I've grouped the class boxes for compactness in this book diagram, on a
whiteboard I'll spread them out.
 

<<<PDF_PAGE 237>>>
 
9.8. Guideline: Agile ModelingMaintain the Model in a
Tool?
It's normal to miss significant conceptual classes during early domain modeling, and to discover
them later during design sketching or programming. If you are taking an agile modeling
approach, the purpose of creating a domain model is to quickly understand and communicate a
rough approximation of the key concepts. Perfection is not the goal, and agile models are usually
discarded shortly after creation (although if you've used a whiteboard, I recommend taking a
digital snapshot). From this viewpoint, there is no motivation to maintain or update the model.
But that doesn't mean it's wrong to update the model.
If someone wants the model maintained and updated with new discoveries, that's a good reason
to redraw the whiteboard sketch within a UML CASE tool, or to originally do the drawing with a
tool and a computer projector (for others to see the diagram easily). But, ask yourself: Who is
going to use the updated model, and why? If there isn't a practical reason, don't bother. Often,
the evolving domain layer of the software hints at most of the noteworthy terms, and a long-life
OO analysis domain model doesn't add value.
 

<<<PDF_PAGE 238>>>
 
9.9. Guideline: Report ObjectsInclude 'Receipt' in the
Model?
Receipt is a noteworthy term in the POS domain. But perhaps it's only a report of a sale and
payment, and thus duplicate information. Should it be in the domain model?
Here are some factors to consider:
In general, showing a report of other information in a domain model is not useful since all its
information is derived or duplicated from other sources. This is a reason to exclude it.
On the other hand, it has a special role in terms of the business rules: It usually confers the
right to the bearer of the (paper) receipt to return bought items. This is a reason to show it
in the model.
Since item returns are not being considered in this iteration, Receipt will be excluded. During the
iteration that tackles the Handle Returns use case, we would be justified to include it.
 

<<<PDF_PAGE 239>>>
 
9.10. Guideline: Think Like a Mapmaker; Use Domain
Terms
The mapmaker strategy applies to both maps and domain models.
Guideline
Make a domain model in the spirit of how a cartographer or mapmaker works:
Use the existing names in the territory. For example, if developing a model for a
library, name the customer a "Borrower" or "Patron"the terms used by the
library staff.
Exclude irrelevant or out-of-scope features. For example, in the Monopoly
domain model for iteration-1, cards (such as the "Get out of Jail Free" card) are
not used, so don't show a Card in the model this iteration.
Do not add things that are not there.
The principle is similar to the Use the Domain Vocabulary strategy [Coad95
].
 

<<<PDF_PAGE 240>>>
 
9.11. Guideline: How to Model the Unreal World?
Some software systems are for domains that find very little analogy in natural or business
domains; software for telecommunications is an example. Yet it is still possible to create a domain
model in these domains. It requires a high degree of abstraction, stepping back from familiar non-
OO designs, and listening carefully to the core vocabulary and concepts that domain experts use.
For example, here are candidate conceptual classes related to the domain of a telecommunication
switch: Message, Connection, Port, Dialog, Route, Protocol.
 

<<<PDF_PAGE 241>>>
 
9.12. Guideline: A Common Mistake with Attributes vs.
Classes
Perhaps the most common mistake when creating a domain model is to represent something as
an attribute when it should have been a conceptual class. A rule of thumb to help prevent this
mistake is:
Guideline
If we do not think of some conceptual class X as a number or text in the real world, X
is probably a conceptual class, not an attribute.
As an example, should store be an attribute of Sale, or a separate conceptual class Store?
In the real world, a store is not considered a number or textthe term suggests a legal entity, an
organization, and something that occupies space. Therefore, Store should be a conceptual class.
As another example, consider the domain of airline reservations. Should destination be an
attribute of Flight, or a separate conceptual class Airport?
In the real world, a destination airport is not considered a number or textit is a massive thing that
occupies space. Therefore, Airport should be a concept.
 

<<<PDF_PAGE 242>>>
 
9.13. Guideline: When to Model with 'Description'
Classes?
A description class contains information that describes something else. For example, a
ProductDescription that records the price, picture, and text description of an Item. This was first
named the Item-Descriptor pattern in [Coad92
].
Motivation: Why Use 'Description' Classes?
The following discussion may at first seem related to a rare, highly specialized issue. However, it
turns out that the need for description classes is common in many domain models.
Assume the following:
An Item instance represents a physical item in a store; as such, it may even have a serial
number.
An Item has a description, price, and itemID, which are not recorded anywhere else.
Everyone working in the store has amnesia.
Every time a real physical item is sold, a corresponding software instance of Item is deleted
from "software land."
With these assumptions, what happens in the following scenario?
There is strong demand for the popular new vegetarian burgerObjectBurger. The store sells out,
implying that all Item instances of ObjectBurgers are deleted from computer memory.
Now, here is one problem: If someone asks, "How much do ObjectBurgers cost?", no one can
answer, because the memory of their price was attached to inventoried instances, which were
deleted as they were sold.
Here are some related problems: The model, if implemented in software similar to the domain
model, has duplicate data, is space-inefficient, and error-prone (due to replicated information)
because the description, price, and itemID are duplicated for every Item instance of the same
product.
The preceding problem illustrates the need for objects that are descriptions (sometimes called
specifications) of other things. To solve the Item problem, what is needed is a ProductDescription
class that records information about items. A ProductDescription does not represent an Item, it
represents a description of information about items. See Figure 9.9
.
Figure 9.9. Descriptions about other things. The * means a multiplicity
of "many." It indicates that one ProductDescription may describe
<<<PDF_PAGE 243>>>
many (*) Items.
A particular Item may have a serial number; it represents a physical instance. A
ProductDescription wouldn't have a serial number.
Switching from a conceptual to a software perspective, note that even if all inventoried items are
sold and their corresponding Item software instances are deleted, the ProductDescription still
remains.
The need for description classes is common in sales, product, and service domains. It is also
common in manufacturing, which requires a description of a manufactured thing that is distinct
from the thing itself.
Guideline: When Are Description Classes Useful?
Guideline
Add a description class (for example, ProductDescription) when:
There needs to be a description about an item or service, independent of the
current existence of any examples of those items or services.
Deleting instances of things they describe (for example, Item) results in a loss of
information that needs to be maintained, but was incorrectly associated with the
deleted thing.
It reduces redundant or duplicated information.
<<<PDF_PAGE 244>>>
Example: Descriptions in the Airline Domain
As another example, consider an airline company that suffers a fatal crash of one of its planes.
Assume that all the flights are cancelled for six months pending completion of an investigation.
Also assume that when flights are cancelled, their corresponding Flight software objects are
deleted from computer memory. Therefore, after the crash, all Flight software objects are
deleted.
If the only record of what airport a flight goes to is in the Flight software instances, which
represent specific flights for a particular date and time, then there is no longer a record of what
flight routes the airline has.
The problem can be solved, both from a purely conceptual perspective in a domain model and
from a software perspective in the software designs, with a FlightDescription that describes a
flight and its route, even when a particular flight is not scheduled (see Figure 9.10
).
Figure 9.10. Descriptions about other things.
Note that the prior example is about a service (a flight) rather than a good (such as a
veggieburger). Descriptions of services or service plans are commonly needed.
As another example, a mobile phone company sells packages such as "bronze," "gold," and so
<<<PDF_PAGE 245>>>
forth. It is necessary to have the concept of a description of the package (a kind of service plan
describing rates per minute, wireless Internet content, the cost, and so forth) separate from the
concept of an actual sold package (such as "gold package sold to Craig Larman on Jan. 1, 2047 at
$55 per month"). Marketing needs to define and record this service plan or
MobileCommunicationsPackageDescription before any are sold.
 

<<<PDF_PAGE 246>>>
 
9.14. Associations
It's useful to find and show associations that are needed to satisfy the information requirements
of the current scenarios under development, and which aid in understanding the domain.
An association
 is a relationship between classes (more precisely, instances of those classes) that
indicates some meaningful and interesting connection (see Figure 9.11
).
Figure 9.11. Associations.
In the UML, associations are defined as "the semantic relationship between two or more classifiers
that involve connections among their instances."
Guideline: When to Show an Association?
Associations worth noting usually imply knowledge of a relationship that needs to be preserved for
some durationit could be milliseconds or years, depending on context. In other words, between
what objects do we need some memory of a relationship?
For example, do we need to remember what SalesLineItem instances are associated with a Sale
instance? Definitely, otherwise it would not be possible to reconstruct a sale, print a receipt, or
calculate a sale total.
And we need to remember completed Sales in a Ledger, for accounting and legal purposes.
Because the domain model is a conceptual perspective, these statements about the need to
remember refer to a need in a real situation of the world, not a software need, although during
implementation many of the same needs will arise.
In the monopoly domain, we need to remember what Square a Piece (or Player) is onthe game
doesn't work if that isn't remembered. Likewise, we need to remember what Piece is owned by a
particular Player. We need to remember what Squares are part of a particular Board.
But on the other hand, there is no need to remember that the Die (or the plural, "dice") total
<<<PDF_PAGE 247>>>
indicates the Square to move to. It's true, but we don't need to have an ongoing memory of that
fact, after the move has been made. Likewise, a Cashier may look up ProductDescriptions, but
there is no need to remember the fact of a particular Cashier looking up particular
ProductDescriptions.
Guideline
Consider including the following associations in a domain model:
Associations for which knowledge of the relationship needs to be preserved for
some duration ("need-to-remember" associations).
Associations derived from the Common Associations List.
Guideline: Why Should We Avoid Adding Many Associations?
We need to avoid adding too many associations to a domain model. Digging back into our discrete
mathematics studies, you may recall that in a graph with n nodes, there can be (n·(n-1))/2
associations to other nodesa potentially very large number. A domain model with 20 classes could
have 190 associations lines! Many lines on the diagram will obscure it with "visual noise."
Therefore, be parsimonious about adding association lines. Use the criterion guidelines suggested
in this chapter, and focus on "need-to-remember" associations.
Perspectives: Will the Associations Be Implemented In Software?
During domain modeling, an association is not a statement about data flows, database foreign key
relationships, instance variables, or object connections in a software solution; it is a statement
that a relationship is meaningful in a purely conceptual perspectivein the real domain.
That said, many of these relationships will be implemented in software as paths of navigation and
visibility (both in the Design Model and Data Model). But the domain model is not a data model;
associations are added to highlight our rough understanding of noteworthy relationships, not to
document object or data structures.
Applying UML: Association Notation
An association is represented as a line between classes with a capitalized association name. See
Figure 9.12
.
Figure 9.12. The UML notation for associations.
<<<PDF_PAGE 248>>>
The ends of an association may contain a multiplicity expression indicating the numerical
relationship between instances of the classes.
The association is inherently bidirectional, meaning that from instances of either class, logical
traversal to the other is possible. This traversal is purely abstract; it is not a statement about
connections between software entities.
An optional "reading direction arrow" indicates the direction to read the association name; it does
not indicate direction of visibility or navigation. If the arrow is not present, the convention is to
read the association from left to right or top to bottom, although the UML does not make this a
rule (see Figure 9.12
).
Caution
The reading direction arrow has no meaning in terms of the model; it is only an aid to
the reader of the diagram.
Guideline: How to Name an Association in UML?
Guideline
Name an association based on a ClassName-VerbPhrase-ClassName format where the
verb phrase creates a sequence that is readable and meaningful.
<<<PDF_PAGE 249>>>
Simple association names such as "Has" or "Uses" are usually poor, as they seldom enhance our
understanding of the domain.
For example,
Sale Paid-by CashPayment
bad example (doesn't enhance meaning): Sale Uses CashPayment
Player Is-on Square
bad example (doesn't enhance meaning): Player Has Square
Association names should start with a capital letter, since an association represents a classifier of
links between instances; in the UML, classifiers should start with a capital letter. Two common and
equally legal formats for a compound association name are:
Records-current
RecordsCurrent
Applying UML: Roles
Each end of an association is called a role
. Roles may optionally have:
multiplicity expression
name
navigability
Multiplicity is examined next.
Applying UML: Multiplicity
Multiplicity
 defines how many instances of a class A can be associated with one instance of a
class B (see Figure 9.13
).
Figure 9.13. Multiplicity on an association.
<<<PDF_PAGE 250>>>
For example, a single instance of a Store can be associated with "many" (zero or more, indicated
by the *) Item instances.
Some examples of multiplicity expressions are shown in Figure 9.14
.
Figure 9.14. Multiplicity values.
The multiplicity value communicates how many instances can be validly associated with another,
at a particular moment, rather than over a span of time. For example, it is possible that a used
car could be repeatedly sold back to used car dealers over time. But at any particular moment,
the car is only Stocked-by one dealer. The car is not Stocked-by many dealers at any particularthe car is only Stocked-by one dealer. The car is not Stocked-by many dealers at any particular
moment. Similarly, in countries with monogamy laws, a person can be Married-to only one othermoment. Similarly, in countries with monogamy laws, a person can be Married-to only one other
person at any particular moment, even though over a span of time, that same person may be
married to many persons.married to many persons.
The multiplicity value is dependent on our interest as a modeler and software developer, because
<<<PDF_PAGE 251>>>
it communicates a domain constraint that will be (or could be) reflected in software. See Figure
9.15
 for an example and explanation.
Figure 9.15. Multiplicity is context dependent.
[View full size image]
Rumbaugh gives another example of Person and Company in the Works-for association
[Rumbaugh91
]. Indicating if a Person instance works for one or many Company instances is
dependent on the context of the model; the tax department is interested in many; a union
probably only one. The choice usually depends on why we are building the software.
Applying UML: Multiple Associations Between Two Classes
Two classes may have multiple associations between them in a UML class diagram; this is not
uncommon. There is no outstanding example in the POS or Monopoly case study, but an example
from the domain of the airline is the relationships between a Flight (or perhaps more precisely, a
FlightLeg) and an Airport (see Figure 9.16
); the flying-to and flying-from associations are
distinctly different relationships, which should be shown separately.
Figure 9.16. Multiple associations.
Guideline: How to Find Associations with a Common Associations
<<<PDF_PAGE 252>>>
List
Start the addition of associations by using the list in Table 9.2
. It contains common categories
that are worth considering, especially for business information systems. Examples are drawn from
the 1) POS, 2) Monopoly, and 3) airline reservation domains.
Table 9.2. Common Associations List.
Category
Examples
A is a transaction related to another
transaction B
CashPaymentSale
CancellationReservation
A is a line item of a transaction B
SalesLineItemSale
A is a product or service for a transaction
(or line item) B
ItemSalesLineItem (or Sale)
FlightReservation
A is a role related to a transaction B
CustomerPayment
PassengerTicket
A is a physical or logical part of B
DrawerRegister
SquareBoard
SeatAirplane
A is physically or logically contained in/on B
RegisterStore, ItemShelf
SquareBoard
PassengerAirplane
A is a description for B
ProductDescriptionItem
FlightDescriptionFlight
A is
known/logged/recorded/reported/captured
in B
SaleRegister
PieceSquare
ReservationFlightManifest
A is a member of B
CashierStore
PlayerMonopolyGame
PilotAirline
A is an organizational subunit of B
DepartmentStore
MaintenanceAirline
<<<PDF_PAGE 253>>>
Category
Examples
A uses or manages or owns B
CashierRegister
PlayerPiece
PilotAirplane
A is next to B
SalesLineItemSalesLineItem
SquareSquare
CityCity
 
A uses or manages or owns B
CashierRegister
PlayerPiece
PilotAirplane
A is next to B
SalesLineItemSalesLineItem
SquareSquare
CityCity
 

<<<PDF_PAGE 254>>>
 
9.15. Example: Associations in the Domain Models
Case Study: NextGen POS
The domain model in Figure 9.17
 shows a set of conceptual classes and associations that are
candidates for our POS domain model. The associations are primarily derived from the "need-to-
remember" criteria of this iteration requirements, and the Common Association List. Reading the
list and mapping the examples to the diagram should explain the choices. For example:
Transactions related to another transaction Sale Paid-by CashPayment.
Line items of a transaction Sale Contains SalesLineItem.
Product for a transaction (or line item) SalesLineItem Records-sale-of Item.
Figure 9.17. NextGen POS partial domain model.
[View full size image]

<<<PDF_PAGE 255>>>
Case Study: Monopoly
See Figure 9.18
. Again, the associations are primarily derived from the "need-to-remember"
criteria of this iteration requirements, and the Common Association List. For example:
A is contained in or on B Board Contains Square.
A owns B Players Owns Piece.
A is known in/on B Piece Is-on Square.
A is member of B Player Member-of (or Plays) MonopolyGame.
Figure 9.18. Monopoly partial domain model.
 

<<<PDF_PAGE 256>>>
 
9.16. Attributes
It is useful to identify those attributes of conceptual classes that are needed to satisfy the
information requirements of the current scenarios under development. An attribute
 is a logical
data value of an object.
Guideline: When to Show Attributes?
Include attributes that the requirements (for example, use cases) suggest or imply a need to
remember information.
For example, a receipt (which reports the information of a sale) in the Process Sale use case
normally includes a date and time, the store name and address, and the cashier ID, among many
other things.
Therefore,
Sale needs a dateTime attribute.
Store needs a name and address.
Cashier needs an ID.
Applying UML: Attribute Notation
Attributes are shown in the second compartment of the class box (see Figure 9.19
). Their type
and other information may optionally be shown.
Figure 9.19. Class and attributes.
More Notation
<<<PDF_PAGE 257>>>
The full syntax for an attribute in the UML is:
visibility name : type multiplicity = default {property-string}
detailed UML class diagram
 notation p. 249
, and also on the back inside cover of the
book
Some common examples are shown in Figure 9.20
.
Figure 9.20. Attribute notation in UML.
[View full size image]
As a convention, most modelers will assume attributes have private visibility (-) unless shown
otherwise, so I don't usually draw an explicit visibility symbol.
{readOnly} is probably the most common property string for attributes.
Multiplicity can be used to indicate the optional presence of a value, or the number of objects that
can fill a (collection) attribute. For example, many domains require that a first and last name be
known for a person, but that a middle name is optional. The expression middleName : [0..1]
indicates an optional value0 or 1 values are present.
Guideline: Where to Record Attribute Requirements?
Notice that, subtly, middleName : [0..1] is a requirement or domain rule, embedded in the
domain model. Although this is just a conceptual-perspective domain model, it probably implies
that the software perspective should allow a missing value for middleName in the UI, the objects,
and the database. Some modellers accept leaving such specifications only in the domain model,
but I find this error-prone and scattered, as people tend to not look at the domain model in detail,
or for requirements guidance. Nor do they usually maintain the domain model.
Instead, I suggest placing all such attribute requirements in the UP Glossary, which serves as a
data dictionary. Perhaps I've spent an hour sketching a domain model with a domain expert;
afterwards, I can spend 15 minutes looking through it and transferring implied attribute
requirements into the Glossary.
Another alternative is to use a tool that integrates UML models with a data dictionary; then all
<<<PDF_PAGE 258>>>
attributes will automatically show up as dictionary elements.
Derived Attributes
The total attribute in the Sale can be calculated or derived from the information in the
SalesLineItems. When we want to communicate that 1) this is a noteworthy attribute, but 2) it is
derivable, we use the UML convention: a / symbol before the attribute name.
As another example, a cashier can receive a group of like items (for example, six tofu packages),
enter the itemID once, and then enter a quantity (for example, six). Consequently, an individual
SalesLineItem can be associated with more than one instance of an item.
The quantity that is entered by the cashier may be recorded as an attribute of the SalesLineItem
(Figure 9.21
). However, the quantity can be calculated from the actual multiplicity value of the
association, so it may be characterized as a derived attributeone that may be derived from other
information.
Figure 9.21. Recording the quantity of items sold in a line item.
[View full size image]
Guideline: What are Suitable Attribute Types?
Focus on Data Type Attributes in the Domain Model
Informally, most attribute types should be what are often thought of as "primitive" data types,
such as numbers and booleans. The type of an attribute should not normally be a complex
domain concept, such as a Sale or Airport.
For example, the currentRegister attribute in the Cashier class in Figure 9.22
 is undesirable
because its type is meant to be a Register, which is not a simple data type (such as Number or
String). The most useful way to express that a Cashier uses a Register is with an association, not
<<<PDF_PAGE 259>>>
with an attribute.
Figure 9.22. Relate with associations, not attributes.
Guideline
The attributes in a domain model should preferably be data types. Very common
data types include: Boolean, Date (or DateTime), Number, Character, String (Text),
Time.
Other common types include: Address, Color, Geometrics (Point, Rectangle), Phone
Number, Social Security Number, Universal Product Code (UPC), SKU, ZIP or postal
codes, enumerated types
To repeat an earlier example, a common confusion is modeling a complex domain concept as an
attribute. To illustrate, a destination airport is not really a string; it is a complex thing that
occupies many square kilometers of space. Therefore, Flight should be related to Airport via an
association, not with an attribute, as shown in Figure 9.23
.
Figure 9.23. Don't show complex concepts as attributes; use
associations.

<<<PDF_PAGE 260>>>
Guideline
Relate conceptual classes with an association, not with an attribute.
Data Types
As said, attributes in the domain model should generally be data types; informally these are
"primitive" types such as number, boolean, character, string, and enumerations (such as Size =
{small, large}). More precisely, this is a UML term that implies a set of values for which unique
identity is not meaningful (in the context of our model or system) [RJB99
]. Said another way,
equality tests are not based on identity, but instead on value.[6]
 For example, it is not (usually)
meaningful to distinguish between:
[6] In Java, for example, a value test is done with the equals method, and an identity test with the == operator.
Separate instances of the Integer 5.
Separate instances of the String 'cat'.
Separate instance of the Date "Nov. 13, 1990".
By contrast, it is meaningful to distinguish (by object identity) between two separate Person
instances whose names are both "Jill Smith" because the two instances can represent separate
individuals with the same name.
Also, data type values are usually immutable. For example, the instance '5' of Integer is
immutable; the instance "Nov. 13, 1990" of Date is probably immutable. On the other hand, a
Person instance may have its lastName changed for various reasons.
From a software perspective, there are few situations where one would compare the memory
addresses (identity) of instances of Integer or Date; only value-based comparisons are relevant.
On the other hand, the memory addresses of Person instances could conceivably be compared
and distinguished, even if they had the same attribute values, because their unique identity is
important.
Some OO and UML modeling books also speak of value objects, which are very similar to data
types, but with minor variations. However, I found the distinctions rather fuzzy and subtle, and
don't stress it.
Perspectives: What About Attributes in Code?
The recommendation that attributes in the domain model be mainly data types does not imply
that C# or Java attributes must only be of simple, primitive data types. The domain model is a
conceptual perspective, not a software one. In the Design Model, attributes may be of any type.
Guideline: When to Define New Data Type Classes?
<<<PDF_PAGE 261>>>
In the NextGen POS system an itemID attribute is needed; it is probably an attribute of an Item
or ProductDescription. Casually, it seems like just a number or perhaps a string. For example,
itemID : Integer or itemID : String.
But it is more than that (item identifiers have subparts), and in fact it is useful to have a class
named ItemID (or ItemIdentifier) in the domain model, and designate the type of the attribute as
such. For example, itemID : ItemIdentifier.
Table 9.3
 provides guidelines when it's useful to model with data types.
Table 9.3. Guidelines for modeling data types.
Guideline
Represent what may initially be considered a number or string as a new data type class in the
domain model if:
It is composed of separate sections.
phone number, name of person
There are operations associated with it, such as parsing or validation.
social security number
It has other attributes.
promotional price could have a start (effective) date and end date
It is a quantity with a unit.
payment amount has a unit of currency
It is an abstraction of one or more types with some of these qualities.
item identifier in the sales domain is a generalization of types such as Universal
Product Code (UPC) and European Article Number (EAN)
Applying these guidelines to the POS domain model attributes yields the following analysis:
The item identifier is an abstraction of various common coding schemes, including UPC-A,
UPC-E, and the family of EAN schemes. These numeric coding schemes have subparts
identifying the manufacturer, product, country (for EAN), and a check-sum digit for
validation. Therefore, there should be a data type ItemID class, because it satisfies many of
the guidelines above.
The price and amount attributes should be a data type Money class because they are
quantities in a unit of currency.
<<<PDF_PAGE 262>>>
The address attribute should be a data type Address class because it has separate sections.
Applying UML: Where to Illustrate These Data Type Classes?
Should the ItemID class be shown as a separate class in a domain model? It depends on what you
want to emphasize in the diagram. Since ItemID is a data type (unique identity of instances is
not used for equality testing), it may be shown only in the attribute compartment of the class
box, as shown in Figure 9.24
. On the other hand, if ItemID is a new type with its own attributes
and associations, showing it as a conceptual class in its own box may be informative. There is no
correct answer; resolution depends on how the domain model is being used as a tool of
communication, and the significance of the concept in the domain.
Figure 9.24. Two ways to indicate a data type property of an object.
[View full size image]
Guideline: No Attributes Representing Foreign Keys
Attributes should not be used to relate conceptual classes in the domain model. The most
common violation of this principle is to add a kind of foreign key attribute, as is typically done
in relational database designs, in order to associate two types. For example, in Figure 9.25
 the
currentRegisterNumber attribute in the Cashier class is undesirable because its purpose is to
relate the Cashier to a Register object. The better way to express that a Cashier uses a Register
is with an association, not with a foreign key attribute. Once again, relate types with an
association, not with an attribute.
Figure 9.25. Do not use attributes as foreign keys.
[View full size image]
<<<PDF_PAGE 263>>>
There are many ways to relate objectsforeign keys being oneand we will defer how to implement
the relation until design to avoid design creep.
Guideline: Modeling Quantities and Units
Most numeric quantities should not be represented as plain numbers. Consider price or weight.
Saying "the price was 13" or "the weight was 37" doesn't say much. Euros? Kilograms?
These are quantities with associated units, and it is common to require knowledge of the unit to
support conversions. The NextGen POS software is for an international market and needs to
support prices in multiple currencies. The domain model (and the software) should model
quantities skillfully.
In the general case, the solution is to represent Quantity as a distinct class, with an associated
Unit [Fowler96
]. It is also common to show Quantity specializations. Money is a kind of quantity
whose units are currencies. Weight is a quantity with units such as kilograms or pounds. See
Figure 9.26
.
Figure 9.26. Modeling quantities.
[View full size image]
 

<<<PDF_PAGE 264>>>
 
9.17. Example: Attributes in the Domain Models
Case Study: NextGen POS
See Figure 9.27
. The attributes chosen reflect the information requirements for this iterationthe
Process Sale cash-only scenarios of this iteration. For example:
CashPayment
amountTendered To determine if sufficient payment was provided,
and to calculate change, an amount (also known as "amount
tendered") must be captured.
Product-Description
description To show the description on a display or receipt.
itemId To look up a ProductDescription.
price To calculate the sales total, and show the line item price.
Sale
dateTime A receipt normally shows date and time of sale, and this
is useful for sales analysis.
SalesLineItem
quantity To record the quantity entered, when there is more than
one item in a line item sale (for example, five packages of tofu).
Store
address, name The receipt requires the name and address of the
store.
Figure 9.27. NextGen POS partial domain model.
[View full size image]
<<<PDF_PAGE 265>>>
Case Study: Monopoly
See Figure 9.28
. The attributes chosen reflect the information requirements for this iterationthe
simplified Play Monopoly Game scenario of this iteration. For example:
Die
faceValue After rolling the dice, needed to
calculate the distance of a move.
Square
name To print the desired trace output.
Figure 9.28. Monopoly partial domain model.
<<<PDF_PAGE 266>>>
 

<<<PDF_PAGE 267>>>
 
9.18. Conclusion: Is the Domain Model Correct?
There is no such thing as a single correct domain model. All models are approximations of the
domain we are attempting to understand; the domain model is primarily a tool of understanding
and communication among a particular group. A useful domain model captures the essential
abstractions and information required to understand the domain in the context of the current
requirements, and aids people in understanding the domainits concepts, terminology, and
relationships.
 

<<<PDF_PAGE 268>>>
 
9.19. Process: Iterative and Evolutionary Domain
Modeling
Although paradoxically a significant number of pages were devoted to explaining domain
modeling, in experienced hands the development of a (partial, evolutionary) model in each
iteration may take only 30 minutes. This is further shortened by the use of predefined analysis
patterns.
In iterative development, we incrementally evolve a domain model over several iterations. In
each, the domain model is limited to the prior and current scenarios under consideration, rather
than expanding to a "big bang" waterfall-style model that early on attempts to capture all possible
conceptual classes and relationships. For example, this POS iteration is limited to a simplified
cash-only Process Sale scenario; therefore, a partial domain model will be created to reflect just
thatnot more.
And to reiterate advice from the start of this chapter:
Guideline
Avoid a waterfall-mindset big-modeling effort to make a thorough or "correct" domain
modelit won't ever be either, and such over-modeling efforts lead to analysis
paralysis, with little or no return on the investment.
Limit domain modeling to no more than a few hours per iteration.
Domain Models Within the UP
As suggested in the example of Table 9.4
, the UP Domain Model is usually both started and
completed in the elaboration phase.
Table 9.4. Sample UP artifacts and timing. s - start; r -
refine
Discipline
Artifact
Incep.
Elab.
Const.
Trans.
Iteration
I1
E1..En
C1..Cn
T1..T2
Business Modeling
Domain Model
 
s
 
 
Requirements
Use-Case Model (SSDs)
s
r
 
 
Vision
s
r
 
 
<<<PDF_PAGE 269>>>
Discipline
Artifact
Incep.
Elab.
Const.
Trans.
Iteration
I1
E1..En
C1..Cn
T1..T2
Supplementary
Specification
s
r
 
 
Glossary
s
r
 
 
Design
Design Model
 
s
r
 
SW Architecture Document
 
s
 
 
Data Model
 
s
r
 
elaboration phase
 p. 33
Inception
Domain models are not strongly motivated in inception, since inception's purpose is not to do a
serious investigation, but rather to decide if the project is worth deeper investigation in an
elaboration phase.
Elaboration
The Domain Model is primarily created during elaboration iterations, when the need is highest to
understand the noteworthy concepts and map some to software classes during design work.
The UP Business Object Model vs. Domain Model
The UP Domain Model is an official variation of the less common UP Business Object Model (BOM).
The UP BOMnot to be confused with the many other definitions of a BOMis a kind of enterprise
model that describes the entire business. It may be used when doing business process
engineering or reengineering, independent of any one software application (such as the NextGen
POS). To quote:
[The UP BOM] serves as an abstraction of how business workers and business entities need
to be related and how they need to collaborate in order to perform the business. [RUP
]
The BOM is represented with several different diagrams (class, activity, and sequence) that
illustrate how the entire enterprise runs (or should run). It is most useful if doing enterprise-wide
business process engineering, but that is a less common activity than creating a single software
application.
Consequently, the UP defines the Domain Model as the more commonly created subset artifact or
specialization of the BOM. To quote:
You can choose to develop an "incomplete" business object model, focusing on explaining
"things" and products important to a domain. […] This is often referred to as a domain
Supplementary
Specification
s
r
 
 
Glossary
s
r
 
 
Design
Design Model
 
s
r
 
SW Architecture Document
 
s
 
 
Data Model
 
s
r
 
elaboration phase
 p. 33
Inception
Domain models are not strongly motivated in inception, since inception's purpose is not to do a
serious investigation, but rather to decide if the project is worth deeper investigation in an
elaboration phase.
Elaboration
The Domain Model is primarily created during elaboration iterations, when the need is highest to
understand the noteworthy concepts and map some to software classes during design work.
The UP Business Object Model vs. Domain Model
The UP Domain Model is an official variation of the less common UP Business Object Model (BOM).
The UP BOMnot to be confused with the many other definitions of a BOMis a kind of enterprise
model that describes the entire business. It may be used when doing business process
engineering or reengineering, independent of any one software application (such as the NextGen
POS). To quote:
[The UP BOM] serves as an abstraction of how business workers and business entities need
to be related and how they need to collaborate in order to perform the business. [RUP
]
The BOM is represented with several different diagrams (class, activity, and sequence) that
illustrate how the entire enterprise runs (or should run). It is most useful if doing enterprise-wide
business process engineering, but that is a less common activity than creating a single software
application.
Consequently, the UP defines the Domain Model as the more commonly created subset artifact or
specialization of the BOM. To quote:
You can choose to develop an "incomplete" business object model, focusing on explaining
"things" and products important to a domain. […] This is often referred to as a domain
<<<PDF_PAGE 270>>>
model. [RUP
]
 

<<<PDF_PAGE 271>>>
 
9.20. Recommended Resources
Odell's Object-Oriented Methods: A Foundation provides a solid introduction to conceptual domain
modeling. Cook and Daniel's Designing Object Systems is also useful.
Fowler's Analysis Patterns offers worthwhile patterns in domain models and is definitely
recommended. Another good book that describes patterns in domain models is Hay's Data Model
Patterns: Conventions of Thought. Advice from data modeling experts who understand the
distinction between pure conceptual models and database schema models can be very useful for
domain object modeling.
Java Modeling in Color with UML [CDL99
] has much more relevant domain modeling advice than
the title suggests. The authors identify common patterns in related types and their associations;
the color aspect is really a visualization of the common categories of these types, such as
descriptions (blue), roles (yellow), and moment-intervals (pink). Color is used to aid in seeing the
patterns.
 

# Chapter 12. Requirements to DesignIteratively


<<<PDF_PAGE 308>>>
 
Chapter 12. Requirements to
DesignIteratively
Hardware, n.: The parts of a computer system that can be kicked.
anonymous
Objectives
Quickly motivate the transition to design activities.
Contrast the importance of object design skill versus UML notation knowledge.
 

<<<PDF_PAGE 309>>>
 
Introduction
So far, the case studies have emphasized analysis of the requirements and objects. If following
the UP guidelines, perhaps 10% of the requirements were investigated in inception, and a slightly
deeper investigation was started in this first iteration of elaboration. The following chapters are a
shift in emphasis toward designing a solution for this iteration in terms of collaborating software
objects.
[View full size image]
 
 

<<<PDF_PAGE 310>>>
 
12.1. Iteratively Do the Right Thing, Do the Thing Right
The requirements and object-oriented analysis has focused on learning to do the right thing; that
is, understanding some of the outstanding goals for the case studies, and related rules and
constraints. By contrast, the following design work will stress do the thing right; that is, skillfully
designing a solution to satisfy the requirements for this iteration.
In iterative development, a transition from primarily a requirements or analysis focus to primarily
a design and implementation focus will occur in each iteration. Early iterations will spend relatively
more time on analysis activities. As the vision and specifications start to stabilize based on early
programming, test, and feedback, in later iterations it is common that analysis lessens; there's
more focus on just building the solution.
 

<<<PDF_PAGE 311>>>
 
12.2. Provoking Early Change
It is natural and healthy to discover and change some requirements during the design and
implementation work, especially in the early iterations. Iterative and evolutionary methods
"embrace change"although we try to provoke that inevitable change in early iterations, so that we
have a more stable goal (and estimate and schedule) for the later iterations. Early programming,
tests, and demos help provoke the inevitable changes early on. Take note! This simple idea lies at
the heart of why iterative development works.
The discovery of changing specifications will both clarify the purpose of the design work of this
iteration and refine the requirements understanding for future iterations. Over the course of these
early elaboration iterations, the requirements discovery should stabilize, so that by the end of
elaboration, perhaps 80% of the requirements are reliably defineddefined and refined as a result
of feedback, early programming and testing, rather than speculation, as occurs in a waterfall
method.
 

<<<PDF_PAGE 312>>>
 
12.3. Didn't All That Analysis and Modeling Take Weeks
To Do?
After many chapters of detailed discussion, it must surely seem like the prior modeling would take
weeks of effort. Not so!
When one is comfortable with the skills of use case writing, domain modeling, and so forth, the
duration to do all the actual modeling that has been explored so far is realistically just a few hours
or days.
However, that does not mean that only a few days have passed since the start of the project.
Many other activities, such as proof-of-concept programming, finding resources (people, software,
…), planning, setting up the environment, and so on, could consume a few weeks of preparation.
 

# Chapter 17. GRASP: Designing Objects with Responsibilities


<<<PDF_PAGE 409>>>
 
Chapter 17. GRASP: Designing Objects
with Responsibilities
Understanding responsibilities is key to good object-oriented design.
Martin Fowler
Objectives
Learn to apply five of the GRASP principles or patterns for OOD.
This chapter and the next contribute significantly to an understanding of core OO design (OOD).
OOD is sometimes taught as some variation of the following:
After identifying your requirements and creating a domain model, then add methods to the
appropriate classes, and define the messaging between the objects to fulfill the
requirements.
Ouch! Such vague advice doesn't help us, because deep principles and issues are involved.
Deciding what methods belong where and how objects should interact carries consequences and
should be undertaken seriously. Mastering OODand this is its intricate charminvolves a large set
of soft principles, with many degrees of freedom. It isn't magicthe patterns can be named
(important!), explained, and applied. Examples help. Practice helps. And this small step helps:
After studying these case studies, try recreating (from memory) the Monopoly solution on walls
with partners, and apply the principles, such as Information Expert.
[View full size image]
 

<<<PDF_PAGE 410>>>
 
17.1. UML versus Design Principles
Since the UML is simply a standard visual modeling language, knowing its details doesn't teach
you how to think in objectsthat's a theme of this book. The UML is sometimes described as a
"design tool" but that's not quite right…
UML and silver bullet thinking
 p. 12
The critical design tool for software development is a mind well educated in design
principles. It is not the UML or any other technology.
 

<<<PDF_PAGE 411>>>
 
17.2. Object Design: Example Inputs, Activities, and
Outputs
This section summarizes a big-picture example of design in an iterative method:
What's been done? Prior activities (e.g., workshop) and artifacts.
How do things relate? Influence of prior artifacts (e.g., use cases) on OO design.
How much design modeling to do, and how?
What's the output?
Especially, I'd like you to understand how the analysis artifacts relate to object design.
What Are Inputs to Object Design?
Let's start with "process" inputs. Assume we are developers working on the POS NextGen project,
and the following scenario is true:
The first two-day requirements workshop is
finished.
The chief architect and business agree to
implement and test some scenarios of
Process Sale in the first three-week
timeboxed iteration.
Three of the twenty use casesthose that are
the most architecturally significant and of high
business valuehave been analyzed in detail,
including, of course, the Process Sale use case.
(The UP recommends, as typical with iterative
methods, analyzing only 10%20% of the
requirements in detail before starting to
program.)
Other artifacts have been started:
Supplementary Specification, Glossary, and
Domain Model.
Programming experiments have resolved the
show-stopper technical questions, such as
whether a Java Swing UI will work on a touch
screen.
The chief architect has drawn some ideas for
the large-scale logical architecture, using
UML package diagrams. This is part of the UP
Design Model.
What are the artifact inputs and their relationship to object design?[1]
 They are summarized in
Figure 17.1
 and in the following table.
[1] Other artifact inputs could include design documents for an existing system being modified. It's also useful to reverse-
engineer existing code into UML package diagrams to see the large-scale logical structure and some class and sequence
diagrams.
<<<PDF_PAGE 412>>>
Figure 17.1. Artifact relationships emphasizing influence on OO design.
[View full size image]

<<<PDF_PAGE 413>>>
The use case text defines the visible behavior
that the software objects must ultimately
supportobjects are designed to "realize"
(implement) the use cases. In the UP, this OO
design is called, not surprisingly, the use case
realization.
The Supplementary Specification defines
the non-functional goals, such as
internalization, our objects must satisfy.
The system sequence diagrams identify the
system operation messages, which are the
starting messages on our interaction diagrams
of collaborating objects.
The Glossary clarifies details of parameters or
data coming in from the UI layer, data being
passed to the database, and detailed item-
specific logic or validation requirements, such
as the legal formats and validation for product
UPCs (universal product codes).
The operation contracts may complement
the use case text to clarify what the software
objects must achieve in a system operation.
The post-conditions define detailed
achievements.
The Domain Model suggests some names and
attributes of software domain objects in the
domain layer of the software architecture.
Not all of these artifacts are necessary. Recall that in the UP all elements are optional, possibly
created to reduce some risk.
What Are Activities of Object Design?
We're ready to take off our analyst hats and put on our designer-modeler hats.
Given one or more of these inputs, developers 1) start immediately coding (ideally with test-first
development), 2) start some UML modeling for the object design, or 3) start with another
modeling technique, such as CRC cards.[2]
[2] All of these approaches are skillful depending on context and person.
test first
 p. 386
In the UML case, the real point is not the UML, but visual modelingusing a language that allows us
to explore more visually than we can with just raw text. In this case, for example, we draw both
interaction diagrams and complementary class diagrams (dynamic and static modeling) during
one modeling day. And most importantly, during the drawing (and coding) activity we apply
various OO design principles, such as GRASP and the Gang-of-Four (GoF) design patterns.
The overall approach to doing the OO design modeling will be based on the metaphor of
responsibility-driven design (RDD), thinking about how to assign responsibilities to
collaborating objects.
GRASP
 p. 277
<<<PDF_PAGE 414>>>
GoF p. 435
RDD p. 276
This and subsequent chapters explore what it means to apply RDD, GRASP, and some
of the GoF design patterns.
On the modeling day, perhaps the team works in small groups for 26 hours either at the walls or
with software modeling tools, doing different kinds of modeling for the difficult, creative parts of
the design. This could include UI, OO, and database modeling with UML drawings, prototyping
tools, sketches, and so forth.
During UML drawing, we adopt the realistic attitude (also promoted in agile modeling) that we are
drawing the models primarily to understand and communicate, not to document. Of course, we
expect some of the UML diagrams to be useful input to the definition (or automated code
generation with a UML tool) of the code.
On Tuesdaystill early in the three-week timeboxed iterationthe team stops modeling and puts on
programmer hats to avoid a waterfall mentality of over-modeling before programming.
What Are the Outputs?
Figure 17.1
 illustrates some inputs and their relationship to the output of a UML interaction and
class diagram. Notice that we may refer to these analysis inputs during design; for example, re-
reading the use case text or operation contracts, scanning the domain model, and reviewing the
Supplementary Specification.
What's been created during the modeling day (for example)?
specifically for object design, UML interaction, class, and package diagrams for the difficult
parts of the design that we wished to explore before coding
UI sketches and prototypes
database models (with UML data modeling profile
 notation p. 629
)
report sketches and prototypes
<<<PDF_PAGE 415>>>
 

<<<PDF_PAGE 416>>>
 
17.3. Responsibilities and Responsibility-Driven Design
A popular way of thinking about the design of software objects and also larger-scale
components[3]
 is in terms of responsibilities
, roles
, and collaborations
. This is part of a
larger approach called responsibility-driven design or RDD [WM02
].
[3] Thinking in terms of responsibilities can apply at any scale of softwarefrom a small object to a system of systems.
In RDD, we think of software objects as having responsibilitiesan abstraction of what they do. The
UML defines a responsibility
 as "a contract or obligation of a classifier" [OMG03b
].
Responsibilities are related to the obligations or behavior of an object in terms of its role.
Basically, these responsibilities are of the following two types: doing and knowing.
Doing responsibilities of an object include:
doing something itself, such as creating an object or doing a calculation
initiating action in other objects
controlling and coordinating activities in other objects
Knowing responsibilities of an object include:
knowing about private encapsulated data
knowing about related objects
knowing about things it can derive or calculate
Responsibilities are assigned to classes of objects during object design. For example, I may
declare that "a Sale is responsible for creating SalesLineItems" (a doing), or "a Sale is responsible
for knowing its total" (a knowing).
Guideline: For software domain objects, the domain model, because of the attributes and
associations it illustrates, often inspires the relevant responsibilities related to "knowing." For
example, if the domain model Sale class has a time attribute, it's natural by the goal of low
representational gap that a software Sale class knows its time.
low representational gap
 p. 138
The translation of responsibilities into classes and methods is influenced by the granularity of the
responsibility. Big responsibilities take hundreds of classes and methods. Little responsibilities
might take one method. For example, the responsibility to "provide access to relational
databases" may involve two hundred classes and thousands of methods, packaged in a
subsystem. By contrast, the responsibility to "create a Sale" may involve only one method in one
<<<PDF_PAGE 417>>>
class.
A responsibility is not the same thing as a methodit's an abstractionbut methods fulfill
responsibilities.
RDD also includes the idea of collaboration
. Responsibilities are implemented by means of
methods that either act alone or collaborate with other methods and objects. For example, the
Sale class might define one or more methods to know its total; say, a method named getTotal. To
fulfill that responsibility, the Sale may collaborate with other objects, such as sending a
getSubtotal message to each SalesLineItem object asking for its subtotal.
RDD is a Metaphor
RDD is a general metaphor for thinking about OO software design. Think of software
objects as similar to people with responsibilities who collaborate with other people to
get work done. RDD leads to viewing an OO design as a community of collaborating
responsible objects.
Key point: GRASP names and describes some basic principles to assign responsibilities, so it's
useful to knowto support RDD.
 

<<<PDF_PAGE 418>>>
 
17.4. GRASP: A Methodical Approach to Basic OO
Design
GRASP: A Learning Aid for OO Design with Responsibilities
It is possible to name and explain the detailed principles and reasoning required to grasp basic
object design, assigning responsibilities to objects. The GRASP principles or patterns are a
learning aid to help you understand essential object design and apply design reasoning in a
methodical, rational, explainable way. This approach to understanding and using design principles
is based on patterns of assigning responsibilities.
This chapterand several othersuses GRASP as a tool to help master the basics of OOD and
understanding responsibility assignment in object design.
Understanding how to apply GRASP for object design is a key goal of the book.
So, GRASP is relevant, but on the other hand, it's just a learning aid to structure and name the
principlesonce you "grasp" the fundamentals, the specific GRASP terms (Information Expert,
Creator, …) aren't important.
 

<<<PDF_PAGE 419>>>
 
17.5. What's the Connection Between Responsibilities,
GRASP, and UML Diagrams?
You can think about assigning responsibilities to objects while coding or while modeling. Within
the UML, drawing interaction diagrams becomes the occasion for considering these responsibilities
(realized as methods).
Figure 17.2
 indicates that Sale objects have been given a responsibility to create Payments, which
is concretely invoked with a makePayment message and handled with a corresponding
makePayment method. Furthermore, the fulfillment of this responsibility requires collaboration to
create the Payment object and invoke its constructor.
Figure 17.2. Responsibilities and methods are related.
Therefore, when we draw a UML interaction diagram, we are deciding on responsibility
assignments. This chapter emphasizes fundamental principlesexpressed in GRASPto guide choices
about assigning responsibilities. Thus, you can apply the GRASP principles while drawing UML
interaction diagrams, and also while coding.
 

<<<PDF_PAGE 420>>>
 
17.6. What are Patterns?
Experienced OO developers (and other software developers) build up a repertoire of both general
principles and idiomatic solutions that guide them in the creation of software. These principles and
idioms, if codified in a structured format describing the problem and solution and named, may be
called patterns
. For example, here is a sample pattern:
Pattern Name:
Information Expert
Problem:
What is a basic principle by which to assign responsibilities to
objects?
Solution:
Assign a responsibility to the class that has the information
needed to fulfill it.
In OO design, a pattern
 is a named description of a problem and solution that can be applied to
new contexts; ideally, a pattern advises us on how to apply its solution in varying circumstances
and considers the forces and trade-offs. Many patterns, given a specific category of problem,
guide the assignment of responsibilities to objects.
Most simply, a good pattern
 is a named and well-known problem/solution pair that
can be applied in new contexts, with advice on how to apply it in novel situations and
discussion of its trade-offs, implementations, variations, and so forth.
Patterns Have NamesImportant!
Software development is a young field. Young fields lack well-established names for their
principlesand that makes communication and education difficult. Patterns have names, such as
Information Expert and Abstract Factory. Naming a pattern, design idea, or principle has the
following advantages:
It supports chunking and incorporating that concept into our understanding and memory.
It facilitates communication.
When a pattern is named and widely publishedand we all agree to use the namewe can discuss a
complex design idea in shorter sentences (or shorter diagrams), a virtue of abstraction. Consider
the following discussion between two software developers, using a vocabulary of pattern names:
Jill: "Hey Jack, for the persistence subsystem, let's expose the services with a Facade. We'll use
an Abstract Factory for Mappers, and Proxies for lazy materialization."
<<<PDF_PAGE 421>>>
Jack: "What the hell did you just say?!?"
Jill: "Here, read this…"
'New Pattern' is an Oxymoron
New pattern should be considered an oxymoron if it describes a new idea. The very term
"pattern" suggests a long-repeating thing. The point of design patterns is not to express new
design ideas. Quite the oppositegreat patterns attempt to codify existing tried-and-true
knowledge, idioms, and principles; the more honed, old, and widely used, the better.
Consequently, the GRASP patterns don't state new ideas; they name and codify widely used basic
principles. To an OO design expert, the GRASP patternsby idea if not by namewill appear
fundamental and familiar. That's the point!
The Gang-of-Four Design Patterns Book
The idea of named patterns in software comes from Kent Beck (also of Extreme Programming
fame) in the mid 1980s.[4]
 However, 1994 was a major milestone in the history of patterns, OO
design, and software design books: The massive-selling and hugely influential book Design
Patterns [GHJV95
][5]
 was published, authored by Gamma, Helm, Johnson, and Vlissides. The
book, considered the "Bible" of design pattern books, describes 23 patterns for OO design, with
names such as Strategy and Adapter. These 23 patterns, authored by four people, are therefore
called the Gang of Four[6]
 (or GoF) design patterns.
[4] The notion of patterns originated with the (building) architectural patterns of Christopher Alexander [AIS77
]. Patterns for
software originated in the 1980s with Kent Beck, who became aware of Alexander's pattern work in architecture, and then
were developed by Beck with Ward Cunningham [BC87
, Beck94
] at Tektronix.
[5] Publishers list the publication date as 1995, but it was released October 1994.
[6] Also a subtle joke related to mid-1970s Chinese politics following Mao's death.

<<<PDF_PAGE 422>>>
However, Design Patterns isn't an introductory book; it assumes significant prior OO design and
programming knowledge, and most code examples are in C++.
Laterintermediatechapters of this book, especially Chapter 26
 (p. 435
), Chapter 35
 (p. 579
), and
Chapter 38
 (p. 625
) introduce many of the most frequently used GoF design patterns and apply
them to our case studies. Also: See "Contents by Major Topics" on page ix.
It is a key goal of this text to learn both GRASP and essential GoF patterns.
Is GRASP a Set of Patterns or Principles?
GRASP defines nine basic OO design principles or basic building blocks in design. Some have
asked, "Doesn't GRASP describe principles rather than patterns?" One answer is in the words of
the Gang of Four authors, from the preface of their influential Design Patterns book:
One person's pattern is another person's primitive building block.
Rather than focusing on labels, this text focuses on the pragmatic value of using the pattern style
as an excellent learning aid for naming, presenting, and remembering basic, classic design ideas.
 

<<<PDF_PAGE 423>>>
 
17.7. Where are We Now?
So far, this chapter has summarized the background for OO design:
The iterative process backgroundPrior artifacts? How do they relate to OO design models?
How much time should we spend design modeling?
1.
RDD as a metaphor for object designa community of collaborating responsible objects.2.
Patterns as a way to name and explain OO design ideasGRASP for basic patterns of
assigning responsibilities, and GoF for more advanced design ideas. Patterns can be applied
during modeling and during coding.
3.
UML for OO design visual modeling, during which time both GRASP and GoF patterns can
be applied.
4.
With that understood, it's time to focus on some details of object design.
 

<<<PDF_PAGE 424>>>
 
17.8. A Short Example of Object Design with GRASP
Following sections explore GRASP in more detail, but let's start with a shorter example to see the
big ideas, applied to the Monopoly case study. There are nine GRASP patterns; this example
applies the following subset:
Creator
Information Expert
Low Coupling
Controller
High Cohesion
All the GRASP patterns are summarized on the inside front cover of this book.
Creator
Problem: Who creates the Square object?
One of the first problems you have to consider in OO design is: Who creates object X? This is a
doing responsibility. For example, in the Monopoly case study, who creates a Square software
object? Now, any object can create a Square, but what would many OO developers choose? And
why?
How about having a Dog object (i.e., some arbitrary class) be the creator? No! We can feel it in
our bones. Why? Becauseand this is the critical pointit doesn't appeal to our mental model of the
domain. Dog doesn't support low representational gap (LRG) between how we think of the
domain and a straightforward correspondence with software objects. I've done this problem with
literally thousands of developers, and virtually every one, from India to the USA, will say, "Make
the Board object create the Squares." Interesting! It reflects an "intuition" that OO software
developers often (exceptions are explored later) want "containers" to create the things
"contained," such as Boards creating Squares.
By the way, why we are defining software classes with the names Square and Board, rather than
the names AB324 and ZC17? Answer: By LRG. This connects the UP Domain Model to the UP
Design Model, or our mental model of the domain to its realization in the domain layer of the
software architecture.
With that as background, here's the definition of the Creator pattern[7]
:
[7] Alternate creation patterns, such as Concrete Factory and Abstract Factory, are discussed later.
<<<PDF_PAGE 425>>>
Name:
Creator
Problem:
Who creates an A?
Solution: (this
can be viewed as
advice)
Assign class B the responsibility to create an instance of class A if one of
these is true (the more the better):
B "contains" or compositely aggregates A.
B records A.
B closely uses A.
B has the initializing data for A.
Notice this has to do with responsibility assignment. Let's see how to apply Creator.
First, a subtle but important point in applying Creator and other GRASP patterns: B and A refer to
software objects, not domain model objects. We first try to apply Creator by looking for existing
software objects that satisfy the role of B. But what if we are just starting the OO design, and we
have not yet defined any software classes? In this case, by LRG, look to the domain model for
inspiration.
Thus, for the Square creation problem, since no software classes are yet defined, we look at the
domain model in Figure 17.3
 and see that a Board contains Squares. That's a conceptual
perspective, not a software one, but of course we can mirror it in the Design Model so that a
software Board object contains software Square objects. And then consistent with LRG and the
Creator advice, the Board will create Squares. Also, Squares will always be a part of one Board,
and Board manages their creation and destruction; thus, they are in a composite aggregation
association with the Board.
Figure 17.3. Monopoly iteration-1 domain model.

<<<PDF_PAGE 426>>>
Recall that an agile modeling practice is to create parallel complementary dynamic and static
object models. Therefore, I've drawn both a partial sequence diagram and class diagram to reflect
this design decision in which I've applied a GRASP pattern while drawing UML diagrams. See
Figure 17.4
 and Figure 17.5
. Notice in Figure 17.4
 that when the Board is created, it creates a
Square. For brevity in this example, I'll ignore the side issue of drawing the loop to create all 40
squares.
Figure 17.4. Applying the Creator pattern in a dynamic model.
Figure 17.5. In a DCD of the Design Model, Board has a composite
aggregation association with Squares. We are applying Creator in a
static model.
Information Expert
Problem: Who knows about a Square object, given a key?
The pattern Information Expert (often abbreviated to Expert) is one of the most basic
responsibility assignment principles in object design.
Suppose objects need to be able to reference a particular Square, given its name. Who should be
responsible for knowing a Square, given a key? Of course, this is a knowing responsibility, but
Expert also applies to doing.
<<<PDF_PAGE 427>>>
As with Creator, any object can be responsible, but what would many OO developers choose? And
why? As with the Creator problem, most OO developers choose the Board object. It seems sort of
trivially obvious to assign this responsibility to a Board, but it is instructive to deconstruct why,
and to learn to apply this principle in more subtle cases. Later examples will get more subtle.
Information Expert explains why the Board is chosen:
Name:
Information Expert
Problem:
What is a basic principle by which to assign responsibilities to objects?
Solution:
(advice)
Assign a responsibility to the class that has the information needed to fulfill it.
A responsibility needs information for its fulfillmentinformation about other objects, an object's
own state, the world around an object, information the object can derive, and so forth. In this
case, to be able to retrieve and present any one Squaregiven its namesome object must know
(have the information) about all the Squares. We previously decided, as shown in Figure 17.5
,
that a software Board will aggregate all the Square objects. Therefore, Board has the information
necessary to fulfill this responsibility. Figure 17.6
 illustrates applying Expert in the context of
drawing.
Figure 17.6. Applying Expert.
The next GRASP principle, Low Coupling, explains why Expert is a useful, core principle of OO
design.
Low Coupling
Question: Why Board over Dog?
<<<PDF_PAGE 428>>>
Expert guides us to assign the responsibility to know a particular Square, given a unique name, to
the Board object because the Board knows about all the Squares (it has the informationit is the
Information Expert). But why does Expert give this advice?
The answer is found in the principle of Low Coupling. Briefly and informally, coupling
 is a
measure of how strongly one element is connected to, has knowledge of, or depends on other
elements. If there is coupling or dependency, then when the depended-upon element changes,
the dependant may be affected. For example, a subclass is strongly coupled to a superclass. An
object A that calls on the operations of object B has coupling to B's services.
The Low Coupling principle applies to many dimensions of software development; it's really one of
the cardinal goals in building software. In terms of object design and responsibilities, we can
describe the advice as follows:
Name:
Low Coupling
Problem:
How to reduce the impact of change?
Solution:
(advice)
Assign responsibilities so that (unnecessary) coupling remains low. Use this
principle to evaluate alternatives.
We use Low Coupling to evaluate existing designs or to evaluate the choice between new
alternativesall other things being equal, we should prefer a design whose coupling is lower than
the alternatives.
For example, as we've decided in Figure 17.5
, a Board object contains many Squares. Why not
assign getSquare to Dog (i.e., some arbitrary other class)? Consider the impact in terms of low
coupling. If a Dog has getSquare, as shown in the UML sketch in Figure 17.7
, it must collaborate
with the Board to get the collection of all the Squares in the Board. They are probably stored in a
Map collection object, which allows retrieval by a key. Then, the Dog can access and return one
particular Square by the key name.
Figure 17.7. Evaluating the effect of coupling on this design.
[View full size image]

<<<PDF_PAGE 429>>>
But let's evaluate the total coupling with this poor Dog design versus our original design where
Board does getSquare. In the Dog case, the Dog and the Board must both know about Square
objects (two objects have coupling to Square); in the Board case, only Board must know about
Square objects (one object has coupling to Square). Thus, the overall coupling is lower with the
Board design, and all other things being equal, it is better than the Dog design, in terms of
supporting the goal of Low Coupling.
At a higher-goal level, why is Low Coupling desirable? In other words, why would we want to
reduce the impact of change? Because Low Coupling tends to reduce the time, effort, and defects
in modifying software. That's a short answer, but one with big implications in building and
maintaining software!
Key Point: Expert Supports Low Coupling
To return to the motivation for Information Expert: it guides us to a choice that
supports Low Coupling. Expert asks us to find the object that has most of the
information required for the responsibility (e.g., Board) and assign responsibility
there.
If we put the responsibility anywhere else (e.g., Dog), the overall coupling will be
higher because more information or objects must be shared away from their original
source or home, as the squares in the Map collection had to be shared with the Dog,
away from their home in the Board.
Applying UML: Please note a few UML elements in the sequence diagram in Figure 17.7
:
The return value variable sqs from the getAllSquares message is also used to name the
lifeline object in sqs : Map<Square> (e.g., a collection of type Map that holds Square
objects). Referencing a return value variable in a lifeline box (to send it messages) is
common.
The variable s in the starting getSquare message and the variable s in the later get message
refer to the same object.
The message expression s = get(name) : Square indicates that the type of s is a reference
to a Square instance.
Controller
A simple layered architecture has a UI layer and a domain layer, among others. Actors, such as
the human observer in the Monopoly game, generate UI events, such as clicking on a button with
a mouse to play the game. The UI software objects (in Java for example, a JFrame window and a
JButton button) must then react to the mouse click event and ultimately cause the game to play.
From the Model-View Separation Principle, we know the UI objects should not contain application
or "business" logic such as calculating a player's move. Therefore, once the UI objects pick up the
mouse event, they need to delegate (forward the task to another object) the request to domain
<<<PDF_PAGE 430>>>
objects in the domain layer.
Model-View Separation
 p. 209
The Controller pattern answers this simple question: What first object after or beyond the UI layer
should receive the message from the UI layer?
To tie this back to system sequence diagrams, as a review of Figure 17.8
 shows, the key system
operation is playGame. Somehow the human observer generates a playGame request (probably
by clicking on a GUI button labeled "Play Game") and the system responds.
Figure 17.8. SSD for the Monopoly game. Note the playGame
operation.
Figure 17.9
 illustrates a finer-grained look at what's going on, assuming a Java Swing GUI JFrame
window and JButton button.[8]
 Clicking on a JButton sends an actionPerformed message to some
object, often to the JFrame window itself, as we see in Figure 17.9
. Thenand this is the key
pointthe JFrame window must adapt that actionPerformed message into something more
semantically meaningful, such as a playGame message (to correspond to the SSD analysis), and
delegate the playGame message to a domain object in the domain layer.
[8] Similar objects, messages, and collaboration patterns apply to .NET, Python, etc.
Figure 17.9. Who is the Controller for the playGame system operation?
[View full size image]
<<<PDF_PAGE 431>>>
Do you see the connection between the SSD system operations and the detailed
object design from the UI to domain layer? This is important.
Thus, Controller deals with a basic question in OO design: How to connect the UI layer to the
application logic layer? Should the Board be the first object to receive the playGame message
from the UI layer? Or something else?
In some OOA/D methods, the name controller was given to the application logic object that
received and "controlled" (coordinated) handling the request.
The Controller pattern offers the following advice:
Name:
Controller
Problem:
What first object beyond the UI layer receives and coordinates ("controls") a
system operation?
Solution:
(advice)
Assign the responsibility to an object representing one of these choices:
Represents the overall "system," a "root object," a device that the
software is running within, or a major subsystem (these are all
variations of a facade controller).
Represents a use case scenario within which the system operation
occurs (a use case or session controller)
Let's consider these options:
Option 1: Represents the overall "system," or a "root object"such as an object called
MonopolyGame.
Option 1: Represents a device that the software is running withinthis option appertains to
specialized hardware devices such as a phone or a bank cash machine (e.g., software class Phone
or BankCashMachine); it doesn't apply in this case.
<<<PDF_PAGE 432>>>
Option 2: Represents the use case or session. The use case that the playGame system operation
occurs within is called Play Monopoly Game. Thus, a software class such as
PlayMonopolyGameHandler (appending "…Handler" or "…Session" is an idiom in OO design when
this version is used).
Option #1, class MonopolyGame, is reasonable if there are only a few system operations (more
on the trade-offs when we discuss High Cohesion). Therefore, Figure 17.10
 illustrates the design
decision based on Controller.
Figure 17.10. Applying the Controller patternusing MonopolyGame.
Connecting the UI layer to the domain layer of software objects.
High Cohesion
Based on the Controller decision, we are now at the design point shown in the sequence diagram
to the right. The detailed design discussion of what comes nextconsistently and methodically
applying GRASPis explored in a following chapter, but right now we have two contrasting design
approaches worth considering, illustrated in Figure 17.11
.
Figure 17.11. Contrasting the level of cohesion in different designs.
[View full size image]
<<<PDF_PAGE 433>>>
Notice in the left-hand version that the MonopolyGame object itself does all the work, and in the
right-hand version it delegates and coordinates the work for the playGame request. In software
design a basic quality known as cohesion informally measures how functionally related the
operations of a software element are, and also measures how much work a software element is
doing. As a simple contrasting example, an object Big with 100 methods and 2,000 source lines of
code (SLOC) is doing a lot more than an object Small with 10 methods and 200 source lines. And
if the 100 methods of Big are covering many different areas of responsibility (such as database
access and random number generation), then Big has less focus or functional cohesion than
Small. In summary, both the amount of code and the relatedness of the code are an indicator of
an object's cohesion.
To be clear, bad cohesion (low cohesion) doesn't just imply an object does work only by itself;
indeed, a low cohesion object with 2,000 SLOC probably collaborates with many other objects.
Now, here's a key point: All that interaction tends to also create bad (high) coupling. Bad
cohesion and bad coupling often go hand-in-hand.
In terms of the contrasting designs in Figure 17.11
, the left-hand version of MonopolyGame has
worse cohesion than the right-hand version, since the left-hand version is making the
MonopolyGame object itself do all the work, rather than delegating and distributing work among
objects. This leads to the principle of High Cohesion, which is used to evaluate different design
choices. All other things being equal, prefer a design with higher cohesion.
Name:
High Cohesion
Problem:
How to keep objects focused, understandable, and manageable, and as a side
effect, support Low Coupling?
Solution:
(advice)
Assign responsibilities so that cohesion remains high. Use this to evaluate
alternatives.
<<<PDF_PAGE 434>>>
We can say that the right-hand design better supports High Cohesion than the left-hand version.
 

<<<PDF_PAGE 435>>>
 
17.9. Applying GRASP to Object Design
GRASP stands for General Responsibility Assignment Software Patterns.[9]
 The name was chosen
to suggest the importance of grasping these principles to successfully design object-oriented
software.
[9] Technically, one should write "GRAS Patterns" rather than "GRASP Patterns," but the latter sounds better.
All nine GRASP patterns are summarized on the inside front cover of this book.
Understanding and being able to apply the ideas behind GRASPwhile coding or while drawing
interaction and class diagramsenables developers new to object technology needs to master these
basic principles as quickly as possible; they form a foundation for designing OO systems.
There are nine GRASP patterns:
Creator
Controller
Pure Fabrication
Information Expert
High Cohesion
Indirection
Low Coupling
Polymorphism
Protected
Variations
The remainder of this chapter reexamines the first five in more detail; the remaining four are
introduced in Chapter 25
 starting on p. 413
.
 

<<<PDF_PAGE 436>>>
 
17.10. Creator
Problem
Who should be responsible for creating a new instance of some class?
The creation of objects is one of the most common activities in an object-oriented system.
Consequently, it is useful to have a general principle for the assignment of creation
responsibilities. Assigned well, the design can support low coupling, increased clarity,
encapsulation, and reusability.
Solution
Assign class B the responsibility to create an instance of class A if one of these is true (the more
the better):[10]
[10] Other creation patterns, such as Concrete Factory and Abstract Factory, are explored later.
B "contains" or compositely aggregates A.
B records A.
B closely uses A.
B has the initializing data for A that will be passed to A when it is created. Thus B is an
Expert with respect to creating A.
B is a creator of A objects.
If more than one option applies, usually prefer a class B which aggregates or contains class A.
Example
In the NextGen POS application, who should be responsible for creating a SalesLineItem instance?
By Creator, we should look for a class that aggregates, contains, and so on, SalesLineItem
instances. Consider the partial domain model in Figure 17.12
.
Figure 17.12. Partial domain model.
<<<PDF_PAGE 437>>>
Since a Sale contains (in fact, aggregates) many SalesLineItem objects, the Creator pattern
suggests that Sale is a good candidate to have the responsibility of creating SalesLineItem
instances. This leads to the design of object interactions shown in Figure 17.13
.
Figure 17.13. Creating a SalesLineItem.
[View full size image]
This assignment of responsibilities requires that a makeLineItem method be defined in Sale. Once
again, the context in which we considered and decided on these responsibilities was while drawing
an interaction diagram. The method section of a class diagram can then summarize the
responsibility assignment results, concretely realized as methods.
Discussion
Creator guides the assigning of responsibilities related to the creation of objects, a very common
task. The basic intent of the Creator pattern is to find a creator that needs to be connected to the
created object in any event. Choosing it as the creator supports low coupling.
Composite aggregates Part, Container contains Content, and Recorder records. Recorded are all
very common relationships between classes in a class diagram. Creator suggests that the
enclosing container or recorder class is a good candidate for the responsibility of creating the
thing contained or recorded. Of course, this is only a guideline.
<<<PDF_PAGE 438>>>
Note that we turned to the concept of composition
 in considering the Creator pattern. A
composite object is an excellent candidate to make its parts.
composite aggregation
 p. 264
Sometimes you identify a creator by looking for the class that has the initializing data that will be
passed in during creation. This is actually an example of the Expert pattern. Initializing data is
passed in during creation via some kind of initialization method, such as a Java constructor that
has parameters. For example, assume that a Payment instance, when created, needs to be
initialized with the Sale total. Since Sale knows the total, Sale is a candidate creator of the
Payment.
Contraindications
Often, creation requires significant complexity, such as using recycled instances for performance,
conditionally creating an instance from one of a family of similar classes based upon some
external property value, and so forth. In these cases, it is advisable to delegate creation to a
helper class called a Concrete Factory or an Abstract Factory [GHJV95
] rather than use the class
suggested by Creator. Factories
 are discussed starting on p. 440
.
Benefits
Low coupling is supported, which implies lower maintenance dependencies and higher
opportunities for reuse. Coupling is probably not increased because the created class is likely
already visible to the creator class, due to the existing associations that motivated its choice
as creator.
Related Patterns or Principles
Low Coupling
Concrete Factory and Abstract Factory
Whole-Part [BMRSS96
] describes a pattern to define aggregate objects that support
encapsulation of components.
 

<<<PDF_PAGE 439>>>
 
17.11. Information Expert (or Expert)
Problem
What is a general principle of assigning responsibilities to objects?
A Design Model may define hundreds or thousands of software classes, and an application may
require hundreds or thousands of responsibilities to be fulfilled. During object design, when the
interactions between objects are defined, we make choices about the assignment of
responsibilities to software classes. If we've chosen well, systems tend to be easier to understand,
maintain, and extend, and our choices afford more opportunity to reuse components in future
applications.
Solution
Assign a responsibility to the information expertthe class that has the information necessary to
fulfill the responsibility.
Example
In the NextGEN POS application, some class needs to know the grand total of a sale.
Start assigning responsibilities by clearly stating the responsibility.
By this advice, the statement is:
Who should be responsible for knowing the grand total of a sale?
By Information Expert, we should look for that class of objects that has the information needed to
determine the total.
Now we come to a key question: Do we look in the Domain Model or the Design Model to analyze
the classes that have the information needed? The Domain Model illustrates conceptual classes of
the real-world domain; the Design Model illustrates software classes.
Answer:
If there are relevant classes in the Design Model, look there first.1.
Otherwise, look in the Domain Model, and attempt to use (or expand) its representations to
inspire the creation of corresponding design classes.
2.
For example, assume we are just starting design work and there is no, or a minimal, Design
Model. Therefore, we look to the Domain Model for information experts; perhaps the real-world
Sale is one. Then, we add a software class to the Design Model similarly called Sale, and give it
<<<PDF_PAGE 440>>>
the responsibility of knowing its total, expressed with the method named getTotal. This approach
supports low representational gap in which the software design of objects appeals to our concepts
of how the real domain is organized.
To examine this case in detail, consider the partial Domain Model in Figure 17.14
.
Figure 17.14. Associations of Sale.
What information do we need to determine the grand total? We need to know about all the
SalesLineItem instances of a sale and the sum of their subtotals. A Sale instance contains these;
therefore, by the guideline of Information Expert, Sale is a suitable class of object for this
responsibility; it is an information expert for the work.
As mentioned, it is in the context of the creation of interaction diagrams that these questions of
responsibility often arise. Imagine we are starting to work through the drawing of diagrams in
order to assign responsibilities to objects. A partial interaction diagram and class diagram in
Figure 17.15
 illustrate some decisions.
Figure 17.15. Partial interaction and class diagrams.
We are not done yet. What information do we need to determine the line item subtotal?
SalesLineItem.quantity and ProductDescription.price. The SalesLineItem knows its quantity and
its associated ProductDescription; therefore, by Expert, SalesLineItem should determine the
subtotal; it is the information expert.
<<<PDF_PAGE 441>>>
In terms of an interaction diagram, this means that the Sale should send getSubtotal messages to
each of the SalesLineItems and sum the results; this design is shown in Figure 17.16
.
Figure 17.16. Calculating the Sale total.
[View full size image]
To fulfill the responsibility of knowing and answering its subtotal, a SalesLineItem has to know the
product price.
The ProductDescription is an information expert on answering its price; therefore, SalesLineItem
sends it a message asking for the product price.
The design is shown in Figure 17.17
.
Figure 17.17. Calculating the Sale total.
[View full size image]
In conclusion, to fulfill the responsibility of knowing and answering the sale's total, we assigned
<<<PDF_PAGE 442>>>
three responsibilities to three design classes of objects as follows.
Design Class
Responsibility
Sale
knows sale total
SalesLineItem
knows line item
subtotal
ProductDescription
knows product price
We considered and decided on these responsibilities in the context of drawing an interaction
diagram. We could then summarize the methods in the method section of a class diagram.
The principle by which we assigned each responsibility was Information Expertplacing it with the
object that had the information needed to fulfill it.
Discussion
Information Expert is frequently used in the assignment of responsibilities; it is a basic guiding
principle used continuously in object design. Expert is not meant to be an obscure or fancy idea; it
expresses the common "intuition" that objects do things related to the information they have.
Notice that the fulfillment of a responsibility often requires information that is spread across
different classes of objects. This implies that many "partial" information experts will collaborate in
the task. For example, the sales total problem ultimately required the collaboration of three
classes of objects. Whenever information is spread across different objects, they will need to
interact via messages to share the work.
Expert usually leads to designs where a software object does those operations that are normally
done to the inanimate real-world thing it represents; Peter Coad calls this the "Do It Myself"
strategy [Coad95
]. For example, in the real world, without the use of electro-mechanical aids, a
sale does not tell you its total; it is an inanimate thing. Someone calculates the total of the sale.
But in object-oriented software land, all software objects are "alive" or "animated," and they can
take on responsibilities and do things. Fundamentally, they do things related to the information
they know. I call this the "animation" principle in object design; it is like being in a cartoon where
everything is alive.
The Information Expert patternlike many things in object technologyhas a real-world analogy. We
commonly give responsibility to individuals who have the information necessary to fulfill a task.
For example, in a business, who should be responsible for creating a profit-and-loss statement?
The person who has access to all the information necessary to create itperhaps the chief financial
officer. And just as software objects collaborate because the information is spread around, so it is
with people. The company's chief financial officer may ask accountants to generate reports on
credits and debits.
Contraindications
In some situations, a solution suggested by Expert is undesirable, usually because of problems in
coupling and cohesion (these principles are discussed later in this chapter).
For example, who should be responsible for saving a Sale in a database? Certainly, much of the
information to be saved is in the Sale object, and thus Expert could argue that the responsibility
lies in the Sale class. And, by logical extension of this decision, each class would have its own
services to save itself in a database. But acting on that reasoning leads to problems in cohesion,
coupling, and duplication. For example, the Sale class must now contain logic related to database
handling, such as that related to SQL and JDBC (Java Database Connectivity). The class no longer
<<<PDF_PAGE 443>>>
focuses on just the pure application logic of "being a sale." Now other kinds of responsibilities
lower its cohesion. The class must be coupled to the technical database services of another
subsystem, such as JDBC services, rather than just being coupled to other objects in the domain
layer of software objects, so its coupling increases. And it is likely that similar database logic
would be duplicated in many persistent classes.
All these problems indicate violation of a basic architectural principle: design for a separation of
major system concerns. Keep application logic in one place (such as the domain software
objects), keep database logic in another place (such as a separate persistence services
subsystem), and so forth, rather than intermingling different system concerns in the same
component.[11]
[11] See Chapter 33
 for a discussion of separation of concerns.
Supporting a separation of major concerns improves coupling and cohesion in a design. Thus,
even though by Expert we could find some justification for putting the responsibility for database
services in the Sale class, for other reasons (usually cohesion and coupling), we'd end up with a
poor design.
Benefits
Information encapsulation is maintained since objects use their own information to fulfill
tasks. This usually supports low coupling, which leads to more robust and maintainable
systems. Low Coupling is also a GRASP pattern that is discussed in a following section.
Behavior is distributed across the classes that have the required information, thus
encouraging more cohesive "lightweight" class definitions that are easier to understand and
maintain. High cohesion is usually supported (another pattern discussed later).
Related Patterns or Principles
Low Coupling
High Cohesion
Also Known As; Similar To
"Place responsibilities with data," "That which knows, does," "Do It Myself," "Put Services with the
Attributes They Work On."
 

<<<PDF_PAGE 444>>>
 
17.12. Low Coupling
Problem
How to support low dependency, low change impact, and increased reuse?
Coupling
 is a measure of how strongly one element is connected to, has knowledge of, or relies
on other elements. An element with low (or weak) coupling is not dependent on too many other
elements; "too many" is context dependent, but we examine it anyway. These elements include
classes, subsystems, systems, and so on.
A class with high (or strong) coupling relies on many other classes. Such classes may be
undesirable; some suffer from the following problems:
Forced local changes because of changes in related classes.
Harder to understand in isolation.
Harder to reuse because its use requires the additional presence of the classes on which it is
dependent.
Solution
Assign a responsibility so that coupling remains low. Use this principle to evaluate alternatives.
Example
Consider the following partial class diagram from a NextGen case study:
Assume we need to create a Payment instance and associate it with the Sale. What class should
be responsible for this? Since a Register "records" a Payment in the real-world domain, the
Creator pattern suggests Register as a candidate for creating the Payment. The Register instance
could then send an addPayment message to the Sale, passing along the new Payment as a
parameter. A possible partial interaction diagram reflecting this is shown in Figure 17.18
.
Figure 17.18. Register creates Payment.

<<<PDF_PAGE 445>>>
This assignment of responsibilities couples the Register class to knowledge of the Payment class.
Applying UML: Note that the Payment instance is explicitly named p so that in message 2 it can
be referenced as a parameter.
Figure 17.19
 shows an alternative solution to creating the Payment and associating it with the
Sale.
Figure 17.19. Sale creates Payment.
Which design, based on assignment of responsibilities, supports Low Coupling? In both cases we
assume the Sale must eventually be coupled to knowledge of a Payment. Design 1, in which the
Register creates the Payment, adds coupling of Register to Payment; Design 2, in which the Sale
does the creation of a Payment, does not increase the coupling. Purely from the point of view of
coupling, prefer Design 2 because it maintains overall lower coupling. This example illustrates how
two patternsLow Coupling and Creatormay suggest different solutions.
In practice, the level of coupling alone can't be considered in isolation from other
principles such as Expert and High Cohesion. Nevertheless, it is one factor to consider
in improving a design.
Discussion
Low Coupling is a principle to keep in mind during all design decisions; it is an underlying goal to
continually consider. It is an evaluative principle that you apply while evaluating all design
decisions.
In object-oriented languages such as C++, Java, and C#, common forms of coupling from TypeX
to TypeY include the following:
TypeX has an attribute (data member or instance variable) that refers to a TypeY instance,
or TypeY itself.
A TypeX object calls on services of a TypeY object.
<<<PDF_PAGE 446>>>
TypeX has a method that references an instance of TypeY, or TypeY itself, by any means.
These typically include a parameter or local variable of type TypeY, or the object returned
from a message being an instance of TypeY.
TypeX is a direct or indirect subclass of TypeY.
TypeY is an interface, and TypeX implements that interface.
Low Coupling encourages you to assign a responsibility so that its placement does not increase
the coupling to a level that leads to the negative results that high coupling can produce.
Low Coupling supports the design of classes that are more independent, which reduces the impact
of change. It can't be considered in isolation from other patterns such as Expert and High
Cohesion, but rather needs to be included as one of several design principles that influence a
choice in assigning a responsibility.
A subclass is strongly coupled to its superclass. Consider carefully any decision to derive from a
superclass since it is such a strong form of coupling. For example, suppose that objects must be
stored persistently in a relational or object database. In this case, you could follow the relatively
common design practice of creating an abstract superclass called PersistentObject from which
other classes derive. The disadvantage of this subclassing is that it highly couples domain objects
to a particular technical service and mixes different architectural concerns, whereas the
advantage is automatic inheritance of persistence behavior.
You cannot obtain an absolute measure of when coupling is too high. What is important is that
you can gauge the current degree of coupling and assess whether increasing it will lead to
problems. In general, classes that are inherently generic in nature and with a high probability for
reuse should have especially low coupling.
The extreme case of Low Coupling is no coupling between classes. This case offends against a
central metaphor of object technology: a system of connected objects that communicate via
messages. Low Coupling taken to excess yields a poor designone with a few incohesive, bloated,
and complex active objects that do all the work, and with many passive zero-coupled objects that
act as simple data repositories. Some moderate degree of coupling between classes is normal and
necessary for creating an object-oriented system in which tasks are fulfilled by a collaboration
between connected objects.
Contraindications
High coupling to stable elements and to pervasive elements is seldom a problem. For example, a
J2EE application can safely couple itself to the Java libraries (java.util, and so on), because they
are stable and widespread.
Pick Your Battles
It is not high coupling per se that is the problem; it is high coupling to elements that are unstable
in some dimension, such as their interface, implementation, or mere presence.
This is an important point: As designers, we can add flexibility, encapsulate details and
implementations, and in general design for lower coupling in many areas of the system. But, if we
put effort into "future proofing" or lowering the coupling when we have no realistic motivation,
this is not time well spent.
You must pick your battles in lowering coupling and encapsulating things. Focus on the points of
realistic high instability or evolution. For example, in the NextGen project, we know that different
third-party tax calculators (with unique interfaces) need to be connected to the system.
<<<PDF_PAGE 447>>>
Therefore, designing for low coupling at this variation point is practical.
Benefits
not affected by changes in other components
simple to understand in isolation
convenient to reuse
Background
Coupling and cohesion are truly fundamental principles in design, and should be appreciated and
applied as such by all software developers. Larry Constantine, also a founder of structured design
in the 1970s and a current advocate of more attention to usability engineering [CL99
], was
primarily responsible in the 1960s for identifying and communicating coupling and cohesion as
critical principles [Constantine68
, CMS74
].
Related Patterns
Protected Variation
 

<<<PDF_PAGE 448>>>
 
17.13. Controller
Problem
What first object beyond the UI layer receives and coordinates ("controls") a system operation?
System operations were first explored during the analysis of SSD. These are the major input
events upon our system. For example, when a cashier using a POS terminal presses the "End
Sale" button, he is generating a system event indicating "the sale has ended." Similarly, when a
writer using a word processor presses the "spell check" button, he is generating a system event
indicating "perform a spell check."
A controller is the first object beyond the UI layer that is responsible for receiving or handling a
system operation message.
Solution
Assign the responsibility to a class representing one of the following choices:
Represents the overall "system," a "root object," a device that the software is running
within, or a major subsystemthese are all variations of a facade controller.
Represents a use case scenario within which the system event occurs, often named
<UseCaseName>Handler, <UseCaseName>Coordinator, or <UseCaseName>Session (use
case or session controller).
Use the same controller class for all system events in the same use case scenario.
Informally, a session is an instance of a conversation with an actor. Sessions can be of
any length but are often organized in terms of use cases (use case sessions).
Corollary: Note that "window," "view," and "document" classes are not on this list. Such classes
should not fulfill the tasks associated with system events; they typically receive these events and
delegate them to a controller.
Example
Some get a better sense of applying this pattern with code examples. Look ahead in the
Implementation
 section on p. 309
 for Java examples of both rich client and Web UIs.
The NextGen application contains several system operations, as illustrated in Figure 17.20
. This
model shows the system itself as a class (which is legal and sometimes useful when modeling).
Figure 17.20. Some system operations of the NextGen POS application.
<<<PDF_PAGE 449>>>
During analysis, system operations may be assigned to the class System in some analysis model,
to indicate they are system operations. However, this does not mean that a software class named
System fulfills them during design. Rather, during design, a controller class is assigned the
responsibility for system operations (see Figure 17.21
).
Figure 17.21. What object should be the Controller for enterItem?
[View full size image]
Who should be the controller for system events such as enterItem and endSale?
By the Controller pattern, here are some choices:
Represents the overall "system," "root object," device, or
subsystem.
Register, POSSystem
Represents a receiver or handler of all system events of a
use case scenario.
ProcessSaleHandler,
ProcessSaleSession
Note that in the domain of POS, a Register (called a POS Terminal) is a specialized device with
<<<PDF_PAGE 450>>>
software running in it.
In terms of interaction diagrams, one of the examples in Figure 17.22
 could be useful.
Figure 17.22. Controller choices.
The choice of which of these classes is the most appropriate controller is influenced by other
factors, which the following section explores.
During design, the system operations identified during system behavior analysis are assigned to
one or more controller classes, such as Register, as shown in Figure 17.23
.
Figure 17.23. Allocation of system operations.
[View full size image]
<<<PDF_PAGE 451>>>
Discussion
Some get a better sense of applying this pattern with code examples. Look ahead in the
Implementation
 section on p. 309
 for examples in Java for both rich client and Web UIs.
Simply, this is a delegation pattern. In accordance with the understanding that the UI layer
shouldn't contain application logic, UI layer objects must delegate work requests to another layer.
When the "other layer" is the domain layer, the Controller pattern summarizes common choices
that you, as an OO developer, make for the domain object delegate that receives the work
requests.
Systems receive external input events, typically involving a GUI operated by a person. Other
mediums of input include external messages, such as in a call-processing telecommunications
switch or signals from sensors such as in process control systems.
In all cases, you must choose a handler for these events. Turn to the Controller pattern for
guidance toward generally accepted, suitable choices. As illustrated in Figure 17.21
, the controller
is a kind of facade into the domain layer from the UI layer.
You will often want to use the same controller class for all the system events of one use case so
that the controller can maintain information about the state of the use case. Such information is
useful, for example, to identify out-of-sequence system events (for example, a makePayment
operation before an endSale operation). Different controllers may be used for different use cases.
A common defect in the design of controllers results from over-assignment of responsibility. A
<<<PDF_PAGE 452>>>
controller then suffers from bad (low) cohesion, violating the principle of High Cohesion.
Guideline
Normally, a controller should delegate to other objects the work that needs to be
done; it coordinates or controls the activity. It does not do much work itself.
Please see the "Issues and Solutions" section for elaboration.
The first category of controller is a facade controller representing the overall system, device, or a
subsystem. The idea is to choose some class name that suggests a cover, or facade, over the
other layers of the application and that provides the main point of service calls from the UI layer
down to other layers. The facade could be an abstraction of the overall physical unit, such as a
Register[12]
 , TelecommSwitch, Phone, or Robot; a class representing the entire software system,
such as POSSystem; or any other concept which the designer chooses to represent the overall
system or a subsystem, even, for example, ChessGame if it was game software.
[12] Various terms are used for a physical POS unit, including register, point-of-sale terminal (POST), and so forth. Over time,
"register" has come to embody the notion of both a physical unit and the logical abstraction of the thing that registers sales
and payments.
Facade controllers are suitable when there are not "too many" system events, or when the user
interface (UI) cannot redirect system event messages to alternating controllers, such as in a
message-processing system.
If you choose a use case controller, then you will have a different controller for each use case.
Note that this kind of controller is not a domain object; it is an artificial construct to support the
system (a Pure Fabrication in terms of the GRASP patterns). For example, if the NextGen
application contains use cases such as Process Sale and Handle Returns, then there may be a
ProcessSaleHandler class and so forth.
When should you choose a use case controller? Consider it an alternative when placing the
responsibilities in a facade controller leads to designs with low cohesion or high coupling, typically
when the facade controller is becoming "bloated" with excessive responsibilities. A use case
controller is a good choice when there are many system events across different processes; it
factors their handling into manageable separate classes and also provides a basis for knowing and
reasoning about the state of the current scenario in progress.
In the UP and Jacobson's older Objectory method [Jacobson92
], there are the (optional) concepts
of boundary, control, and entity classes. Boundary objects are abstractions of the interfaces,
entity objects are the application-independent (and typically persistent) domain software
objects, and control objects are use case handlers as described in this Controller pattern.
A important corollary of the Controller pattern is that UI objects (for example, window or button
objects) and the UI layer should not have responsibility for fulfilling system events. In other
words, system operations should be handled in the application logic or domain layers of objects
rather than in the UI layer of a system. See the "Issues and Solutions" section for an example.
Web UIs and Server-Side Application of Controller
Please see p. 310
 for a server-side example using Java Struts
a popular framework.
<<<PDF_PAGE 453>>>
A similar delegation approach can be used in ASP.NET and WebForms: The "code behind" file that
contains event handlers for Web browser button clicks will obtain a reference to a domain
controller object (e.g., a Register object in the POS case study), and then delegate the request for
work. This is in contrast to the common, fragile style of ASP.NET programming in which
developers insert application logic handling in the "code behind" file, thus mixing application logic
into the UI layer.
Server-side Web UI frameworks (such as Struts) embody the concept of the Web-MVC (Model-
View-Controller) pattern. The "controller" in Web-MVC differs from this GRASP controller. The
former is part of the UI layer and controls the UI interaction and page flow. The GRASP controller
is part of the domain layer and controls or coordinates the handling of the work request,
essentially unaware of what UI technology is being used (e.g., a Web UI, a Swing UI, …).
Also common with server-side designs when Java technologies are used is delegation from the
Web UI layer (e.g., from a Struts Action class) to an Enterprise JavaBeans (EJB) Session object.
Variant #2 of the Controller patternan object representing a user session or use case
scenariocovers this case. In this case, the EJB Session object may itself delegate farther on to the
domain layer of objects, and again, you can apply the Controller pattern to choose a suitable
receiver in the pure domain layer.
All that said, the appropriate handling of server-side systems operations is strongly influenced by
the chosen server technical frameworks and continues to be a moving target. But the underlying
principle of Model-View Separation can and does still apply.
Even with a rich-client UI (e.g., a Swing UI) that interacts with a server, the Controller pattern
still applies. The client-side UI forwards the request to the local client-side controller, and the
controller forwards all or part of the request handling to remote services. This design lowers the
coupling of the UI to remote services and makes it easier, for example, to provide the services
either locally or remotely, through the indirection of the client-side controller.
Benefits
Increased potential for reuse and pluggable interfaces These benefits ensure that application
logic is not handled in the interface layer. The responsibilities of a controller could technically
be handled in an interface object, but such a design implies that program code and the
fulfillment of application logic would be embedded in interface or window objects. An
interface-as-controller design reduces the opportunity to reuse logic in future applications,
since logic that is bound to a particular interface (for example, window-like objects) is
seldom applicable in other applications. By contrast, delegating a system operation
responsibility to a controller supports the reuse of the logic in future applications. And since
the application logic is not bound to the interface layer, it can be replaced with a different
interface.
Opportunity to reason about the state of the use case Sometimes we must ensure that
system operations occur in a legal sequence, or we want to be able to reason about the
current state of activity and operations within the use case that is underway. For example,
we may have to guarantee that the makePayment operation cannot occur until the endSale
operation has occurred. If so, we need to capture this state information somewhere; the
controller is one reasonable choice, especially if we use the same controller throughout the
use case (as recommended).
Implementation
The following examples use Java technologies for two common cases, a rich client in Java Swing
and a Web UI with Struts on the server (a Servlet engine).
<<<PDF_PAGE 454>>>
Please note that you should apply a similar approach in .NET WinForms and ASP.NET
WebForms. A good practice in well-designed .NET (often ignored by MS programmers who
violate the Model-View Separation Principle) is to not insert application logic code in the event
handlers or in the "code behind" files (those are both part of the UI layer). Rather, in the .NET
event handlers or "code behind" files, simply obtain a reference to a domain object (e.g., a
Register object), and delegate to it.
Implementation with Java Swing: Rich Client UI
This section assumes you are familiar with basic Swing. The code contains comments to explain
the key points. A few comments: Notice at 
 that the ProcessSaleJFrame window has a
reference to the domain controller object, the Register. At 
 I define the handler for the button
click. At 
 I show the key messagesending the enterItem message to the controller in the
domain layer.
    
package com.craiglarman.nextgen.ui.swing;
       
// imports…
       
// in Java, a JFrame is a typical window
    
public class ProcessSaleJFrame extends JFrame
    
{
       
// the window has a reference to the 'controller' domain object
  
private Register register;
       
// the window is passed the register, on creation
    
public ProcessSaleJFrame(Register _register)
    
{
       
register = _register;
    
}
       
// this button is clicked to perform the
       
// system operation "enterItem"
    
private JButton BTN_ENTER_ITEM;
       
// this is the important method!
       
// here i show the message from the UI layer to domain layer
    
private JButton getBTN_ENTER_ITEM()
    
{
          
// does the button exist?
       
if (BTN_ENTER_ITEM != null)
          
return BTN_ENTER_ITEM;
          
// ELSE button needs to be initialized...
       
BTN_ENTER_ITEM = new JButton();
       
BTN_ENTER_ITEM.setText("Enter Item");
<<<PDF_PAGE 455>>>
          
// THIS IS THE KEY SECTION!
          
// in Java, this is how you define
          
// a click handler for a button
  
BTN_ENTER_ITEM.addActionListener(new ActionListener()
        
{
        
public void actionPerformed(ActionEvent e)
        
{
               
// Transformer is a utility class to
               
// transform Strings to other data types
               
// because the JTextField GUI widgets have Strings
           
ItemID id = Transformer.toItemID(getTXT_ID().getText());
           
int qty = Transformer.toInt(getTXT_QTY().getText());
               
// here we cross the boundary from the
               
// UI layer to the domain layer
               
// delegate to the 'controller'
               
// > > > THIS IS THE KEY STATEMENT < < <
         
register.enterItem(id, qty);
        
}
        
} ); // end of the addActionListener call
     
return BTN_ENTER_ITEM;
     
} // end of method
  
// …
  
} // end of class
Implementation with Java Struts: Client Browser and WebUI
This section assumes you are familiar with basic Struts. Notice at 
 that to obtain a reference to
the Register domain object on the server side, the Action object must dig into the Servlet context.
At 
 I show the key messagesending the enterItem message to the domain controller object in
the domain layer.
  
package com.craiglarman.nextgen.ui.web;
  
// … imports
     
// in Struts, an Action object is associated with a
     
// web browser button click, and invoked (on the server)
     
// when the button is clicked.
  
public class EnterItemAction extends Action {
     
// this is the method invoked on the server
     
// when the button is clicked on the client browser
  
public ActionForward execute( ActionMapping mapping,
<<<PDF_PAGE 456>>>
                                  
ActionForm form,
                                  
HttpServletRequest request,
                                  
HttpServletResponse response )
                                
throws Exception
  
{
        
// the server has a Repository object that
        
// holds references to several things, including
        
// the POS "register" object
     
Repository repository = (Repository)getServlet().
        
getServletContext().getAttribute(Constants.REPOSITORY_KEY);
   
Register register = repository.getRegister();
        
// extract the itemID and qty from the web form
     
String txtId = ((SaleForm)form).getItemID();
     
String txtQty = ((SaleForm)form).getQuantity();
        
// Transformer is a utility class to
        
// transform Strings to other data types
     
ItemID id = Transformer.toItemID(txtId);
     
int qty = Transformer.toInt(txtQty);
        
// here we cross the boundary from the
        
// UI layer to the domain layer
        
// delegate to the 'domain controller'
        
// > > > THIS IS THE KEY STATEMENT < < <
     
register.enterItem(id, qty);
     
// …
  
} // end of method
  
} // end of class
Bloated Controllers
Issues and Solutions
Poorly designed, a controller class will have low cohesionunfocused and handling too many areas
of responsibility; this is called a bloated controller. Signs of bloating are:
There is only a single controller class receiving all system events in the system, and there
are many of them. This sometimes happens if a facade controller is chosen.
The controller itself performs many of the tasks necessary to fulfill the system event,
without delegating the work. This usually involves a violation of Information Expert and High
Cohesion.
A controller has many attributes, and it maintains significant information about the system
or domain, which should have been distributed to other objects, or it duplicates information
<<<PDF_PAGE 457>>>
found elsewhere.
Among the cures for a bloated controller are these two:
Add more controllersa system does not have to need only one. Instead of facade controllers,
employ use case controllers. For example, consider an application with many system events,
such as an airline reservation system.
It may contain the following controllers:
Use case controllers
MakeReservationHandler
ManageSchedulesHandler
ManageFaresHandler
1.
Design the controller so that it primarily delegates the fulfillment of each system operation
responsibility to other objects.
2.
UI Layer Does Not Handle System Events
To reiterate: An important corollary of the Controller pattern is that UI objects (for example,
window objects) and the UI layer should not have responsibility for handling system events. As an
example, consider a design in Java that uses a JFrame to display the information.
Assume the NextGen application has a window that displays sale information and captures cashier
operations. Using the Controller pattern, Figure 17.24
 illustrates an acceptable relationship
between the JFrame and the controller and other objects in a portion of the POS system (with
simplifications).
Figure 17.24. Desirable coupling of UI layer to domain layer.
[View full size image]
<<<PDF_PAGE 458>>>
Notice that the SaleJFrame classpart of the UI layerdelegates the enterItem request to the
Register object. It did not get involved in processing the operation or deciding how to handle it;
the window only delegated it to another layer.
Assigning the responsibility for system operations to objects in the application or domain layer by
using the Controller pattern rather than the UI layer can increase reuse potential. If a UI layer
object (like the SaleJFrame) handles a system operation that represents part of a business
process, then business process logic would be contained in an interface (for example, window-
like) object; the opportunity for reuse of the business logic then diminishes because of its coupling
to a particular interface and application. Consequently, the design in Figure 17.25
 is undesirable.
Figure 17.25. Less desirable coupling of interface layer to domain
layer.
[View full size image]
<<<PDF_PAGE 459>>>
Placing system operation responsibility in a domain object controller makes it easier to reuse the
program logic supporting the associated business process in future applications. It also makes it
easier to unplug the UI layer and use a different UI framework or technology, or to run the
system in an offline "batch" mode.
Message Handling Systems and the Command Pattern
Some applications are message-handling systems or servers that receive requests from other
processes. A telecommunications switch is a common example. In such systems, the design of the
interface and controller is somewhat different. The details are explored in a later chapter, but in
essence, a common solution is to use the Command pattern [GHJV95
] and Command Processor
pattern [BMRSS96
], introduced in Chapter 38
.
Related Patterns
Command In a message-handling system, each message may be represented and handled
by a separate Command object [GHJV95
].
Facade A facade controller is a kind of Facade [GHJV95
].
Layers This is a POSA pattern [BMRSS96
]. Placing domain logic in the domain layer rather
than the presentation layer is part of the Layers pattern.
<<<PDF_PAGE 460>>>
Pure Fabrication This GRASP pattern is an arbitrary creation of the designer, not a
software class whose name is inspired by the Domain Model. A use case controller is a kind
of Pure Fabrication.
 

<<<PDF_PAGE 461>>>
 
17.14. High Cohesion
Problem
How to keep objects focused, understandable, and manageable, and as a side effect, support Low
Coupling?
In terms of object design, cohesion (or more specifically, functional cohesion) is a measure of
how strongly related and focused the responsibilities of an element are. An element with highly
related responsibilities that does not do a tremendous amount of work has high cohesion. These
elements include classes, subsystems, and so on.
Solution
Assign a responsibility so that cohesion remains high. Use this to evaluate alternatives.
A class with low cohesion does many unrelated things or does too much work. Such classes are
undesirable; they suffer from the following problems:
hard to comprehend
hard to reuse
hard to maintain
delicate; constantly affected by change
Low cohesion classes often represent a very "large grain" of abstraction or have taken on
responsibilities that should have been delegated to other objects.
Example
Let's take another look at the example problem used in the Low Coupling pattern and analyze it
for High Cohesion.
Assume we have a need to create a (cash) Payment instance and associate it with the Sale. What
class should be responsible for this? Since Register records a Payment in the real-world domain,
the Creator pattern suggests Register as a candidate for creating the Payment. The Register
instance could then send an addPayment message to the Sale, passing along the new Payment as
a parameter, as shown in Figure 17.26
.
Figure 17.26. Register creates Payment.
<<<PDF_PAGE 462>>>
This assignment of responsibilities places the responsibility for making a payment in the Register.
The Register is taking on part of the responsibility for fulfilling the makePayment system
operation.
In this isolated example, this is acceptable; but if we continue to make the Register class
responsible for doing some or most of the work related to more and more system operations, it
will become increasingly burdened with tasks and become incohesive.
Imagine fifty system operations, all received by Register. If Register did the work related to each,
it would become a "bloated" incohesive object. The point is not that this single Payment creation
task in itself makes the Register incohesive, but as part of a larger picture of overall responsibility
assignment, it may suggest a trend toward low cohesion.
And most important in terms of developing skills as object designers, regardless of the final
design choice, is the valuable achievement that at least we know to consider the impact on
cohesion.
By contrast, as shown in Figure 17.27
, the second design delegates the payment creation
responsibility to the Sale supports higher cohesion in the Register.
Figure 17.27. Sale creates Payment.
Since the second design supports both high cohesion and low coupling, it is desirable.
<<<PDF_PAGE 463>>>
In practice, the level of cohesion alone can't be considered in isolation from other
responsibilities and other principles such as Expert and Low Coupling.
Discussion
Like Low Coupling, High Cohesion is a principle to keep in mind during all design decisions; it is an
underlying goal to continually consider. It is an evaluative principle that a designer applies while
evaluating all design decisions.
Grady Booch describes high functional cohesion as existing when the elements of a component
(such as a class) "all work together to provide some well-bounded behavior" [Booch94
].
Here are some scenarios that illustrate varying degrees of functional cohesion:
Very low cohesion A class is solely responsible for many things in very different functional
areas.
Assume the existence of a class called RDB-RPC-Interface which is completely
responsible for interacting with relational databases and for handling remote procedure
calls. These are two vastly different functional areas, and each requires lots of
supporting code. The responsibilities should be split into a family of classes related to
RDB access and a family related to RPC support.
1.
Low cohesion A class has sole responsibility for a complex task in one functional area.
Assume the existence of a class called RDBInterface which is completely responsible for
interacting with relational databases. The methods of the class are all related, but
there are lots of them, and a tremendous amount of supporting code; there may be
hundreds or thousands of methods. The class should split into a family of lightweight
classes sharing the work to provide RDB access.
2.
High cohesion A class has moderate responsibilities in one functional area and collaborates
with other classes to fulfill tasks.
Assume the existence of a class called RDBInterface that is only partially responsible
for interacting with relational databases. It interacts with a dozen other classes related
to RDB access in order to retrieve and save objects.
3.
Moderate cohesion A class has lightweight and sole responsibilities in a few different areas
that are logically related to the class concept but not to each other.
Assume the existence of a class called Company that is completely responsible for (a)
knowing its employees and (b) knowing its financial information. These two areas are
not strongly related to each other, although both are logically related to the concept of
a company. In addition, the total number of public methods is small, as is the amount
of supporting code.
4.
As a rule of thumb, a class with high cohesion has a relatively small number of methods, with
<<<PDF_PAGE 464>>>
highly related functionality, and does not do too much work. It collaborates with other objects to
share the effort if the task is large.
A class with high cohesion is advantageous because it is relatively easy to maintain, understand,
and reuse. The high degree of related functionality, combined with a small number of operations,
also simplifies maintenance and enhancements. The fine grain of highly related functionality also
supports increased reuse potential.
The High Cohesion patternlike many things in object technologyhas a real-world analogy. It is a
common observation that if a person takes on too many unrelated responsibilitiesespecially ones
that should properly be delegated to othersthen the person is not effective. This is observed in
some managers who have not learned how to delegate. These people suffer from low cohesion;
they are ready to become "unglued."
Another Classic Principle: Modular Design
Coupling and cohesion are old principles in software design; designing with objects does not imply
ignoring well-established fundamentals. Another of thesewhich is strongly related to coupling and
cohesionis to promote modular design. To quote:
Modularity is the property of a system that has been decomposed into a set of cohesive and
loosely coupled modules [Booch94
].
We promote a modular design by creating methods and classes with high cohesion. At the basic
object level, we achieve modularity by designing each method with a clear, single purpose and by
grouping a related set of concerns into a class.
Cohesion and Coupling; Yin and Yang
Bad cohesion usually begets bad coupling, and vice versa. I call cohesion and
coupling the yin and yang of software engineering because of their
interdependent influence. For example, consider a GUI widget class that
represents and paints a widget, saves data to a database, and invokes remote
object services. Not only is it profoundly incohesive, but it is coupled to many
(and disparate) elements.
Contraindications
In a few cases, accepting lower cohesion is justified.
One case is the grouping of responsibilities or code into one class or component to simplify
maintenance by one personalthough be warned that such grouping may also worsen
maintenance. But suppose an application contains embedded SQL statements that by other good
design principles should be distributed across ten classes, such as ten "database mapper" classes.
Now, commonly only one or two SQL experts know how to best define and maintain this SQL.
Even if dozens of object-oriented (OO) programmers work on the project, few OO programmers
may have strong SQL skills. Suppose the SQL expert is not even a comfortable OO programmer.
The software architect may decide to group all the SQL statements into one class,
RDBOperations, so that it is easy for the SQL expert to work on the SQL in one location.
Another case for components with lower cohesion is with distributed server objects. Because of
overhead and performance implications associated with remote objects and remote
<<<PDF_PAGE 465>>>
communication, it is sometimes desirable to create fewer and larger, less cohesive server objects
that provide an interface for many operations. This approach is also related to the pattern called
Coarse-Grained Remote Interface. In that pattern the remote operations are made more
coarse-grained so that they can to do or request more work in remote operation calls to alleviate
the performance penalty of remote calls over a network. As a simple example, instead of a
remote object with three fine-grained operations setName, setSalary, and setHireDate, there is
one remote operation, setData, which receives a set of data. This results in fewer remote calls
and better performance.
Benefits
Clarity and ease of comprehension of the design is increased.
Maintenance and enhancements are simplified.
Low coupling is often supported.
Reuse of fine-grained, highly related functionality is increased because a cohesive class can
be used for a very specific purpose.
 

<<<PDF_PAGE 466>>>
 
17.15. Recommended Resources
The metaphor of RDD especially emebged from the influential object work in Smalltalk at
Tektronix in Portland, from Kent Beck, Ward Cunningham, Rebecca Wirfs-Brock, and others.
Designing Object-Oriented Software [WWW90
] is the landmark text, and is as relevant today as
when it was written. Wirfs-Brock has more recently released another RDD text, Object Design:
Roles, Responsibilities, and Collaborations [WM02
].
Two other recommended texts emphasizing fundamental object design principles are Object-
Oriented Design Heuristics by Riel and Object Models by Coad.
 

# Chapter 18. Object Design Examples with GRASP


<<<PDF_PAGE 467>>>
 
Chapter 18. Object Design Examples with
GRASP
To invent, you need a good imagination and a pile of junk.
Thomas Edison
Objectives
Design use case realizations.
Apply GRASP to assign responsibilities to classes.
Apply UML to illustrate and think through the design of objects.
 

<<<PDF_PAGE 468>>>
 
Introduction
This chapter applies OO design principles and the UML to the case studies, to show larger
examples of reasonably designed objects with responsibilities and collaborations. Please note that
the GRASP patterns by name are not important; they're just a learning aid that helps us think
methodically about basic OO design.
[View full size image]
Key Point
The assignment of responsibilities and design of collaborations are very important and
creative steps during design, both while diagraming and while coding.
The No-Magic Zone
This chapter invites you to learn through detailed explanations how an OO developer might
reason while designing by principles. In fact, over a short time of practice, these principles
become ingrained, and some of the decision-making happens almost at a subconscious level.
But first, I wish to exhaustively illustrate that no "magic" is needed in object design, no
unjustifiable decisions are necessaryassignment of responsibilities and the choice of collaborations
can be rationally explained and learned. OO software design really can be more science than art,
though there is plenty of room for creativity and elegant design.
 

<<<PDF_PAGE 469>>>
 
18.1. What is a Use Case Realization?
The last chapter on basic OO design principles looked at little fragments of design problems. In
contrast, this chapter demonstrates the larger picture of designing the domain objects[1]
 for an
entire use case scenario. You will see larger-scale collaborations and more complex UML
diagrams.
[1] Recall, as explained on p. 200, that the case studies focus on the domain layer, not the UI or service layers, which are
nevertheless important.
To quote, "A use-case realization describes how a particular use case is realized within the
Design Model, in terms of collaborating objects" [RUP
]. More precisely, a designer can describe
the design of one or more scenarios of a use case; each of these is called a use case realization
(though non-standard, perhaps better called a scenario realization). Use case realization is a
UP term used to remind us of the connection between the requirements expressed as use cases
and the object design that satisfies the requirements.
UML diagrams are a common language to illustrate use case realizations. And as we explored in
the prior chapter, we can apply principles and patterns of object design, such as Information
Expert and Low Coupling, during this use case realization design work.
To review, Figure 18.1
 illustrates the relationship between some UP artifacts, emphasizing the Use
Case Model and the Design Modeluse case realizations.
Figure 18.1. Artifact relationships, emphasizing use case realization.
[View full size image]
<<<PDF_PAGE 470>>>
Some relevant artifact-influence points include the following:
The use case suggests the system operations that are shown in SSDs.
The system operations become the starting messages entering the Controllers for domain
layer interaction diagrams. See Figure 18.2
.
This is a key point often missed by those new to OOA/D modeling.
Figure 18.2. Communication diagrams and system operation
handling.
[View full size image]
<<<PDF_PAGE 471>>>
Domain layer interaction diagrams illustrate how objects interact to fulfill the required
tasksthe use case realization.
 

<<<PDF_PAGE 472>>>
 
18.2. Artifact Comments
SSDs, System Operations, Interaction Diagrams, and Use Case
Realizations
In the current NextGen POS iteration we are considering scenarios and system operations
identified on the SSDs of the Process Sale use case:
makeNewSale
enterItem
endSale
makePayment
If we use communication diagrams to illustrate the use case realizations, we will draw a different
communication diagram to show the handling of each system operation message. Of course, the
same is true for sequence diagrams. For example, see Figure 18.2
 and Figure 18.3
.
Figure 18.3. Sequence diagrams and system operation handling.
[View full size image]

<<<PDF_PAGE 473>>>
Key Point
The system operations in the SSDs are used as the starting messages into the domain
layer controller objects.
Use Cases and Use Case Realizations
Naturally, use cases are a prime input to use case realizations. The use case text and related
requirements expressed in the Supplementary Specifications, Glossary, UI prototypes, report
prototypes, and so forth, all inform developers what needs to be built. But bear in mind that
written requirements are imperfectoften very imperfect.
Involve the Customer Frequently
The above section gives the impression that documents are the critical requirements input to
doing software design and development. Truly, though, it is hard to beat the ongoing participation
of customers in evaluating demos, discussing requirements and tests, prioritizing, and so forth.
One of the principles of agile methods is "Business people and developers must work together
daily throughout the project"a very worthy goal.
Operation Contracts and Use Case Realizations
As discussed, use case realizations could be designed directly from the use case text or from
one's domain knowledge. For some complex system operations, contracts may have been written
that add more analysis detail. For example:
Contract CO2: enterItem
Operation:
enterItem(itemID : ItemID, quantity : integer)
Cross References:
Use Cases: Process Sale
Preconditions:
There is a sale underway.
Postconditions:
- A SalesLineItem instance sli was created (instance
creation).
- ...
In conjunction with contemplating the use case text, for each contract, we work through the
postcondition state changes and design message interactions to satisfy the requirements. For
example, given this partial enterItem system operation, we diagram a partial interaction that
satisfies the state change of SalesLineItem instance creation, as shown in Figure 18.4
.
<<<PDF_PAGE 474>>>
Figure 18.4. Partial interaction diagram satisfies a contract
postcondition.
[View full size image]
The Domain Model and Use Case Realizations
In the interaction diagrams, the Domain Model inspires some of the software objects, such as a
Sale conceptual class and Sale software class. The existing Domain Modelas with all analysis
artifactswon't be perfect; you should expect errors and omissions. You will discover new concepts
that were previously missed, ignore concepts that were previously identified, and do likewise with
associations and attributes.
Must you limit the design classes in the Design Model to classes with names inspired from the
Domain Model? Not at all. It's normal to discover new conceptual classes during design work that
were missed during earlier domain analysis and to make up software classes whose names and
purpose are completely unrelated to the Domain Model.
 

<<<PDF_PAGE 475>>>
 
18.3. What's Next?
The remainder of this chapter is organized as follows:
A relatively detailed discussion of the design of the NextGen POS.1.
Likewise, for the Monopoly case study, starting on p. 347
.2.
Applying UML and patterns to these case studies, let's get into the details…
 

<<<PDF_PAGE 476>>>
 
18.4. Use Case Realizations for the NextGen Iteration
The following sections explore the choices and decisions made during the design of a use case
realization with objects based on the GRASP patterns. I intentionally detail explanations, to show
that there's no magic in OO designit's based on justifiable principles.
Initialization and the 'Start Up' Use Case
The Start Up use case realization is the design context in which to consider creating most of the
'root' or long-lived objects. See p. 345
 for some of the design details.
Guideline
When coding, program at least some Start Up initialization first. But during OO design
modeling, consider the Start Up initialization design last, after you have discovered
what really needs to be created and initialized. Then, design the initialization to
support the needs of other use case realizations.
Based on this guideline, we will explore the Process Sale use case realization before the
supporting Start Up design.
How to Design makeNewSale?
The makeNewSale system operation occurs when a cashier initiates a request to start a new sale,
after a customer has arrived with things to buy. The use case may have been sufficient to decide
what was necessary, but for this case study we wrote contracts for all the system operations, to
demonstrate the approach.
Contract CO1: makeNewSale
<<<PDF_PAGE 477>>>
Operation:
makeNewSale()
Cross References:
Use Cases: Process Sale
Preconditions:
none
Postconditions:
- A Sale instance s was created (instance creation).
- s was associated with the Register (association
formed).
- Attributes of s were initialized.
Choosing the Controller Class
Our first design choice involves choosing the controller for the system operation message
enterItem. By the Controller pattern, here are some choices:
Represents the overall "system," "root object,"
a specialized device, or a major subsystem.
Store a kind of root object because we think
of most of the other domain objects as
"within" the Store.
Register a specialized device that the software
runs on; also called a POSTerminal.
POSSystem a name suggesting the overall
system
Represents a receiver or handler of all system
events of a use case scenario.
ProcessSaleHandler constructed from the
pattern <use-case-name> "Handler" or
"Session"
ProcessSaleSession
Choosing a device-object facade controller like Register is satisfactory if there are only a few
system operations and if the facade controller is not taking on too many responsibilities (in other
words, if it is not becoming incohesive). Choosing a use case controller is suitable when we have
many system operations and we wish to distribute responsibilities in order to keep each controller
class lightweight and focused (in other words, cohesive). In this case, Register suffices since there
are only a few system operations.
Remember, this Register is a software object in the Design Model. It isn't a physical
register.
Thus, based on the Controller pattern, the interaction diagram shown in Figure 18.5
 begins by
sending the system operation makeNewSale message to a Register software object.
<<<PDF_PAGE 478>>>
Figure 18.5. Applying the GRASP Controller pattern.
Creating a New Sale
We must create a software Sale object, and the GRASP Creator pattern suggests assigning the
responsibility for creation to a class that aggregates, contains, or records the object to be
created.
Analyzing the Domain Model reveals that a Register may be thought of as recording a Sale;
indeed, the word "register" in business has for hundreds of years meant the thing that recorded
(or registered) account transactions, such as sales.
Thus, Register is a reasonable candidate for creating a Sale. Note how this supports a low
representational gap (LRG). And by having the Register create the Sale, we can easily associate
the Register with it over time so that during future operations within the session, the Register will
have a reference to the current Sale instance.
In addition to the above, when the Sale is created, it must create an empty collection (such as a
Java List) to record all the future SalesLineItem instances that will be added. This collection will
be contained within and maintained by the Sale instance, which implies by Creator that the Sale is
a good candidate for creating the collection.
Therefore, the Register creates the Sale, and the Sale creates an empty collection, represented
by a multiobject in the interaction diagram.
Hence, the interaction diagram in Figure 18.6
 illustrates the design.
Figure 18.6. Sale and the collection creation.
[View full size image]
<<<PDF_PAGE 479>>>
Conclusion
The design was not difficult, but the point of its careful explanation in terms of Controller and
Creator was to illustrate that the details of a design can be rationally and methodically decided
and explained in terms of principles and patterns, such as GRASP.
How to Design enterItem?
The enterItem system operation occurs when a cashier enters the itemID and (optionally) the
quantity of something to be purchased. Here is the complete contract:
Contract CO2: enterItem
Operation:
enterItem(itemID : ItemID, quantity : integer)
Cross References:
Use Cases: Process Sale
Preconditions:
There is an underway sale.
Postconditions:
- A SalesLineItem instance sli was created (instance
creation).
- sli was associated with the current Sale (association
formed).
- sli.quantity became quantity (attribute modification).
- sli was associated with a ProductDescription, based on
itemID match (association formed).
We now construct an interaction diagram to satisfy the postconditions of enterItem, using the
GRASP patterns to help with the design decisions.
<<<PDF_PAGE 480>>>
Choosing the Controller Class
Our first choice involves handling the responsibility for the system operation message enterItem.
Based on the Controller pattern, as for makeNewSale, we will continue to use Register as a
controller.
Display Item Description and Price?
Because of a principle of Model-View Separation, it is not the responsibility of non-GUI objects
(such as a Register or Sale) to get involved in output tasks. Therefore, although the use case
states that the description and price are displayed after this operation, we ignore the design at
this time.
All that is required with respect to responsibilities for the display of information is that the
information is known, which it is in this case.
Creating a New SalesLineItem
The enterItem contract postconditions indicate the creation, initialization, and association of a
SalesLineItem. Analysis of the Domain Model reveals that a Sale contains SalesLineItem objects.
Taking inspiration from the domain, we determine that a software Sale may similarly contain
software SalesLineItem. Hence, by Creator, a software Sale is an appropriate candidate to create
a SalesLineItem.
We can associate the Sale with the newly created SalesLineItem by storing the new instance in its
collection of line items. The postconditions indicate that the new SalesLineItem needs a quantity
when created; therefore, the Register must pass it along to the Sale, which must pass it along as
a parameter in the create message. In Java, that would be implemented as a constructor call with
a parameter.
Therefore, by Creator, a makeLineItem message is sent to a Sale for it to create a SalesLineItem.
The Sale creates a SalesLineItem, and then stores the new instance in its permanent collection.
The parameters to the makeLineItem message include the quantity, so that the SalesLineItem
can record it, and the ProductDescription that matches the itemID.
Finding a ProductDescription
The SalesLineItem needs to be associated with the ProductDescription that matches the incoming
itemID. This implies that we must retrieve a Product-Description, based on an itemID match.
Before considering how to achieve the lookup, we want to consider who should be responsible for
it. Thus, a first step is:
Start assigning responsibilities by clearly stating the responsibility.
<<<PDF_PAGE 481>>>
To restate the problem:
Who should be responsible for knowing a ProductDescription, based on an itemID match?
This is neither a creation problem nor one of choosing a controller for a system event. Now we
see our first application of Information Expert in the design.
In many cases, the Expert pattern is the principal one to apply. Information Expert suggests that
the object that has the information required to fulfill the responsibility should do it. Who knows
about all the ProductDescription objects?
Analyzing the Domain Model reveals that the ProductCatalog logically contains all the
ProductDescriptions. Once again, taking inspiration from the domain, we design software classes
with similar organization: a software ProductCatalog will contain software ProductDescriptions.
With that decided, then by Information Expert ProductCatalog is a good candidate for this lookup
responsibility since it knows all the ProductDescription objects.
The lookup can be implemented, for example, with a method called getProductDescription
(abbreviated as getProductDesc in some of the diagrams).[2]
[2] The name of access methods is idiomatic to each language. Java always uses the object.getFoo() form; C++ tends to use
object.foo(); and C# uses object.Foo, which hides (like Eiffel and Ada) whether access is by a method call or is direct access
of a public attribute.
Visibility to a ProductCatalog
Who should send the getProductDescription message to the ProductCatalog to ask for a
ProductDescription?
It is reasonable to assume that a long-life Register and a ProductCatalog instance were created
during the initial Start Up use case and that the Register object is permanently connected to the
ProductCatalog object. With that assumption (which we might record on a task list of things to
ensure in the design when we get to designing the initialization), we know that the Register can
send the getProductDescription message to the ProductCatalog.
This implies another concept in object design: visibility. Visibility
 is the ability of one object to
"see" or have a reference to another object.
For an object to send a message to another object, it must have visibility to it.
Since we assume that the Register has a permanent connectionor referenceto the ProductCatalog,
it has visibility to it, and hence can send it messages such as getProductDescription. A following
chapter explores the question of visibility more closely.
The Final Design
<<<PDF_PAGE 482>>>
Given the above discussion, the interaction diagram in Figure 18.7
 and the DCD in Figure 18.8
(dynamic and static views) reflects the decisions regarding the assignment of responsibilities and
how objects should interact. Mark the considerable reflection on the GRASP patterns, that brought
us to this design; the design of object interactions and responsibility assignment requires some
deliberation.
Figure 18.7. The enterItem interaction diagram. Dynamic view.
[View full size image]
Figure 18.8. Partial DCD related to the enterItem design. Static view.
[View full size image]
Yet, once these principles are deeply "grasped" the decisions often come quickly, almost
subconsciously.
Retrieving ProductDescriptions from a Database
<<<PDF_PAGE 483>>>
In the final version of the NextGen POS application, it is unlikely that all the ProductDescriptions
will be in memory. They will most likely be stored in a relational database and retrieved on
demand; some may be locally cached for performance or fault-tolerance reasons. However, in the
interest of simplicity, we defer for now the issues surrounding retrieval from a database and
assume that all the ProductDescriptions are in memory.
Chapter 38
 explores the topic of database access of persistent objects, which is a larger topic
influenced by the choice of technologies, such as Java or .NET.
How to Design endSale?
The endSale system operation occurs when a cashier presses a button indicating the end of
entering line items into a sale (another name could have been endItemEntry). Here is the
contract:
Contract CO3: endSale
Operation:
endSale()
Cross References:
Use Cases: Process Sale
Preconditions:
There is an underway sale.
Postconditions:
Sale.isComplete became true (attribute
modification).
Choosing the Controller Class
Our first choice involves handling the responsibility for the system operation message endSale.
Based on the Controller GRASP pattern, as for enterItem, we will continue to use Register as a
controller.
Setting the Sale.isComplete Attribute
The contract postconditions state:
Sale.isComplete became true (attribute modification).
As always, Expert should be the first pattern considered unless the problem is a controller or
creation problem (which it is not).
Who should be responsible for setting the isComplete attribute of the Sale to true?
By Expert, it should be the Sale itself, since it owns and maintains the isComplete attribute. Thus,
the Register will send a becomeComplete message to the Sale to set it to true (see Figure
18.9
).[3]
[3] That style is especially a Smalltalk idiom. Probably in Java, setComplete(true).
<<<PDF_PAGE 484>>>
Figure 18.9. Completion of item entry.
[View full size image]
Calculating the Sale Total
Consider this fragment of the Process Sale use case:
Main Success Scenario:
Customer arrives ...3.
Cashier tells System to create a new sale.4.
Cashier enters item identifier.5.
System records sale line item and ...6.
Cashier repeats steps 3-4 until indicates done.
System presents total with taxes calculated.4.
In step 5, a total is presented (or displayed). Because of the Model-View Separation principle, we
should not concern ourselves with the design of how the sale total will be displayed, but we must
ensure that the total is known. Note that no design class currently knows the sale total, so we
need to create a design of object interactions that satisfies this requirement.
As always, Information Expert should be a pattern to consider unless the problem is a controller
or creation problem (which it is not).
You have probably figured out by Expert that the Sale itself should be responsible for knowing its
total. But to make crystal clear the reasoning process to find an Expert, follow the analysis of this
simple example.
State the responsibility:
Who should be responsible for knowing the sale total?
1.
2.
<<<PDF_PAGE 485>>>
Summarize the information required:
The sale total is the sum of the subtotals of all the sales line-items.
sales line-item subtotal := line-item quantity * product description price
2.
List the information required to fulfill this responsibility and the classes that know this
information.
3.
Information Required
for Sale Total
Information Expert
ProductDescription.price
ProductDescription
SalesLineItem.quantity
SalesLineItem
all the SalesLineItems in
the current Sale
Sale
Next we analyze the reasoning process in more detail:
Who should be responsible for calculating the Sale total? By Expert, it should be the Sale
itself, since it knows about all the SalesLineItem instances whose subtotals must be summed
to calculate the sale total. Therefore, Sale will have the responsibility of knowing its total,
implemented as a getTotal method.
For a Sale to calculate its total, it needs the subtotal for each SalesLineItem. Who should be
responsible for calculating the SalesLineItem subtotal? By Expert, it should be the
SalesLineItem itself, since it knows the quantity and the ProductDescription it is associated
with. Therefore, SalesLineItem will have the responsibility of knowing its subtotal,
implemented as a getSubtotal method.
For the SalesLineItem to calculate its subtotal, it needs the price of the ProductDescription.
Who should be responsible for providing the ProductDescription price? By Expert, it should
be the ProductDescription itself, since it encapsulates the price as an attribute. Therefore,
ProductDescription will have the responsibility of knowing its price, implemented as a
getPrice operation.
My goodness, that was detailed!
Although the above analysis is trivial in this case and the degree of excruciating
elaboration presented is uncalled for in actual design practice, the same reasoning
strategy to find an Expert can and should be applied in more difficult situations. If you
follow the above logic, you can see how to apply Expert to almost any problem.
The Sale.getTotal Design
Given the above discussion, let us construct an interaction diagram that illustrates what happens
<<<PDF_PAGE 486>>>
when a Sale is sent a getTotal message. The first message in this diagram is getTotal, but
observe that the getTotal message is not a system operation message (such as enterItem or
makeNewSale).
This leads to the following observation:
Not all interaction diagrams start with a system operation message; they can start
with any message for which the designer wishes to show interactions.
The interaction diagram is shown in Figure 18.10
. First, the getTotal message is sent to a Sale
instance. The Sale then sends a getSubtotal message to each related SalesLineItem instance. The
SalesLineItem in turn sends a getPrice message to its associated ProductDescriptions.
Figure 18.10. Sale.getTotal interaction diagram.
[View full size image]
Since arithmetic is not (usually) illustrated via messages, we can illustrate the details of the
calculations by attaching algorithms or constraints to the diagram that defines the calculations.
Who will send the getTotal message to the Sale? Most likely, it will be an object in the UI layer,
such as a Java JFrame.
Observe in Figure 18.12
 the use of the "method" note symbol style in UML 2.
Figure 18.12. Showing a method in a note symbol.
[View full size image]
<<<PDF_PAGE 487>>>
Figure 18.11. Showing a method in a note symbol.
[View full size image]
How to Design makePayment?
The makePayment system operation occurs when a cashier enters the amount of cash tendered
for payment. Here is the complete contract:
Contract CO4: makePayment
<<<PDF_PAGE 488>>>
Operation:
makePayment( amount: Money )
Cross References:
Use Cases: Process Sale
Preconditions:
There is an underway sale.
Postconditions:
- A Payment instance p was created (instance creation).
- p.amountTendered became amount (attribute modification).
- p was associated with the current Sale (association formed).
- The current Sale was associated with the Store (association
formed); (to add it to the historical log of completed sales).
We construct a design to satisfy the postconditions of makePayment.
Creating the Payment
One of the contract postconditions states:
A Payment instance p was created (instance creation).
This is a creation responsibility, so we consider the Creator GRASP pattern.
Who records, aggregates, most closely uses, or contains a Payment? There is some appeal in
stating that a Register logically records a Payment because in the real domain a "register" records
account information; this motivates Register's candidacy by the goal of reducing the
representational gap in the software design. Additionally, we can reasonably expect that Sale
software will closely use a Payment; thus, it, too, may be a candidate.
Another way to find a creator is to use the Expert pattern in terms of who the Information Expert
is with respect to initializing datathe amount tendered in this case. The Register is the controller
that receives the system operation makePayment message, so it will initially have the amount
tendered. Consequently the Register is again a candidate.
In summary, there are two candidates:
Register
Sale
Now, this leads to a key design idea:
<<<PDF_PAGE 489>>>
Guideline
When there are alternative design choices, take a closer look at the cohesion
and coupling implications of the alternatives, and possibly at the future evolution
pressures on the alternatives. Choose an alternative with good cohesion, coupling,
and stability in the presence of likely future changes.
Consider some of the implications of these choices in terms of the High Cohesion and Low
Coupling GRASP patterns. If we choose the Sale to create the Payment, the work (or
responsibilities) of the Register is lighterleading to a simpler Register definition. Also, the Register
does not need to know about the existence of a Payment instance because it can be recorded
indirectly via the Saleleading to lower coupling in the Register. This leads to the design shown in
Figure 18.13
.
Figure 18.13. Register.makePayment interaction diagram.
[View full size image]
This interaction diagram satisfies the postconditions of the contract: the Payment has been
created, associated with the Sale, and its amountTendered has been set.
Logging a Sale
Once complete, the requirements state that the sale should be placed in an historical log. As
always, Information Expert should be an early pattern considered unless the problem is a
controller or creation problem (which it is not), and the responsibility should be stated:
Who is responsible for knowing all the logged sales and doing the logging?
By the goal of low representational gap in the software design (in relation to our concepts of the
domain), we can reasonably expect a Store to know all the logged sales since they are strongly
related to its finances. Other alternatives include classic accounting concepts, such as a
SalesLedger. Using a SalesLedger object makes sense as the design grows and the Store
becomes incohesive (see Figure 18.14
).
Figure 18.14. Who should be responsible for knowing the completed
<<<PDF_PAGE 490>>>
sales?
[View full size image]
Note also that the postconditions of the contract indicate relating the Sale to the Store. This is an
example of postconditions not being what we want to actually achieve in the design. Perhaps we
didn't think of a SalesLedger earlier, but now that we have, we choose to use it instead of a
Store. If this were the case, we would (ideally) add SalesLedger to the Domain Model as well
since a sales ledger is a concept in the real-world domain. This kind of discovery and change
during design work is to be expected.
In this case, we stick with the original plan of using the Store (see Figure 18.15
).
Figure 18.15. Logging a completed sale.
[View full size image]
<<<PDF_PAGE 491>>>
Calculating the Balance
The Process Sale use case implies that the balance due from a payment be printed on a receipt
and displayed somehow.
Because of the Model-View Separation principle, we should not concern ourselves with how the
balance will be displayed or printed, but we must ensure that it is known. Note that no class
currently knows the balance, so we need to create a design of object interactions that satisfies
this requirement.
As always, Information Expert should be considered unless the problem is a controller or creation
problem (which it is not), and the responsibility should be stated:
Who is responsible for knowing the balance?
To calculate the balance, we need the sale total and payment cash tendered. Therefore, Sale and
Payment are partial Experts on solving this problem.
If the Payment is primarily responsible for knowing the balance, it needs visibility to the Sale, to
ask the Sale for its total. Since it does not currently know about the Sale, this approach would
increase the overall coupling in the designit would not support the Low Coupling pattern.
In contrast, if the Sale is primarily responsible for knowing the balance, it needs visibility to the
Payment, to ask it for its cash tendered. Since the Sale already has visibility to the Paymentas its
creatorthis approach does not increase the overall coupling and is therefore a preferable design.
Consequently, the interaction diagram in Figure 18.16
 provides a solution for knowing the
balance.
Figure 18.16. Sale.getBalance interaction diagram.
[View full size image]
<<<PDF_PAGE 492>>>
The Final NextGen DCD for Iteration-1
In accordance with the design decisions in this chapter, Figure 18.17
 illustrates a static-view DCD
of the emerging design for the domain layer, reflecting the use case realizations for the chosen
scenarios of Process Sale in iteration-1.
Figure 18.17. A more complete DCD reflecting most design decisions.
[View full size image]
Of course, we still have more OO design workeither while coding or while modelingto do in other
layers, include the UI layer and services layers.
How to Connect the UI Layer to the Domain Layer?
Common designs by which objects in the UI layer obtain visibility to objects in the domain layer
include the following:
An initializer object (for example, a Factory object) called from the application starting
<<<PDF_PAGE 493>>>
method (e.g., the Java main method) creates both a UI and a domain object and passes the
domain object to the UI.
A UI object retrieves the domain object from a well-known source, such as a factory object
that is responsible for creating domain objects.
Once the UI object has a connection to the Register instance (the facade controller in this design),
it can forward system event messages, such as the enterItem and endSale message, to it (see
Figure 18.18
).
Figure 18.18. Connecting the UI and domain layers.
[View full size image]
In the case of the enterItem message, we want the window to show the running total after each
entry. Design solutions are:
Add a getTotal method to the Register. The UI sends the getTotal message to the Register,
which delegates to the Sale. This has the possible advantage of maintaining lower coupling
from the UI to the domain layerthe UI only knows of the Register object. But it starts to
expand the interface of the Register object, making it less cohesive.
A UI asks for a reference to the current Sale object, and then when it requires the total (or
any other information related to the sale), it directly sends messages to the Sale. This
design increases the coupling from the UI to the domain layer. However, as we explored in
the Low Coupling GRASP pattern discussion, higher coupling in and of itself is not a problem;
rather, coupling to unstable things is a real problem. Assume we decide the Sale is a stable
object that will be an integral part of the designwhich is reasonable. Then, coupling to the
Sale is not a major problem.
As illustrated in Figure 18.19
, this design follows the second approach.
<<<PDF_PAGE 494>>>
Figure 18.19. Connecting the UI and domain layers.
[View full size image]
Initialization and the 'Start Up' Use Case
When to Create the Initialization Design?
Most, if not all, systems have either an implicit or explicit Start Up use case and some initial
system operation related to the starting up of the application. Although abstractly, a startUp
system operation is the earliest one to execute, delay the development of an interaction diagram
for it until after all other system operations have been considered. This practice ensures that
information has been discovered concerning the initialization activities required to support the
later system operation interaction diagrams.
Guideline
Do the initialization design last.
How do Applications Start Up?
The startUp or initialize system operation of a Start Up use case abstractly represents the
<<<PDF_PAGE 495>>>
initialization phase of execution when an application is launched. To understand how to design an
interaction diagram for this operation, you must first understand the contexts in which
initialization can occur. How an application starts and initializes depends on the programming
language and operating system.
In all cases, a common design idiom is to create an initial domain object or a set of peer initial
domain objects that are the first software "domain" objects created. This creation may happen
explicitly in the starting main method or in a Factory object called from the main method.
Often, the initial domain object (assuming the singular case), once created, is responsible for the
creation of its direct child domain objects. For example, a Store chosen as the initial domain
object may be responsible for the creation of a Register object.
In a Java application, for example, the main method may create the initial domain object or
delegate the work to a Factory object that creates it.
public class Main
{
public static void main( String[] args )
{
   
// Store is the initial domain object.
   
// The Store creates some other domain objects.
   
Store store = new Store();
   
Register register = store.getRegister();
   
ProcessSaleJFrame frame = new ProcessSaleJFrame( register );
   
...
}
}
Choosing the Initial Domain Object
What should the class of the initial domain object be?
Guideline
Choose as an initial domain object a class at or near the root of the containment or
aggregation hierarchy of domain objects. This may be a facade controller, such as
Register, or some other object considered to contain all or most other objects, such
as a Store.
High Cohesion and Low Coupling considerations influence the choice between these alternatives.
In this application, we chose the Store as the initial object.
<<<PDF_PAGE 496>>>
Store.create Design
The tasks of creation and initialization derive from the needs of the prior design work, such as the
design for handling enterItem and so on. By reflecting on the prior interaction designs, we identify
the following initialization work:
Create a Store, Register, ProductCatalog, and ProductDescriptions.
Associate the ProductCatalog with ProductDescriptions.
Associate Store with ProductCatalog.
Associate Store with Register.
Associate Register with ProductCatalog.
Figure 18.20
 shows the design. We chose the Store to create the ProductCatalog and Register by
the Creator pattern. Likewise, we chose ProductCatalog to create the ProductDescriptions. Recall
that this approach to creating the specifications is temporary. In the final design, we will
materialize them from a database, as needed.
Figure 18.20. Creation of the initial domain object and subsequent
objects.
[View full size image]
Applying UML: Observe that the creation of all the ProductDescription instances and their
addition to a container happens in a repeating section, indicated by the * following the sequence
numbers.
<<<PDF_PAGE 497>>>
An interesting deviation between modeling the real-world domain and the design is illustrated in
the fact that the software Store object only creates one Register object. A real store may house
many real registers or POS terminals. However, we are considering a software design, not real
life. In our current requirements, our software Store only needs to create a single instance of a
software Register.
Multiplicity between classes of objects in the Domain Model and Design Model may not
be the same.
 

<<<PDF_PAGE 498>>>
 
18.5. Use Case Realizations for the Monopoly Iteration
First, an education point: Please don't dismiss this case study because it isn't a business
application. The logic, especially in later iterations, becomes quite complex, with rich OO design
problems to solve. The core object design principles that it illustratesapplying Information Expert,
evaluating the coupling and cohesion of alternativesare relevant to object design in all domains.
We are designing a simplified version of Monopoly in iteration-1 for a scenario of the use case Play
Monopoly Game. It has two system operations: initialize (or startUp) and playGame. Following
our guideline, we will ignore initialization design until the last step and focus first on the main
system operationsonly playGame in this case.
iteration-1 requirements p. 44
Also, to support the goal of low representational gap (LRG), we look again at Figure 18.21
, which
shows the Domain Model. We turn to it for inspiration as we design the domain layer of the
Design Model.
Figure 18.21. Iteration-1 Domain Model for Monopoly.

<<<PDF_PAGE 499>>>
How to Design playGame?
The playGame system operation occurs when the human game observer performs some UI
gesture (such as clicking a "play game" button) to request the game to play as a simulation while
the observer watches the output.
We didn't write a detailed use case or an operation contract for this case study, as most people
know the rules; our focus is the design issues, not the requirements.
Choosing the Controller Class
Our first design choice involves selecting the controller for the system operation message
playGame that comes from the UI layer into the domain layer. By the Controller pattern, here are
some choices:
Represents the overall "system," "root object,"
a specialized device, or a major subsystem.
MonopolyGame a kind of root object: We think
of most of the other domain objects as
"contained within" the MonopolyGame.
Abbreviated MGame in most of the UML
sketches.
MonopolyGameSystem a name suggesting the
overall system
Represents a receiver or handler of all system
events of a use case scenario.
PlayMonopolyGameHandler constructed from
the pattern <use-case-name> "Handler"
PlayMonopolyGameSession
Choosing a root-object facade controller like MonopolyGame (MGame in Figure 18.22
) is
satisfactory if there are only a few system operations (there are only two in this use case) and if
the facade controller is not taking on too many responsibilities (in other words, if it is not
becoming incohesive).
Figure 18.22. Applying Controller to the playGame system operation.

<<<PDF_PAGE 500>>>
The Game-Loop Algorithm
Before discussing OO design choices, we prepare by considering the basic algorithm of the
simulation. First, some terminology:
turn a player rolling the dice and moving the piece
round all the players taking one turn
Now the game loop:
for N rounds
   
for each Player p
      
p takes a turn
Recall that the iteration-1 version does not have a winner, so the simulation simply runs for N
rounds.
Who is Responsible for Controlling the Game Loop?
Reviewing the algorithm: The first responsibility is game loop controllooping for N rounds and
having a turn played for each player. This is a doing responsibility and is not a creation or
controller problem, so naturally, Expert should be considered. Applying Expert means asking,
"What information is needed for the responsibility?" Here's the analysis:
Information Needed
Who Has the Information?
the current round count
No object has it yet, but by LRG, assigning this to the
MonopolyGame object is justifiable.
all the players (so that each
can be used in taking a turn)
Taking inspiration from the domain model, MonopolyGame is a
good candidate.
Therefore, by Expert, MonopolyGame is a justifiable choice to control the game loop and
coordinate the playing of each round. Figure 18.23
 illustrates in UML. Notice the use of a private
(internal) playRound helper method; it accomplishes at least two goals:
It factors the play-single-round logic into a helper method; it is good to organize cohesive
chunks of behavior into small separate methods.
Good OO method design encourages small methods with a single purpose. This
supports High Cohesion at the method level.
1.
The name playRound is inspired by domain vocabularythat's desirable, it improves
comprehension.
2.
<<<PDF_PAGE 501>>>
2.
Figure 18.23. Game loop.
Who Takes a Turn?
Taking a turn involves rolling the dice and moving a piece to the square indicated by the total of
the dice face values.
What object should be responsible for taking the turn of a player? This is a doing responsibility.
Again, Expert applies.
Now, a naive reaction might be to say "a Player object should take the turn" because in the real
world a human player takes a turn. Howeverand this is a key pointOO designs are not one-to-
one simulations of how a real domain works, especially with respect to how people behave. If you
applied the (wrong) guideline "put responsibilities in software objects as they are assigned to
people" then, for example in the POS domain, a Cashier software object would do almost
everything! A violation of High Cohesion and Low Coupling. Big fat objects.
Rather, object designs distribute responsibilities among many objects by the principle of
Information Expert (among many others).
Therefore, we should not choose a Player object just because a human player takes a turn.
Yet, as we shall see, Player turns out to be a good choice for taking a turn. But the justification
will be by Expert, not inspiration from how humans behave. Applying Expert means asking, "What
information is needed for the responsibility?" Here's the analysis:
Information Needed
Who Has the Information?
current location of the player
(to know the starting point of a
move)
Taking inspiration from the domain model, a Piece knows its
Square and a Player knows its Piece. Therefore, a Player
software object could know its location by LRG.
the two Die objects (to roll
them and calculate their total)
Taking inspiration from the domain model, MonopolyGame is a
candidate since we think of the dice as being part of the game.
<<<PDF_PAGE 502>>>
Information Needed
Who Has the Information?
all the squaresthe square
organization (to be able to
move to the correct new
square)
By LRG, Board is a good candidate.
Now, this is an interesting problem! There are three partial information experts for the "take a
turn" responsibility: Player, MonopolyGame, and Board.
What's interesting about this problem is how to resolve itthe evaluations and trade-offs an OO
developer may consider. Here's the first guideline to solve the problem:
Guideline: When there are multiple partial information experts to choose from, place the
responsibility in the dominant information expertthe object with the majority of the information.
This tends to best support Low Coupling.
Unfortunately, in this case, are all rather equal, each with about one-third of the informationno
dominant expert.
So, here's another guideline to try:
Guideline: When there are alternative design choices, consider the coupling and cohesion impact
of each, and choose the best.
OK, that can be applied. MonopolyGame is already doing some work, so giving it more work
impacts its cohesion, especially when contrasted with a Player and Board object, which are not
doing anything yet. But we still have a two-way tie with these objects.
So, here's another guideline:
Guideline: When there is no clear winner from the alternatives other guidelines, consider
probable future evolution of the software objects and the impact in terms of Information Expert,
cohesion, and coupling.
For example, in iteration-1, taking a turn doesn't involve much information. However, consider
the complete set of game rules in a later iteration. Then, taking a turn can involve buying a
property that the player lands on, if the player has enough money or if its color fits in with the
player's "color strategy." What object would be expected to know a player's cash total? Answer: a
Player (by LRG). What object would be expected to know a player's color strategy? Answer: a
Player (by LRG, as it involves a player's current holdings of properties).
Thus, in the end, by these guidelines Player turns out to be a good candidate, justified by Expert
when we consider the full game rules.
My goodness, that was detailed!
Surely this discussion was more detailed than you normally want to read! Yet, if you
can now follow its reasoning and apply it in new situations, it will serve you very well
for the remainder of your career as an OO developer, and thus have been worth the
effort.
all the squaresthe square
organization (to be able to
move to the correct new
square)
By LRG, Board is a good candidate.
Now, this is an interesting problem! There are three partial information experts for the "take a
turn" responsibility: Player, MonopolyGame, and Board.
What's interesting about this problem is how to resolve itthe evaluations and trade-offs an OO
developer may consider. Here's the first guideline to solve the problem:
Guideline: When there are multiple partial information experts to choose from, place the
responsibility in the dominant information expertthe object with the majority of the information.
This tends to best support Low Coupling.
Unfortunately, in this case, are all rather equal, each with about one-third of the informationno
dominant expert.
So, here's another guideline to try:
Guideline: When there are alternative design choices, consider the coupling and cohesion impact
of each, and choose the best.
OK, that can be applied. MonopolyGame is already doing some work, so giving it more work
impacts its cohesion, especially when contrasted with a Player and Board object, which are not
doing anything yet. But we still have a two-way tie with these objects.
So, here's another guideline:
Guideline: When there is no clear winner from the alternatives other guidelines, consider
probable future evolution of the software objects and the impact in terms of Information Expert,
cohesion, and coupling.
For example, in iteration-1, taking a turn doesn't involve much information. However, consider
the complete set of game rules in a later iteration. Then, taking a turn can involve buying a
property that the player lands on, if the player has enough money or if its color fits in with the
player's "color strategy." What object would be expected to know a player's cash total? Answer: a
Player (by LRG). What object would be expected to know a player's color strategy? Answer: a
Player (by LRG, as it involves a player's current holdings of properties).
Thus, in the end, by these guidelines Player turns out to be a good candidate, justified by Expert
when we consider the full game rules.
My goodness, that was detailed!
Surely this discussion was more detailed than you normally want to read! Yet, if you
can now follow its reasoning and apply it in new situations, it will serve you very well
for the remainder of your career as an OO developer, and thus have been worth the
effort.
<<<PDF_PAGE 503>>>
Based on the above, Figure 18.24
 illustrates the emerging dynamic design and static design.
Figure 18.24. Player takes a turn by Expert.
[View full size image]
Applying UML: Notice the approach to indicating that the takeTurn message is sent to each
player in a collection named players.
Taking a Turn
Taking a turn means:
calculating a random number total between 2 and 12 (the range of two dice)1.
calculating the new square location2.
moving the player's piece from an old location to a new square location3.
First, the random number problem: By LRG, we'll create a Die object with a faceValue attribute.
Calculating a new random faceValue involves changing information in the Die, so by Expert Die
should be able to "roll" itself (generate a new random value, using domain vocabulary), and
answer its faceValue.
Second, the new square location problem: By LRG, it's reasonable that a Board knows all its
Squares. Then by Expert a Board will be responsible for knowing a new square location, given an
old square location, and some offset (the dice total).
<<<PDF_PAGE 504>>>
Third, the piece movement problem: By LRG, it's reasonable for a Player to know its Piece, and a
Piece its Square location (or even for a Player to directly know its Square location). Then by
Expert a Piece will set its new location, but it may receive that new location from its owner, the
Player.
Who Coordinates All This?
The above three steps need to be coordinated by some object. Since the Player is responsible for
taking a turn, the Player should coordinate.
The Problem of Visibility
However, that the Player coordinates these steps implies its collaboration with the Die, Board, and
Piece objects. And this implies a visibility
 needthe Player must have an object reference to those
objects.
Since the Player will need visibility to the Die, Board, and Piece objects each and every turn, we
can usefully initialize the Player during startup with permanent references to those objects.
The Final Design of playGame
Based on the above design decisions, the emerging dynamic design is as shown in Figure 18.25
and the static design as in Figure 18.26
. Notice that each message, each allocation of
responsibility, was methodically and rationally motivated by the GRASP principles. As you come to
master these principles, you will be able to reason through a design and evaluate existing ones in
terms of coupling, cohesion, Expert, and so forth.
Figure 18.25. Dynamic design for playGame.
[View full size image]
<<<PDF_PAGE 505>>>
Figure 18.26. Static design for playGame.
[View full size image]
Applying UML:
<<<PDF_PAGE 506>>>
Notice in Figure 18.25
 that I show two sequence diagrams. In the top, the takeTurn
message to a Player is not expanded. Then, in the bottom diagram, I expand the takeTurn
message. This is a common sketching style, so that each wall diagram is not too large. The
two diagrams are related informally. More formally, I could use UML sd and ref frames (see
p. 235
), which would be easy and appropriate in a UML tool; but for wall sketching,
informality suffices.
Notice again, with the roll and getFaceValue messages to a Die object, the convention of
drawing a loop frame around messages to a collection selection object, to indicate collection
over each element in a collection.
Notice the parameter fvTot in the getSquare message. I am informally suggesting this is the
total of all the Die faceValues. This kind of informality is appropriate when we apply "UML as
sketch," assuming the audience understands the context.
The Command-Query Separation Principle
Notice in Figure 18.25
 that the message to roll the Die is followed by a second getFaceValue to
retrieve its new faceValue. In particular, the roll method is voidit has no return value. For
example:
// style #1; used in the official solution
public void roll()
{
   
faceValue = // random num generation
}
public int getFaceValue()
{
   
return faceValue;
}
Why not make roll non-void and combine these two functions so that the roll method returns the
new faceValue, as follows?
// style #2; why is this poor?
public int roll()
{
   
faceValue = // random num generation
   
return faceValue;
}
You can find many examples of code that follow style #2, but it is considered undesirable because
it violates the Command-Query Separation Principle, (CQS) a classic OO design principle for
methods [Meyer88
]. This principle states that every method should either be:
<<<PDF_PAGE 507>>>
a command method that performs an action (updating, coordinating, …), often has side
effects such as changing the state of objects, and is void (no return value); or
a query that returns data to the caller and has no side effectsit should not permanently
change the state of any objects
Butand this is the key pointa method should not be both.
The roll method is a commandit has the side effect of changing the state of the Die's faceValue.
Therefore, it should not also return the new faceValue, as then the method also becomes a kind of
query and violates the "must be void" rule.
Motivation: Why Bother?
CQS is widely considered desirable in computer science theory because with it, you can more
easily reason about a program's state without simultaneously modifying that state. And it makes
designs simpler to understand and anticipate. For example, if an application consistently follows
CQS, you know that a query or getter method isn't going to modify anything and a command isn't
going to return anything. Simple pattern. This often turns out to be nice to rely on, as the
alternative can be a nasty surpriseviolating the Principle of Least Surprise in software
development.
Consider this contrived but explosive counter-example in which a query method violates CQS:
Missile m = new Missile();
   
// looks harmless to me!
String name = m.getName();
…
public class Missile
{
// …
public String getName()
{
   
launch(); // launch missile!
   
return name;
}
} // end of class
Initialization and the 'Start Up' Use Case
The initialize system operation occurs, at least abstractly, in a Start Up use case. For this design,
we must first choose a suitable root object that will be the creator of some other objects. For
example, MonopolyGame is itself a good candidate root object. By Creator, the MonopolyGame
can justifiably create the Board and Players, for exampleand the Board can justifiably create the
Squares, for example. We could show the details of the dynamic design with UML interaction
diagrams, but I'll use this case as an opportunity to show a UML dependency line stereotyped with
«create», in a class diagram. Figure 18.27
 illustrates a static view diagram that suggests the
creation logic. I ignore the fine details of the interactions. In fact, that's probably suitable,
because from this UML sketch we (the developers who drew this) can pretty easily figure out the
<<<PDF_PAGE 508>>>
creation details while coding.
Figure 18.27. Creation dependencies.
 

<<<PDF_PAGE 509>>>
 
18.6. Process: Iterative and Evolutionary Object Design
I've made many suggestions about iterative and evolutionary object design for use case
realizations over the last few chapters, including
"On to Object Design" on page 213
"Object Design: Example Inputs, Activities, and Outputs" on page 272
The essential point: Keep it light and short, move quickly to code and test, and don't try to detail
everything in UML models. Model the creative, difficult parts of the design.
Figure 18.28
 offers suggestions on the time and space for doing this work.
Figure 18.28. Sample process and setting context.
[View full size image]
Object Design Within the UP
<<<PDF_PAGE 510>>>
To again consider the UP as the example iterative method: use case realizations are part of the
UP Design Model.
Inception The Design Model and use case realizations will not usually be started until elaboration
because they involve detailed design decisions, which are premature during inception.
Elaboration During this phase, use case realizations may be created for the most architecturally
significant or risky scenarios of the design. However, UML diagramming will not be done for every
scenario, and not necessarily in complete and fine-grained detail. The idea is to do interaction
diagrams for the key use case realizations that benefit from some forethought and exploration of
alternatives, focusing on the major design decisions.
Construction Use case realizations are created for remaining design problems.
Table 18.1
 summarizes.
Table 18.1. Sample UP artifacts and timing. s - start; r -
refine
Discipline
Artifact
Incep.
Elab.
Const.
Trans.
Iteration
I1
E1..En
C1..Cn
T1..T2
Business
Modeling
Domain Model
 
s
 
 
Requirements
Use Case Model (SSDs)
s
r
 
 
Supplementary
Specification
s
r
 
 
Glossary
s
r
 
 
Design
Design Model
 
s
r
 
SW Architecture
Document
 
s
 
 
Data Model
 
s
r
 
 

<<<PDF_PAGE 511>>>
 
18.7. Summary
Designing object interactions and assigning responsibilities is at the heart of object design. These
choices can have a profound impact on the extensibility, clarity, and maintainability of an object
software system, plus on the degree and quality of reusable components. There are principles by
which the choices of responsibility assignment can be made; the GRASP patterns summarize
some of the most general and common ones used by object-oriented designers.
 

# Chapter 25. GRASP: More Objects with Responsibilities


<<<PDF_PAGE 576>>>
 
Chapter 25. GRASP: More Objects with
Responsibilities
Luck is the residue of design.
Branch Rickey
Objectives
Learn to apply the remaining GRASP patterns.
 

<<<PDF_PAGE 577>>>
 
Introduction
Previously, we applied five GRASP patterns:
Information Expert, Creator, High Cohesion, Low Coupling, and Controller
The final four GRASP patterns are covered in this chapter. They are:
Polymorphism
Indirection
Pure Fabrication
Protected Variations
[View full size image]
Once these have been explained, we will have a rich and shared vocabulary with which to discuss
designs. And as some of the "Gang-of-Four" (GoF) design patterns (such as Strategy and Abstract
Factory) are also introduced in subsequent chapters, that vocabulary will grow. A short sentence,
such as "I suggest a Strategy generated from a Abstract Factory to support Protected Variations
and low coupling with respect to <X>" communicates lots of information about the design, since
pattern names tersely convey a complex design concept.
Subsequent chapters introduce other useful patterns and apply them to the development of the
second iteration of the case studies.
 

<<<PDF_PAGE 578>>>
 
25.1. Polymorphism
Problem
How handle alternatives based on type? How to create pluggable software components?
Alternatives based on type Conditional variation is a fundamental theme in programs. If a
program is designed using if-then-else or case statement conditional logic, then if a new variation
arises, it requires modification of the case logicoften in many places. This approach makes it
difficult to easily extend a program with new variations because changes tend to be required in
several placeswherever the conditional logic exists.
Pluggable software components Viewing components in client-server relationships, how can you
replace one server component with another, without affecting the client?
Solution
When related alternatives or behaviors vary by type (class), assign responsibility for the
behaviorusing polymorphic operationsto the types for which the behavior varies.[1]
[1] Polymorphism
 has several related meanings. In this context, it means "giving the same name to services in different
objects" [Coad95
] when the services are similar or related. The different object types usually implement a common interface
or are related in an implementation hierarchy with a common superclass, but this is language-dependent; for example,
dynamic binding languages such as Smalltalk do not require this.
Corollary: Do not test for the type of an object and use conditional logic to perform varying
alternatives based on type.
Examples
NextGen Problem: How Support Third-Party Tax Calculators?
In the NextGen POS application, there are multiple external third-party tax calculators that must
be supported (such as Tax-Master and Good-As-Gold TaxPro); the system needs to be able to
integrate with different ones. Each tax calculator has a different interface, so there is similar but
varying behavior to adapt to each of these external fixed interfaces or APIs. One product may
support a raw TCP socket protocol, another may offer a SOAP interface, and a third may offer a
Java RMI interface.
What objects should be responsible for handling these varying external tax calculator interfaces?
Since the behavior of calculator adaptation varies by the type of calculator, by Polymorphism we
should assign the responsibility for adaptation to different calculator (or calculator adapter)
objects themselves, implemented with a polymorphic getTaxes operation (see Figure 25.1
).
Figure 25.1. Polymorphism in adapting to different external tax
calculators.
<<<PDF_PAGE 579>>>
[View full size image]
These calculator adapter objects are not the external calculators, but rather, local software
objects that represent the external calculators, or the adapter for the calculator. By sending a
message to the local object, a call will ultimately be made on the external calculator in its native
API.
Each getTaxes method takes the Sale object as a parameter, so that the calculator can analyze
the sale. The implementation of each getTaxes method will be different: TaxMasterAdapter will
adapt the request to the API of Tax-Master, and so on.
UML Notice the interface and interface realization notation in Figure 25.1
.
Monopoly Problem: How to Design for Different Square Actions?
To review, when a player lands on the Go square, they receive $200. There's a different action for
landing on the Income Tax square, and so forth. Notice that there is a different rule for different
types of squares. Let's review the Polymorphism design principle:
When related alternatives or behaviors vary by type (class), assign responsibility for the
behaviorusing polymorphic operationsto the types for which the behavior varies. Corollary:
Do not test for the type of an object and use conditional logic to perform varying
alternatives based on type.
From the corollary, we know we should not design with case logic (a switch statement in Java or
C#) as in the following pseudocode:
   
// bad design
SWITCH ON square.type
CASE GoSquare: player receives $200
<<<PDF_PAGE 580>>>
CASE IncomeTaxSquare: player pays tax
…
Rather, the principle advises us to create a polymorphic operation for each type for which the
behavior varies. It varies for the types (classes) RegularSquare, GoSquare, and so on. What is
the operation that varies? It's what happens when a player lands on a square. Thus, a good name
for the polymorphic operation is landedOn or some variation. Therefore, by Polymorphism, we'll
create a separate class for each kind of square that has a different landedOn responsibility, and
implement a landedOn method in each. Figure 25.2
 illustrates the static-view class design.
Figure 25.2. Applying Polymorphism to the Monopoly problem.
[View full size image]
Applying UML: Notice in Figure 25.2
 the use of the {abstract} keyword for the landedOn
operation.
Guideline: Unless there is a default behavior in the superclass, declare a polymorphic operation
in the superclass to be {abstract}.
The remaining interesting problem is the dynamic design: How should the interaction diagrams
evolve? What object should send the landedOn message to the square that a player lands on?
Since a Player software object already knows its location square (the one it landed on), then by
the principles of Low Coupling and by Expert, class Player is a good choice to send the message,
as a Player already has visibility to the correct square.
Naturally, this message should be sent at the end of the takeTurn method. Please review the
iteration-1 takeTurn
 design on p. 355
 to see our starting point. Figure 25.3
 and Figure 25.4
illustrate the evolving dynamic design.
Figure 25.3. Applying Polymorphism.
[View full size image]
<<<PDF_PAGE 581>>>
Figure 25.4. The GoSquare case.
Applying UML:
UML frames
 p. 235
Notice in Figure 25.3
 and Figure 25.4
 the informal approach to showing the polymorphic
cases in separate diagrams when sketching UML. An alternativeespecially when using a UML
toolis to use sd and ref frames.
Notice in Figure 25.3
 that the Player object is labeled 'p' so that in the landedOn message
we can refer to that object in the parameter list. (You will see in Figure 25.4
 that it is useful
for the Square to have parameter visibility to the Player.)
<<<PDF_PAGE 582>>>
Notice in Figure 25.3
 that the Square object is labeled loc (short for 'location') and this is the
same label as the return value variable in the getSquare message. This implies they are the
same object.
Let's consider each of the polymorphic cases in terms of GRASP and the design issues:
GoSquare See Figure 25.4
. By low representational gap, the Player should know its cash.
Therefore, by Expert, it should be sent an addCash message. Thus the square needs
visibility to the Player so it can send the message; consequently, the Player is passed as a
parameter 'p' in the landedOn message to achieve parameter visibility.
RegularSquare See Figure 25.5
. In this case, nothing happens. I've informally labeled the
diagram to indicate this, though a UML note box could be used as well. In code, the body of
this method will be emptysometimes called a NO-OP (no operation) method. Note that to
make the magic of polymorphism work, we need to use this approach to avoid special case
logic.
Figure 25.5. The RegularSquare case.
IncomeTaxSquare See Figure 25.6
. We need to calculate 10% of the player's net worth. By
low representational gap and by Expert, who should know this? The Player. Thus the square
asks for the player's worth, and then deducts the appropriate amount.
Figure 25.6. The IncomeTaxSquare case.

<<<PDF_PAGE 583>>>
GoToJailSquare See Figure 25.7
. Simply, the Player's location must be changed. By Expert,
it should receive a setLocation message. Probably, the GoToJailSquare will be initialized with
an attribute referencing the JailSquare, so that it can pass this square as a parameter to the
Player.
Figure 25.7. The GoToJailSquare case.
UML as Sketch: Notice in Figure 25.4
 that the vertical lifeline is drawn as a solid line, rather than
the traditional dashed line. This is more convenient when hand sketching. Furthermore, UML 2
allows either formatalthough in any event conformance to correct UML is not so important when
sketching, only that the participants understand each other.
Improving the Coupling
As a small OO design refinement, notice in Figure 18.25
 on p. 357
 for iteration-1 that the Piece
remembers the square location but the Player does not, and thus the Player must extract the
location from the Piece (to send the getSquare message to the Board), and then re-assign the
new location to the Piece. That's a weak design point, and in this iteration, when the Player must
also send the landedOn message to its Square, it becomes even weaker. Why? What's wrong with
it? Answer: Problems in coupling.
Clearly the Player needs to permanently know its own Square location object rather than the
Piece, since the Player keeps collaborating with its Square. You should see this as a refactoring
opportunity to improve couplingwhen object A keeps needing the data in object B it implies either
1) object A should hold that data, or 2) object B should have the responsibility (by Expert) rather
than object A.
Therefore, in iteration-2 I've refined the design so that the Player rather than the Piece knows its
square; this is reflected in both the DCD of Figure 25.2
 and the interaction diagram of Figure
25.3
.
In fact, one can even question if the Piece is a useful object in the Design Model. In the real
world, a little plastic piece sitting on the board is a useful proxy for a human, because we're big
and go to the kitchen for cold beer! But in software, the Player object (being a tiny software blob)
can fulfill the role of the Piece.
Discussion
Polymorphism is a fundamental principle in designing how a system is organized to handle similar
variations. A design based on assigning responsibilities by Polymorphism can be easily extended
to handle new variations. For example, adding a new calculator adapter class with its own
<<<PDF_PAGE 584>>>
polymorphic getTaxes method will have minor impact on the existing design.
Guideline: When to Design with Interfaces?
Polymorphism implies the presence of abstract superclasses or interfaces in most OO languages.
When should you consider using an interface? The general answer is to introduce one when you
want to support polymorphism without being committed to a particular class hierarchy. If an
abstract superclass AC is used without an interface, any new polymorphic solution must be a
subclass of AC, which is very limiting in single-inheritance languages such as Java and C#. As a
rule-of-thumb, if there is a class hierarchy with an abstract superclass C1, consider making an
interface I1 that corresponds to the public method signatures of C1, and then declare C1 to
implement the I1 interface. Then, even if there is no immediate motivation to avoid subclassing
under C1 for a new polymorphic solution, there is a flexible evolution point for unknown future
cases.
Contraindications
Sometimes, developers design systems with interfaces and polymorphism for speculative "future-
proofing" against an unknown possible variation. If the variation point is definitely motivated by
an immediate or very probable variability, then the effort of adding the flexibility through
polymorphism is of course rational. But critical evaluation is required, because it is not uncommon
to see unnecessary effort being applied to future-proofing a design with polymorphism at
variation points that in fact are improbable and will never actually arise. Be realistic about the
true likelihood of variability before investing in increased flexibility.
Benefits
Extensions required for new variations are easy to add.
New implementations can be introduced without affecting clients.
Related Patterns
Protected Variations
A number of popular GoF design patterns [GHJV95
], which will be discussed in this book,
rely on polymorphism, including Adapter, Command, Composite, Proxy, State, and Strategy.
Also Known As; Similar To
Choosing Message, Don't Ask "What Kind?"
 

<<<PDF_PAGE 585>>>
 
25.2. Pure Fabrication
Problem
What object should have the responsibility, when you do not want to violate High Cohesion and
Low Coupling, or other goals, but solutions offered by Expert (for example) are not appropriate?
Object-oriented designs are sometimes characterized by implementing as software classes
representations of concepts in the real-world problem domain to lower the representational gap;
for example a Sale and Customer class. However, there are many situations in which assigning
responsibilities only to domain layer software classes leads to problems in terms of poor cohesion
or coupling, or low reuse potential.
Solution
Assign a highly cohesive set of responsibilities to an artificial or convenience class that does not
represent a problem domain conceptsomething made up, to support high cohesion, low coupling,
and reuse.
Such a class is a fabrication of the imagination. Ideally, the responsibilities assigned to this
fabrication support high cohesion and low coupling, so that the design of the fabrication is very
clean, or purehence a pure fabrication.
Finally, in English pure fabrication is an idiom that implies making something up, which we do
when we're desperate!
Examples
NextGen Problem: Saving a Sale Object in a Database
For example, suppose that support is needed to save Sale instances in a relational database. By
Information Expert, there is some justification to assign this responsibility to the Sale class itself,
because the sale has the data that needs to be saved. But consider the following implications:
The task requires a relatively large number of supporting database-oriented operations,
none related to the concept of sale-ness, so the Sale class becomes incohesive.
The Sale class has to be coupled to the relational database interface (such as JDBC in Java
technologies), so its coupling goes up. And the coupling is not even to another domain
object, but to a particular kind of database interface.
Saving objects in a relational database is a very general task for which many classes need
support. Placing these responsibilities in the Sale class suggests there is going to be poor
reuse or lots of duplication in other classes that do the same thing.
Thus, even though Sale is a logical candidate by virtue of Information Expert to save itself in a
database, it leads to a design with low cohesion, high coupling, and low reuse potentialexactly the
kind of desperate situation that calls for making something up.
<<<PDF_PAGE 586>>>
A reasonable solution is to create a new class that is solely responsible for saving objects in some
kind of persistent storage medium, such as a relational database; call it the PersistentStorage.[2]
This class is a Pure Fabricationa figment of the imagination.
[2] In a real persistence framework, more than a single pure fabrication class is ultimately necessary to create a reasonable
design. This object will be a front-end facade on to a large number of back-end helper objects.
Notice the name: PersistentStorage. This is an understandable concept, yet the name or concept
"persistent storage" is not something one would find in the Domain Model. And if a designer asked
a business-person in a store, "Do you work with persistent storage objects?" they would not
understand. They understand concepts such as "sale" and "payment." PersistentStorage is not a
domain concept, but something made up or fabricated for the convenience of the software
developer.
This Pure Fabrication solves the following design problems:
The Sale remains well-designed, with high cohesion and low coupling.
The PersistentStorage class is itself relatively cohesive, having the sole purpose of storing or
inserting objects in a persistent storage medium.
The PersistentStorage class is a very generic and reusable object.
Creating a pure fabrication in this example is exactly the situation in which their use is called
foreliminating a bad design based on Expert, with poor cohesion and coupling, with a good design
in which there is greater potential for reuse.
Note that, as with all the GRASP patterns, the emphasis is on where responsibilities should be
placed. In this example the responsibilities are shifted from the Sale class (motivated by Expert)
to a Pure Fabrication.
Monopoly Problem: Handling the Dice
In the refactoring chapter, I used the example of dice rolling behavior (rolling and summing the
dice totals) to apply Extract Method (p. 391
) in the Player.takeTurn method. At the end of the
example I also mentioned that the refactored solution itself was not ideal, and a better solution
would be presented later.
In the current design, the Player rolls all the dice and sums the total. Dice are very general
objects, usable in many games. By putting this rolling and summing responsibility in a Monopoly
game Player, the summing service is not generalized for use in other games. Another weakness:
It is not possible to simply ask for the current dice total without rolling the dice again.
But, choosing any other object inspired from the Monopoly game domain model leads to the same
problems. And that leads us to Pure Fabricationmake something up to conveniently provide
<<<PDF_PAGE 587>>>
related services.
Although there is no cup for the dice in Monopoly, many games do use a dice cup in which one
shakes all the dice and rolls them onto a table. Therefore, I propose a Pure Fabrication called Cup
(notice that I'm still trying to use similar domain-relevant vocabulary) to hold all the dice, roll
them, and know their total. The new design is shown in Figure 25.8
 and Figure 25.9
. The Cup
holds a collection of many Die objects. When one sends a roll message to a Cup, it sends a roll
message to all its dice.
Figure 25.8. DCD for a Cup.
Figure 25.9. Using the Cup in the Monopoly game.
Discussion
The design of objects can be broadly divided into two groups:
Those chosen by representational decomposition.1.
Those chosen by behavioral decomposition.2.
<<<PDF_PAGE 588>>>
1.
2.
For example, the creation of a software class such as Sale is by representational decomposition;
the software class is related to or represents a thing in a domain. Representational decomposition
is a common strategy in object design and supports the goal of low representational gap. But
sometimes, we desire to assign responsibilities by grouping behaviors or by algorithm, without
any concern for creating a class with a name or purpose that is related to a real-world domain
concept.
A good example is an "algorithm" object such as a TableOfContentsGenerator, whose purpose is
(surprise!) to generate a table of contents and was created as a helper or convenience class by a
developer, without any concern for choosing a name from the domain vocabulary of books and
documents. It exists as a convenience class conceived by the developer to group together some
related behavior or methods, and is thus motivated by behavioral decomposition.
To contrast, a software class named TableOfContents is inspired by representational
decomposition, and should contain information consistent with our concept of the real domain
(such as chapter names).
Identifying a class as a Pure Fabrication is not critical. It's an educational concept to communicate
the general idea that some software classes are inspired by representations of the domain, and
some are simply "made up" as a convenience for the object designer. These convenience classes
are usually designed to group together some common behavior, and are thus inspired by
behavioral rather than representational decomposition.
Said another way, a Pure Fabrication is usually partitioned based on related functionality, so it is a
kind of function-centric or behavioral object.
Many existing object-oriented design patterns are examples of Pure Fabrications: Adapter,
Strategy, Command, and so on [GHJV95
].
As a final comment worth reiterating: Sometimes a solution offered by Information Expert is not
desirable. Even though the object is a candidate for the responsibility by virtue of having much of
the information related to the responsibility, in other ways, its choice leads to a poor design,
usually due to problems in cohesion or coupling.
Benefits
High Cohesion is supported because responsibilities are factored into a fine-grained class
that only focuses on a very specific set of related tasks.
Reuse potential may increase because of the presence of fine-grained Pure Fabrication
classes whose responsibilities have applicability in other applications.
Contraindications
Behavioral decomposition into Pure Fabrication objects is sometimes overused by those new to
object design and more familiar with decomposing or organizing software in terms of functions. To
exaggerate, functions just become objects. There is nothing inherently wrong with creating
"function" or "algorithm" objects, but it needs to be balanced with the ability to design with
representational decomposition, such as the ability to apply Information Expert so that a
representational class such as Sale also has responsibilities. Information Expert supports the goal
of co-locating responsibilities with the objects that know the information needed for those
responsibilities, which tends to support lower coupling. If overused, Pure Fabrication could lead to
too many behavior objects that have responsibilities not co-located with the information required
for their fulfillment, which can adversely affect coupling. The usual symptom is that most of the
data inside the objects is being passed to other objects to reason with it.
Related Patterns and Principles
<<<PDF_PAGE 589>>>
Low Coupling.
High Cohesion.
A Pure Fabrication usually takes on responsibilities from the domain class that would be
assigned those responsibilities based on the Expert pattern.
All GoF design patterns [GHJV95
], such as Adapter, Command, Strategy, and so on, are
Pure Fabrications.
Virtually all other design patterns are Pure Fabrications.
 

<<<PDF_PAGE 590>>>
 
25.3. Indirection
Problem
Where to assign a responsibility, to avoid direct coupling between two (or more) things? How to
de-couple objects so that low coupling is supported and reuse potential remains higher?
Solution
Assign the responsibility to an intermediate object to mediate between other components or
services so that they are not directly coupled.
The intermediary creates an indirection between the other components.
Examples
TaxCalculatorAdapter
These objects act as intermediaries to the external tax calculators. Via polymorphism, they
provide a consistent interface to the inner objects and hide the variations in the external APIs. By
adding a level of indirection and adding polymorphism, the adapter objects protect the inner
design against variations in the external interfaces (see Figure 25.10
).
Figure 25.10. Indirection via the adapter.
[View full size image]
Applying UML: Notice how the external TaxMaster remote service application is modeled in
Figure 25.10
: It's labeled with the «actor» keyword to indicate it's an external software
component to our NextGen system.
PersistentStorage
<<<PDF_PAGE 591>>>
The Pure Fabrication example of decoupling the Sale from the relational database services
through the introduction of a PersistentStorage class is also an example of assigning
responsibilities to support Indirection. The PersistentStorage acts as a intermediary between the
Sale and the database.
Discussion
"Most problems in computer science can be solved by another level of indirection" is an old adage
with particular relevance to object-oriented designs. [3]
[3] By David Wheeler. Note there is also the counter-adage: "Most problems in performance can be solved by removing
another layer of indirection!"
Just as many existing design patterns are specializations of Pure Fabrication, many are also
specializations of Indirection. Adapter, Facade, and Observer are examples [GHJV95
]. In addition,
many Pure Fabrications are generated because of Indirection. The motivation for Indirection is
usually Low Coupling; an intermediary is added to decouple other components or services.
Benefits
Lower coupling between components.
Related Patterns and Principles
Protected Variations
Low Coupling
Many GoF patterns, such as Adapter, Bridge, Facade, Observer, and Mediator [GHJV95
].
Many Indirection intermediaries are Pure Fabrications.
 

<<<PDF_PAGE 592>>>
 
25.4. Protected Variations
Problem
How to design objects, subsystems, and systems so that the variations or instability in these
elements does not have an undesirable impact on other elements?
Solution
Identify points of predicted variation or instability; assign responsibilities to create a stable
interface around them.
Note: The term "interface" is used in the broadest sense of an access view; it does not literally
only mean something like a Java interface.
Example
For example, the prior external tax calculator problem and its solution with Polymorphism
illustrate Protected Variations (Figure 25.1
). The point of instability or variation is the different
interfaces or APIs of external tax calculators. The POS system needs to be able to integrate with
many existing tax calculator systems, and also with future third-party calculators not yet in
existence.
By adding a level of indirection, an interface, and using polymorphism with various
ITaxCalculatorAdapter implementations, protection within the system from variations in external
APIs is achieved. Internal objects collaborate with a stable interface; the various adapter
implementations hide the variations to the external systems.
Discussion
This is a very important, fundamental principle of software design! Almost every software or
architectural design trick in bookdata encapsulation, polymorphism, data-driven designs,
interfaces, virtual machines, configuration files, operating systems, and much moreis a
specialization of Protected Variations.
Protected Variations (PV) was first published as a named pattern by Cockburn in [VCK96
],
although this very fundamental design principle has been around for decades under various
terms, such as the term information hiding [Parnas72
].
Mechanisms Motivated by Protected Variations
PV is a root principle motivating most of the mechanisms and patterns in programming and
design to provide flexibility and protection from variationsvariations in data, behavior, hardware,
software components, operating systems, and more.
At one level, the maturation of a developer or architect can be seen in their growing knowledge of
ever-wider mechanisms to achieve PV, to pick the appropriate PV battles worth fighting, and their
ability to choose a suitable PV solution. In the early stages, one learns about data encapsulation,
interfaces, and polymorphismall core mechanisms to achieve PV. Later, one learns techniques
such as rule-based languages, rule interpreters, reflective and metadata designs, virtual
<<<PDF_PAGE 593>>>
machines, and so forthall of which can be applied to protect against some variation.
For example:
Core Protected Variations Mechanisms
Data encapsulation, interfaces, polymorphism, indirection, and standards are motivated by PV.
Note that components such as virtual machines and operating systems are complex examples of
indirection to achieve PV.
Data-Driven Designs
Data-driven designs cover a broad family of techniques including reading codes, values, class file
paths, class names, and so forth, from an external source in order to change the behavior of, or
"parameterize" a system in some way at run-time. Other variants include style sheets, metadata
for object-relational mapping, property files, reading in window layouts, and much more. The
system is protected from the impact of data, metadata, or declarative variations by externalizing
the variant, reading it in, and reasoning with it.
Service Lookup
Service lookup includes techniques such as using naming services (for example, Java's JNDI) or
traders to obtain a service (for example, Java's Jini, or UDDI for Web services). Clients are
protected from variations in the location of services, using the stable interface of the lookup
service. It is a special case of data-driven design.
Interpreter-Driven Designs
Interpreter-driven designs include rule interpreters that execute rules read from an external
source, script or language interpreters that read and run programs, virtual machines, neural
network engines that execute nets, constraint logic engines that read and reason with constraint
sets, and so forth. This approach allows changing or parameterizing the behavior of a system via
external logic expressions. The system is protected from the impact of logic variations by
externalizing the logic, reading it in, and using an interpreter.
Reflective or Meta-Level Designs
An example of this approach is using the java.beans.Introspector to obtain a BeanInfo object,
asking for the getter Method object for bean property X, and calling Method.invoke. The system is
protected from the impact of logic or external code variations by reflective algorithms that use
introspection and meta-language services. It may be considered a special case of data-driven
designs.
Uniform Access
Some languages, such as Ada, Eiffel, and C#, support a syntactic construct so that both a method
and field access are expressed the same way. For example, aCircle.radius may invoke a
<<<PDF_PAGE 594>>>
radius():float method or directly refer to a public field, depending on the definition of the class.
We can change from public fields to access methods, without changing the client code.
Standard Languages
Official language standards such as SQL provide protection against a proliferation of varying
languages.
The Liskov Substitution Principle (LSP)
LSP [Liskov88
] formalizes the principle of protection against variations in different
implementations of an interface, or subclass extensions of a superclass.
To quote:
What is wanted here is something like the following substitution property: If for each object
o1 of type S there is an object o2 of type T such that for all programs P defined in terms of
T, the behavior of P is unchanged when o1 is substituted for o2 then S is a subtype of T
[Liskov88
].
Informally, software (methods, classes, …) that refers to a type T (some interface or abstract
superclass) should work properly or as expected with any substituted implementation or subclass
of Tcall it S. For example:
public void addTaxes( ITaxCalculatorAdapter calculator, Sale sale )
{
   
List taxLineItems = calculator.getTaxes( sale );
   
// ...
}
For this method addTaxes, no matter what implementation of ITaxCalculatorAdapter is passed in
as an actual parameter, the method should continue to work "as expected." LSP is a simple idea,
intuitive to most object developers, that formalizes this intuition.
Structure-Hiding Designs
In the first edition of this book, an important, classic object design principle called Don't Talk to
Strangers or the Law of Demeter [Lieberherr88
] was expressed as one of the nine GRASP
patterns. Briefly, it means to avoid creating designs that traverse long object structure paths and
send messages (or talk) to distant, indirect (stranger) objects. Such designs are fragile with
respect to changes in the object structuresa common point of instability. But in the second edition
the more general PV replaced Don't Talk to Strangers, because the latter is a special case of the
former. That is, a mechanism to achieve protection from structure changes is to apply the Don't
Talk to Strangers rules.
Don't Talk to Strangers places constraints on what objects you should send messages to within a
method. It states that within a method, messages should only be sent to the following objects:
The this object (or self).1.
2.
3.
<<<PDF_PAGE 595>>>
1.
A parameter of the method.2.
An attribute of this.3.
An element of a collection which is an attribute of this.4.
An object created within the method.5.
The intent is to avoid coupling a client to knowledge of indirect objects and the object connections
between objects.
Direct objects are a client's "familiars," indirect objects are "strangers." A client should talk to
familiars, and avoid talking to strangers.
Here is an example that (mildly) violates Don't Talk to Strangers. The comments explain the
violation.
class Register
{
private Sale sale;
public void slightlyFragileMethod()
{
   
// sale.getPayment() sends a message to a "familiar" (passes #3)
   
// but in sale.getPayment().getTenderedAmount()
   
// the getTenderedAmount() message is to a "stranger" Payment
   
Money amount = sale.getPayment().getTenderedAmount();
   
// ...
}
   
// ...
}
This code traverses structural connections from a familiar object (the Sale) to a stranger object
(the Payment), and then sends it a message. It is very slightly fragile, as it depends on the fact
that Sale objects are connected to Payment objects. Realistically, this is unlikely to be a problem.
But, consider this next fragment, which traverses farther along the structural path:
public void moreFragileMethod()
{
   
AccountHolder holder =
      
sale.getPayment().getAccount().getAccountHolder();
   
// …
}
Or more generally:
<<<PDF_PAGE 596>>>
public void doX()
{
   
F someF =
      
foo.getA().getB().getC().getD().getE().getF();
   
// …
}
The example is contrived, but you see the pattern: Traversing farther along a path of object
connections in order to send a message to a distant, indirect objecttalking to a distant stranger.
The design is coupled to a particular structure of how objects are connected. The farther along a
path the program traverses, the more fragile it is. Why? Because the object structure (the
connections) may change. This is especially true in young applications or early iterations.
Karl Lieberherr and his colleagues have done research into good object design principles, under
the umbrella of the Demeter project. This Law of Demeter (Don't Talk to Strangers) was identified
because of the frequency with which they saw change and instability in object structure, and thus
frequent breakage in code that was coupled to knowledge of object connections.
Yet, as will be examined in the following "Speculative PV and Picking your Battles
" section, it is
not always necessary to protect against this; it depends on the instability of the object structure.
In standard libraries (such as the Java libraries) the structural connections between classes of
objects are relatively stable. In mature systems, the structure is more stable. In new systems in
early iteration, it isn't stable.
In general, the farther along a path one traverses, the more fragile it is, and thus it is more useful
to conform to Don't Talk to Strangers.
Strictly obeying this lawprotection against structural variationsrequires adding new public
operations to the "familiars" of an object; these operations provide the ultimately desired
information, and hide how it was obtained. For example, to support Don't Talk to Strangers for
the previous two cases:
// case 1
Money amount = sale.getTenderedAmountOfPayment();
// case 2
AccountHolder holder = sale.getAccountHolderOfPayment();
Contraindications
Caution: Speculative PV and Picking Your Battles
First, two points of change are worth defining:
variation pointVariations in the existing, current system or requirements, such as the
multiple tax calculator interfaces that must be supported.
evolution pointSpeculative points of variation that may arise in the future, but which are
<<<PDF_PAGE 597>>>
not present in the existing requirements.[4]
[4] In the UP, evolution points can be formally documented in Change Cases; each describes relevant aspects of an
evolution point for the benefit of a future architect.
PV is applied to both variation and evolution points.
A caution: Sometimes the cost of speculative "future-proofing" at evolution points outweighs the
cost incurred by a simple, more "brittle" design that is reworked as necessary in response to the
true change pressures. That is, the cost of engineering protection at evolution points can be
higher than reworking a simple design.
For example, I recall a pager message-handling system where the architect added a scripting
language and interpreter to support flexibility and protected variation at an evolution point.
However, during rework in an incremental release, the complex (and inefficient) scripting was
removedit simply wasn't needed. And when I started OO programming (in the early 1980s) I
suffered the disease of "generalize-itis" in which I tended to spend many hours creating
superclasses of the classes I really needed to write. I would make everything very general and
flexible (and protected against variations), for that future situation when it would really pay
offwhich never came. I was a poor judge of when it was worth the effort.
The point is not to advocate rework and brittle designs. If the need for flexibility and protection
from change is realistic, then applying PV is motivated. But if it is for speculative future-proofing
or speculative "reuse" with very uncertain probabilities, then restraint and critical thinking is
called for.
Novice developers tend toward brittle designs, intermediate developers tend toward overly fancy
and flexible, generalized ones (in ways that never get used). Expert designers choose with
insight; perhaps a simple and brittle design whose cost of change is balanced against its
likelihood.
Benefits
Extensions required for new variations are easy to add.
New implementations can be introduced without affecting clients.
Coupling is lowered.
The impact or cost of changes can be lowered.
Related Patterns and Principles
Most design principles and patterns are mechanisms for protected variation, including
polymorphism, interfaces, indirection, data encapsulation, most of the GoF design patterns,
and so on.
In [Pree95
] variation and evolution points are called "hot spots."
Also Known As; Similar To
PV is essentially the same as the information hiding and open-closed principles, which are older
terms. As an "official" pattern in the pattern community, it was named "Protected Variations" in
1996 by Cockburn in [VCK96
].
<<<PDF_PAGE 598>>>
Information Hiding
David Parnas's famous paper On the Criteria To Be Used in Decomposing Systems Into Modules
[Parnas72
] is an example of classics often cited but seldom read. In it, Parnas introduces the
concept of information hiding. Perhaps because the term sounds like the idea of data
encapsulation, it has been misinterpreted as data encapsulation, and some books erroneously
define the concepts as synonyms. Rather, Parnas intended information hiding to mean hide
information about the design from other modules, at the points of difficulty or likely change. To
quote his discussion of information hiding as a guiding design principle:
We propose instead that one begins with a list of difficult design decisions or design decisions
which are likely to change. Each module is then designed to hide such a decision from the
others.
That is, Parnas's information hiding is the same principle expressed in PV, and not simply data
encapsulationwhich is but one of many techniques to hide information about the design. However,
the term has been so widely reinterpreted as a synonym for data encapsulation that it is no
longer possible to use it in its original sense without misunderstanding.
Open-Closed Principle
The Open-Closed Principle (OCP), described by Bertrand Meyer in [Meyer88
], is essentially
equivalent to the PV pattern and to information hiding. A definition of OCP is:
Modules should be both open (for extension; adaptable) and closed (the module is closed to
modification in ways that affect clients).
OCP and PV are essentially two expressions of the same principle, with different emphasis:
protection at variation and evolution points. In OCP, "module" includes all discrete software
elements, including methods, classes, subsystems, applications, and so forth.
In the context of OCP, the phrase "closed with respect to X" means that clients are not affected if
X changes. For example, "the class is closed with respect to instance field definitions" through the
mechanism of data encapsulation with private fields and public accessing methods. At the same
time, they are open to modifying the definitions of the private data, because outside clients are
not directly coupled to the private data.
As another example, "the tax calculator adapters are closed with respect to their public interface"
through implementing the stable ITaxCalculatorAdapter interface. However, the adapters are
open to extension by being privately modified in response to changes in the APIs of the external
tax calculators, in ways that do not break their clients.
 

# Chapter 26. Applying GoF Design Patterns


<<<PDF_PAGE 599>>>
 
Chapter 26. Applying GoF Design
Patterns
The shift of focus (to patterns) will have a profound and enduring effect on the way we write
programs.
Ward Cunningham and Ralph Johnson
Objectives
Introduce and apply some GoF design patterns.
Show GRASP principles as a generalization of other design patterns.
 

<<<PDF_PAGE 600>>>
 
Introduction
This chapter explores OO design for use-case realizations for the NextGen case study, providing
support for external third-party services whose interfaces may vary, more complex product
pricing rules, and pluggable business rules. The emphasis is to show how to apply the Gang-of-
Four (GoF) and the more basic GRASP patterns. It illustrates that object design and the
assignment of responsibilities can be explained and learned based on the application of patternsa
vocabulary of principles and idioms that can be combined to design objects.
[View full size image]
Some of the 23 GoF design patterns are introduced here, but more are also covered in later
chapters, including:
"More Object Design with GoF Patterns
" on page 579
"Designing a Persistence Framework with Patterns
" on page 625
The Gang-of-Four Design Patterns
GoF design patterns, and their seminal influence, were first introduced on p. 280
. As a brief
review, these were first described in Design Patterns [GHJV95
], a seminal and extremely popular
work that presents 23 patterns useful during object design.
Not all of the 23 patterns are widely used; perhaps 15 are common and most useful.
A thorough study of the Design Patterns book is recommended to grow as an object designer,
although that book assumes the reader is already an OO designer with significant experienceand
has a background in C++ and Smalltalk. In contrast, this book offers an introduction.
 

<<<PDF_PAGE 601>>>
 
26.1. Adapter (GoF)
The NextGen problem explored on p. 414
 to motivate the Polymorphism pattern and its solution is
more specifically an example of the GoF Adapter pattern.
Name:
Adapter
Problem:
How to resolve incompatible interfaces, or provide a stable interface to similar
components with different interfaces?
Solution:
(advice)
Convert the original interface of a component into another interface, through
an intermediate adapter object.
To review: The NextGen POS system needs to support several kinds of external third-party
services, including tax calculators, credit authorization services, inventory systems, and
accounting systems, among others. Each has a different API, which can't be changed.
A solution is to add a level of indirection with objects that adapt the varying external interfaces to
a consistent interface used within the application. The solution is illustrated in Figure 26.1
.
Figure 26.1. The Adapter pattern.
[View full size image]

<<<PDF_PAGE 602>>>
As illustrated in Figure 26.2
, a particular adapter instance will be instantiated for the chosen
external service[1]
 , such as SAP for accounting, and will adapt the postSale request to the
external interface, such as a SOAP XML interface over HTTPS for an intranet Web service offered
by SAP.
[1] In the J2EE Connector Architecture, these adapters to external services are more specifically called resource adapters.
Figure 26.2. Using an Adapter.
[View full size image]
Guideline: Include Pattern in Type Name
Notice that the type names include the pattern name "Adapter." This is a relatively
common style and has the advantage of easily communicating to others reading the
code or diagrams what design patterns are being used.
Related Patterns
A resource adapter that hides an external system may also be considered a Facade object
(another GoF pattern discussed in this chapter), as it wraps access to the subsystem or system
with a single object (which is the essence of Facade). However, the motivation to call it a resource
adapter especially exists when the wrapping object provides adaptation to varying external
interfaces.
 

<<<PDF_PAGE 603>>>
 
26.2. Some GRASP Principles as a Generalization of
Other Patterns
The previous use of the Adapter pattern can be viewed as a specialization of some GRASP building
blocks:
Adapter supports Protected Variations with respect to changing external interfaces or third-
party packages through the use of an Indirection object that applies interfaces and
Polymorphism.
What's the Problem? Pattern Overload!
The Pattern Almanac 2000 [Rising00
] lists around 500 design patterns. And many hundreds more
have been published since then. The curious developer has no time to actually program given this
reading list!
A Solution: See the Underlying Principles
Yes, it's important for an experienced designer to know in detail and by memory 50+ of the most
important design patterns, but few of us can learn or remember 1,000 patterns, or even start to
organize that pattern plethora into a useful taxonomy.
But there's good news: Most design patterns can be seen as specializations of a few basic GRASP
principles. Although it is indeed helpful to study detailed design patterns to accelerate learning, it
is even more helpful to see their underlying basic themes (Protected Variations, Polymorphism,
Indirection, …) to help us to cut through the myriad details and see the essential "alphabet" of
design techniques being applied.
Example: Adapter and GRASP
Figure 26.1
 illustrates my point that detailed design patterns can be analyzed in terms of the
basic underlying "alphabet" of GRASP principles. UML generalization relationships are used to
suggest the conceptual connections. At this point perhaps this idea seems academic or overly
analytical. But it is truly the case that as you spend some years applying and reflecting on myriad
design patterns, you will increasingly come to feel that it's the underlying themes that are
important, and the fine details of Adapter or Strategy or whatever will become secondary.
Figure 26.3. Relating Adapter to some core GRASP principles.
[View full size image]
<<<PDF_PAGE 604>>>
 

<<<PDF_PAGE 605>>>
 
26.3. "Analysis" Discoveries During Design: Domain
Model
Observe that in the Adapter design in Figure 26.1
, the getTaxes operation returns a list of
TaxLineItems. That is, on deeper reflection and investigation of how taxes are handled and tax
calculators work, the modeler (me) realized that a list of tax line items are associated with a sale,
such as state tax, federal tax, and so forth (there is always the chance governments will invent
new taxes!).
In addition to being a newly created software class in the Design Model, this is a domain concept.
It is normal and common to discover noteworthy domain concepts and refined understanding of
the requirements during design or programmingiterative development supports this kind of
incremental discovery.
Should this discovery be reflected in the Domain Model (or Glossary)? If the Domain Model will be
used in the future as a source of inspiration for later design work, or as a visual learning aid to
communicate the key domain concepts, then adding it could have value. Figure 26.4
 illustrates an
updated Domain Model.
Figure 26.4. Updated partial Domain Model.
 

<<<PDF_PAGE 606>>>
 
26.4. Factory
This is also called Simple Factory or Concrete Factory. This pattern is not a GoF design
pattern, but extremely widespread. It is also a simplification of the GoF Abstract Factory pattern
(p. 597
), and often described as a variation of Abstract Factory, although that's not strictly
accurate. Nevertheless, because of its prevalence and association with GoF, it is presented now.
The adapter raises a new problem in the design: In the prior Adapter pattern solution for external
services with varying interfaces, who creates the adapters? And how to determine which class of
adapter to create, such as TaxMaster-Adapter or GoodAsGoldTaxProAdapter?
If some domain object creates them, the responsibilities of the domain object are going beyond
pure application logic (such as sales total calculations) and into other concerns related to
connectivity with external software components.
This point underscores another fundamental design principle (usually considered an architectural
design principle): Design to maintain a separation of concerns. That is, modularize or separate
distinct concerns into different areas, so that each has a cohesive purpose. Fundamentally, it is an
application of the GRASP High Cohesion principle. For example, the domain layer of software
objects emphasizes relatively pure application logic responsibilities, whereas a different group of
objects is responsible for the concern of connectivity to external systems.
Therefore, choosing a domain object (such as a Register) to create the adapters does not support
the goal of a separation of concerns, and lowers its cohesion.
A common alternative in this case is to apply the Factory pattern, in which a Pure Fabrication
"factory" object is defined to create objects.
Factory objects have several advantages:
Separate the responsibility of complex creation into cohesive helper objects.
Hide potentially complex creation logic.
Allow introduction of performance-enhancing memory management strategies, such as
object caching or recycling.
Name:
Factory
Problem:
Who should be responsible for creating objects when there are special
considerations, such as complex creation logic, a desire to separate the
creation responsibilities for better cohesion, and so forth?
Solution:
(advice)
Create a Pure Fabrication object called a Factory that handles the creation.
A Factory solution is illustrated in Figure 26.5
.
<<<PDF_PAGE 607>>>
Figure 26.5. The Factory pattern.
[View full size image]
Note that in the ServicesFactory, the logic to decide which class to create is resolved by reading in
the class name from an external source (for example, via a system property if Java is used) and
then dynamically loading the class. This is an example of a partial data-driven design. This
design achieves Protected Variations with respect to changes in the implementation class of the
adapter. Without changing the source code in this factory class, we can create instances of new
adapter classes by changing the property value and ensuring that the new class is visible in the
Java class path for loading.
Related Patterns
Factories are often accessed with the Singleton pattern.
 

<<<PDF_PAGE 608>>>
 
26.5. Singleton (GoF)
The ServicesFactory raises another new problem in the design: Who creates the factory itself, and
how is it accessed?
First, observe that only one instance of the factory is needed within the process. Second, quick
reflection suggests that the methods of this factory may need to be called from various places in
the code, as different places need access to the adapters for calling on the external services.
Thus, there is a visibility problem: How to get visibility to this single ServicesFactory instance?
One solution is pass the ServicesFactory instance around as a parameter to wherever a visibility
need is discovered for it, or to initialize the objects that need visibility to it, with a permanent
reference. This is possible but inconvenient; an alternative is the Singleton pattern.
Occasionally, it is desirable to support global visibility or a single access point to a single instance
of a class rather than some other form of visibility. This is true for the ServicesFactory instance.
Name:
Singleton
Problem:
Exactly one instance of a class is allowedit is a "singleton." Objects need a
global and single point of access.
Solution:
(advice)
Define a static method of the class that returns the singleton.
For example, Figure 26.6
 shows an implementation of the Singleton pattern.
Figure 26.6. The Singleton pattern in the ServicesFactory class.
[View full size image]
<<<PDF_PAGE 609>>>
Applying UML: Notice how a singleton is illustrated, with a '1' in the top right corner of the name
compartment.
Thus, the key idea is that class X defines a static method getInstance that itself provides a single
instance of X.
With this approach, a developer has global visibility to this single instance, via the static
getInstance method of the class, as in this example:
public class Register
{
public void initialize()
{
   
… do some work …
   
// accessing the singleton Factory via the getInstance call
   
accountingAdapter =
      
ServicesFactory.getInstance().getAccountingAdapter();
   
… do some work …
}
// other methods…
} // end of class
Since visibility to public classes is global in scope (in most languages), at any point in the code, in
any method of any class, one can write
<<<PDF_PAGE 610>>>
SingletonClass.getInstance()
in order to obtain visibility to the singleton instance, and then send it a message, such as
SingletonClass.getInstance().doFoo(). And it's hard to beat the feeling of being able to globally
doFoo!
Implementation and Design Issues
A Singleton getInstance method is often frequently called. In multi-threaded applications, the
creation step of the lazy initialization logic is a critical section requiring thread concurrency
control. Thus, assuming the instance is lazy initialized, it is common to wrap the method with
concurrency control. In Java, for example:
public static 
synchronized
 
ServicesFactory getInstance()
public static 
synchronized
 
ServicesFactory getInstance()
{
   
if ( instance == null )
   
{
      
// critical section if multithreaded application
      
instance = new ServicesFactory();
   
}
   
return instance;
}
On the subject of lazy initialization, why not prefer eager initialization, as in this example?
public class ServicesFactory
{
// eager initialization
private static ServicesFactory instance =
   
new ServicesFactory();
public static ServicesFactory getInstance()
{
   
return instance;
}
// other methods...
}
The first approach of lazy initialization is usually preferred for at least these reasons:
Creation work (and perhaps holding on to "expensive" resources) is avoided, if the instance
is never actually accessed.
The getInstance lazy initialization sometimes contains complex and conditional creation
<<<PDF_PAGE 611>>>
logic.
Figure 26.7. Implicit getInstance Singleton pattern message indicated
in the UML because of the '1' mark.
[View full size image]
Another common Singleton implementation question is: Why not make all the service methods
static methods of the class itself, instead of using an instance object with instance-side methods?
For example, what if we add a static method called getAccountingAdapter to ServicesFactory. But,
an instance and instance-side methods are usually preferred for these reasons:
Instance-side methods permit subclassing and refinement of the singleton class into
subclasses; static methods are not polymorphic (virtual) and don't permit overriding in
subclasses in most languages (Smalltalk excluded).
Most object-oriented remote communication mechanisms (for example, Java's RMI) only
support remote-enabling of instance methods, not static methods. A singleton instance could
be remote-enabled, although that is admittedly rarely done.
A class is not always a singleton in all application contexts. In application X, it may be a
singleton, but it may be a "multi-ton" in application Y. It is also not uncommon to start off a
design thinking the object will be a singleton, and then discovering a need for multiple
instances in the same process. Thus, the instance-side solution offers flexibility.
Related Patterns
The Singleton pattern is often used for Factory objects and Facade objectsanother GoF pattern
that will be discussed.
 

<<<PDF_PAGE 612>>>
 
26.6. Conclusion of the External Services with Varying
Interfaces Problem
A combination of Adapter, Factory, and Singleton patterns have been used to provide Protected
Variations from the varying interfaces of external tax calculators, accounting systems, and so
forth. Figure 26.8
 illustrates a larger context of using these in the use-case realization.
Figure 26.8. Adapter, Factory, and Singleton patterns applied to the
design.
[View full size image]
This design may not be ideal, and there is always room for improvement. But one of the goals
strived for in this case study is to illustrate that at least a design can be constructed from a set of
principles or pattern "building blocks," and that there is a methodical approach to doing and
explaining a design. It is my sincere hope that it is possible to see how the design in Figure 26.8
arose from reasoning based on Controller, Creator, Protected Variations, Low Coupling, High
Cohesion, Indirection, Polymorphism, Adapter, Factory, and Singleton.
Note how succinct a designer can be in conversation or documentation when there is a shared
understanding of patterns. I can say, "To handle the problem of varying interfaces for external
services, let's use Adapters generated from a Singleton Factory." Object designers really do have
conversations that sound like this; using patterns and pattern names supports raising the level of
abstraction in design communication.
 

<<<PDF_PAGE 613>>>
 
26.7. Strategy (GoF)
The next design problem to be resolved is to provide more complex pricing logic, such as a store-
wide discount for the day, senior citizen discounts, and so forth.
The pricing strategy (which may also be called a rule, policy, or algorithm) for a sale can vary.
During one period it may be 10% off all sales, later it may be $10 off if the sale total is greater
than $200, and myriad other variations. How do we design for these varying pricing algorithms?
Name:
Strategy
Problem:
How to design for varying, but related, algorithms or policies? How to design
for the ability to change these algorithms or policies?
Solution:
(advice)
Define each algorithm/policy/strategy in a separate class, with a common
interface.
Since the behavior of pricing varies by the strategy (or algorithm), we create multiple
SalePricingStrategy classes, each with a polymorphic getTotal method (see Figure 26.9
). Each
getTotal method takes the Sale object as a parameter, so that the pricing strategy object can find
the pre-discount price from the Sale, and then apply the discounting rule. The implementation of
each getTotal method will be different: PercentDiscountPricingStrategy will discount by a
percentage, and so on.
Figure 26.9. Pricing Strategy classes.
[View full size image]
<<<PDF_PAGE 614>>>
A strategy object is attached to a context objectthe object to which it applies the algorithm. In
this example, the context object is a Sale. When a getTotal message is sent to a Sale, it delegates
some of the work to its strategy object, as illustrated in Figure 26.10
. It is not required that the
message to the context object and the strategy object have the same name, as in this example
(for example, getTotal and getTotal), but it is common. However, it is commonindeed, usually
requiredthat the context object pass a reference to itself (this) on to the strategy object, so that
the strategy has parameter visibility to the context object, for further collaboration.
Figure 26.10. Strategy in collaboration.
[View full size image]
Observe that the context object (Sale) needs attribute visibility to its strategy. This is reflected in
the DCD in Figure 26.11
.
Figure 26.11. Context object needs attribute visibility to its strategy.
<<<PDF_PAGE 615>>>
[View full size image]
Creating a Strategy with a Factory
There are different pricing algorithms or strategies, and they change over time. Who should
create the strategy? A straightforward approach is to apply the Factory pattern again: A
PricingStrategyFactory can be responsible for creating all strategies (all the pluggable or changing
algorithms or policies) needed by the application. As with the ServicesFactory, it can read the
name of the implementation class of the pricing strategy from a system property (or some
external data source), and then make an instance of it. With this partial data-driven design (or
reflective design) one can dynamically change at any timewhile the NextGen POS application is
runningthe pricing policy, by specifying a different class of Strategy to create.
Observe that a new factory was used for the strategies; that is, different than the
ServicesFactory. This supports the goal of High Cohesioneach factory is cohesively focused on
creating a related family of objects.
UML Observe that in Figure 26.11
 the reference via a directed association is to the interface
ISalePricingStrategy, not to a concrete class. This indicates that the reference attribute in the
Sale will be declared in terms of the interface, not a class, so that any implementation of the
interface can be bound to the attribute.
Note that because of the frequently changing pricing policy (it could be every hour), it is not
desirable to cache the created strategy instance in a field of the PricingStrategyFactory, but
rather to re-create one each time, by reading the external property for its class name, and then
instantiating the strategy.
And as with most factories, the PricingStrategyFactory will be a singleton (one instance) and
accessed via the Singleton pattern (see Figure 26.12
).
Figure 26.12. Factory for strategies.
<<<PDF_PAGE 616>>>
When a Sale instance is created, it can ask the factory for its pricing strategy, as shown in Figure
26.13
.
Figure 26.13. Creating a strategy.
[View full size image]
Reading and Initializing the Percentage Value
Finally, a design problem that has been ignored until now is the issue of how to find the different
numbers for the percentage or absolute discounts. For example, on Monday, the
PercentageDiscountPricingStrategy may have a percentage value of 10%, but 20% on Tuesday.
Note also that a percentage discount may be related to the type of buyer, such as a senior citizen,
rather than to a time period.
These numbers will be stored in some external data store, such as a relational database, so they
can be easily changed. So, what object will read them and ensure they are assigned to the
strategy? A reasonable choice is the StrategyFactory itself, since it is creating the pricing strategy,
and can know which percentage to read from a data store ("current store discount," "senior
discount," and so forth).
<<<PDF_PAGE 617>>>
Designs to read these numbers from external data stores vary from the simple to the complex,
such as a plain JDBC SQL call (if Java technologies, as an example) or collaborating with objects
that add levels of indirection in order to hide the particular location, data query language, or type
of data store. Analyzing the variation and evolution points with respect to the data store will
reveal if there is a need for protected variation. For example, we could ask, "Are we all
comfortable with a long-term commitment to using a relational database that understands SQL?".
If so, a simple JDBC call from within the StrategyFactory may suffice.
Summary
Protected Variations with respect to dynamically changing pricing policies has been achieved with
the Strategy and Factory patterns. Strategy builds on Polymorphism and interfaces to allow
pluggable algorithms in an object design.
Related Patterns
Strategy is based on Polymorphism, and provides Protected Variations with respect to changing
algorithms. Strategies are often created by a Factory.
 

<<<PDF_PAGE 618>>>
 
26.8. Composite (GoF) and Other Design Principles
To raise yet another interesting requirements and design problem: How do we handle the case of
multiple, conflicting pricing policies? For example, suppose a store has the following policies in
effect today (Monday):
20% senior discount policy
preferred customer discount of 15% off sales over $400
on Monday, there is $50 off purchases over $500
buy 1 case of Darjeeling tea, get 15% discount off of everything
Suppose a senior who is also a preferred customer buys 1 case of Darjeeling tea, and $600 of
veggieburgers (clearly an enthusiastic vegetarian who loves chai). What pricing policy should be
applied?
To clarify: There are now pricing strategies that attach to the sale by virtue of three factors:
time period (Monday)1.
customer type (senior)2.
a particular line item product (Darjeeling tea)3.
Another point of clarification: Three of the four example policies are really just "percentage
discount" strategies, which simplifies our view of the problem.
Part of the answer to this problem requires defining the store's conflict resolution strategy.
Usually, a store applies the "best for the customer" (lowest price) conflict resolution strategy, but
this is not required, and it could change. For example, during a difficult financial period, the store
may have to use a "highest price" conflict resolution strategy.
The first point to note is that there can exist multiple co-existing strategies, that is, one sale may
have several pricing strategies. Another point to note is that a pricing strategy can be related to
the type of customer (for example, a senior). This has creation design implications: The customer
type must be known by the StrategyFactory at the time of creation of a pricing strategy for the
customer.
Similarly, a pricing strategy can be related to the type of product being bought (for example,
Darjeeling tea). This likewise has creation design implications: The ProductDescription must be
known by the StrategyFactory at the time of creation of a pricing strategy influenced by the
product.
Is there a way to change the design so that the Sale object does not know if it is dealing with one
or many pricing strategies, and also offer a design for the conflict resolution? Yes, with the
Composite pattern.
<<<PDF_PAGE 619>>>
Name:
Composite
Problem:
How to treat a group or composition structure of objects the same way
(polymorphically) as a non-composite (atomic) object?
Solution:
(advice)
Define classes for composite and atomic objects so that they implement the
same interface.
For example, a new class called CompositeBestForCustomerPricingStrategy (well, at least it's
descriptive) can implement the ISalesPricingStrategy and itself contain other
ISalesPricingStrategy objects. Figure 26.14
 explains the design idea in detail.
Figure 26.14. The Composite pattern.
[View full size image]

<<<PDF_PAGE 620>>>
Observe that in this design, the composite classes such as
CompositeBestForCustomerPricingStrategy inherit an attribute pricingStrategies that contains a
list of more ISalePricingStrategy objects. This is a signature feature of a composite object: The
outer composite object contains a list of inner objects, and both the outer and inner objects
implement the same interface. That is, the composite class itself implements the
ISalePricingStrategy interface.
Thus, we can attach either a composite CompositeBestForCustomerPricingStrategy object (which
contains other strategies inside of it) or an atomic PercentDiscountPricingStrategy object to the
Sale object, and the Sale does not know or care if its pricing strategy is an atomic or composite
strategyit looks the same to the Sale object. It is just another object that implements the
ISalePricingStrategy interface and understands the getTotal message (Figure 26.15
).
Figure 26.15. Collaboration with a Composite.
[View full size image]
UML In Figure 26.15
, please note a way to indicate objects that implement an interface, when we
don't care to specify the exact implementation class.
To clarify with some sample code in Java, the CompositePricingStrategy and one of its subclasses
are defined as follows:
// superclass so all subclasses can inherit a List of strategies
public abstract class CompositePricingStrategy
   
implements ISalePricingStrategy
{
protected List strategies = new ArrayList();
public add( ISalePricingStrategy s )
{
   
strategies.add( s );
<<<PDF_PAGE 621>>>
}
public abstract Money getTotal( Sale sale );
} // end of class
// a Composite Strategy that returns the lowest total
// of its inner SalePricingStrategies
public class CompositeBestForCustomerPricingStrategy
   
extends CompositePricingStrategy
{
public Money getTotal( Sale sale )
{
   
Money lowestTotal = new Money( Integer.MAX_VALUE );
   
// iterate over all the inner strategies
   
for( Iterator i = strategies.iterator(); i.hasNext(); )
   
{
      
ISalePricingStrategy strategy =
         
(ISalePricingStrategy)i.next();
      
Money total = strategy.getTotal( sale );
      
lowestTotal = total.min( lowestTotal );
   
}
return lowestTotal;
}
} // end of class
Figure 26.16. Abstract superclasses, abstract methods, and
inheritance in the UML.
[View full size image]
<<<PDF_PAGE 622>>>
Creating Multiple SalePricingStrategies
With the Composite pattern, we have made a group of multiple (and conflicting) pricing strategies
look to the Sale object like a single pricing strategy. The composite object that contains the group
also implements the ISalePricingStrategy interface. The more challenging (and interesting) part of
this design problem is: When do we create these strategies?
A desirable design will start by creating a Composite that contains the present moment's store
discount policy (which could be set to 0% discount if none is active), such as some
PercentageDiscountPricingStrategy. Then, if at a later step in the scenario, another pricing
strategy is discovered to also apply (such as senior discount), it will be easy to add it to the
composite, using the inherited CompositePricingStrategy.add method.
There are three points in the scenario where pricing strategies may be added to the composite:
Current store-defined discount, added when the sale is created.1.
Customer type discount, added when the customer type is communicated to the POS.2.
Product type discount (if bought Darjeeling tea, 15% off the overall sale), added when the
product is entered to the sale.
3.
The design of the first case is shown in Figure 26.17
. As in the original design discussed earlier,
the strategy class name to instantiate could be read as a system property, and a percentage
value could be read from an external data store.
Figure 26.17. Creating a composite strategy.
[View full size image]
<<<PDF_PAGE 623>>>
For the second case of a customer type discount, first recall the use case extension which
previously recognized this requirement:
Use Case UC1: Process Sale
…
Extensions (or Alternative Flows):
5b. Customer says they are eligible for a discount (e.g., employee, preferred customer)
Cashier signals discount request.1.
Cashier enters Customer identification.
System presents discount total, based on discount rules.
This indicates a new system operation on the POS system, in addition to makeNewSale,
enterItem, endSale, and makePayment. We will call this fifth system operation
enterCustomerForDiscount; it may optionally occur after the endSale operation. It implies that
some form of customer identification will have to come in through the user interface, the
customerID. Perhaps it can be captured from a card reader, or via the keyboard.
The design of the second case is shown in Figure 26.18
 and Figure 26.19
. Not surprisingly, the
factory object is responsible for the creation of the additional pricing strategy. It may make
another PercentageDiscountPricingStrategy that represents, for example, a senior discount. But
as with the original creation design, the choice of class will be read in as a system property, as
will the specific percentage for the customer type, to provide Protected Variations with respect to
changing the class or values. Note that by virtue of the Composite pattern, the Sale may have
two or three conflicting pricing strategies attached to it, but it continues to look like a single
strategy to the Sale object.
<<<PDF_PAGE 624>>>
Figure 26.18. Creating the pricing strategy for a customer discount,
part 1
.
[View full size image]
Figure 26.19. Creating the pricing strategy for a customer discount,
part 2
.
[View full size image]

<<<PDF_PAGE 625>>>
UML Figure 26.18
 and Figure 26.19
 show an important UML 2 idea in interaction diagrams: Using
the ref and sd frame to relate diagrams.
Considering GRASP and Other Principles in the Design
To review thinking in terms of some basic GRASP patterns: For this second case, why not have
the Register send a message to the PricingStrategyFactory, to create this new pricing strategy
and then pass it to the Sale? One reason is to support Low Coupling. The Sale is already coupled
to the factory; by making the Register also collaborate with it, the coupling in the design would
increase. Furthermore, the Sale is the Information Expert that knows its current pricing strategy
(which is going to be modified); so by Expert, it is also justified to delegate to the Sale.
Observe in the design that customerID is transformed into a Customer object via the Register
asking the Store for a Customer, given an ID. First, it is justifiable to give the getCustomer
responsibility to the Store; by Information Expert and the goal of low representational gap, the
Store can know all the Customers. And the Register asks the Store, because the Register already
has attribute visibility to the Store (from earlier design work); if the Sale had to ask the Store,
the Sale would need a reference to the Store, increasing the coupling beyond its current levels,
and therefore not supporting Low Coupling.
IDs to Objects
Second, why transform the customerID (an "ID"perhaps a number) into a Customer object? This
is a common practice in object designto transform keys and IDs for things into true objects. This
transformation often takes place shortly after an ID or key enters the domain layer of the Design
Model from the UI layer. It doesn't have a pattern name, but it could be a candidate for a pattern
because it is such a common idiom among experienced object designersperhaps IDs to Objects.
Why bother? Having a true Customer object that encapsulates a set of information about the
customer, and which can have behavior (related to Information Expert, for example), frequently
becomes beneficial and flexible as the design grows, even if the designer does not originally
perceive a need for a true object and thought instead that a plain number or ID would be
sufficient. Note that in the earlier design, the transformation of the itemID into a
ProductDescription object is another example of this IDs to Objects pattern.
Pass Aggregate Object as Parameter
Finally, note that in the addCustomerPricingStrategy(s:Sale) message we pass a Sale to the
factory, and then the factory turns around and asks for the Customer and PricingStrategy from
the Sale.
Why not just extract these two objects from the Sale, and instead pass in the Customer and
PricingStrategy to the factory? The answer is another common object design idiom: Avoid
extracting child objects out of parent or aggregate objects, and then passing around the child
objects. Rather, pass around the aggregate object that contains child objects.
Following this principle increases flexibility, because then the factory can collaborate with the
entire Sale in ways we may not have previously anticipated as necessary (which is very
common), and as a corollary, it reduces the need to anticipate what the factory object needs; the
designer just passes as a parameter the entire Sale, without knowing what more particular
objects the factory may need. Although this idiom does not have a name, it is related to Low
Coupling and Protected Variations. Perhaps it could be called the Pass Aggregate Object as
Parameter pattern.
Summary
<<<PDF_PAGE 626>>>
This design problem was squeezed for many tips in object design. A skilled object designer has
many of these patterns committed to memory through studying their published explanations, and
has internalized core principles, such as those described in the GRASP family.
Please note that although this application of Composite was to a Strategy family, the Composite
pattern can be applied to other kinds of objects, not just strategies. For example, it is common to
create "macro commands"commands that contain other commandsthrough the use of Composite.
The Command pattern is described in a subsequent chapter.
Related Patterns
Composite is often used with the Strategy and Command patterns. Composite is based on
Polymorphism and provides Protected Variations to a client so that it is not impacted if its related
objects are atomic or composite.
 

<<<PDF_PAGE 627>>>
 
26.9. Facade (GoF)
Another requirement chosen for this iteration is pluggable business rules. That is, at predictable
points in the scenarios, such as when makeNewSale or enterItem occurs in the Process Sale use
case, or when a cashier starts cashing in, different customers who wish to purchase the NextGen
POS would like to customize its behavior slightly.
To be more precise, assume that rules are desired that can invalidate an action. For example:
Suppose when a new sale is created, it is possible to identify that it will be paid by a gift
certificate (this is possible and common). Then, a store may have a rule to only allow one
item to be purchased if a gift certificate is used. Consequently, subsequent enterItem
operations, after the first, should be invalidated.
If the sale is paid by a gift certificate, invalidate all payment types of change due back to the
customer except for another gift certificate. For example, if the cashier requested change in
the form of cash, or as a credit to the customer's store account, invalidate those requests.
Suppose when a new sale is created, it is possible to identify that it is for a charitable
donation (from the store to the charity). A store may also have a rule to only allow item
entries less than $250 each, and also to only add items to the sale if the currently logged in
"cashier" is a manager.
In terms of requirements analysis, the specific scenario points across all use cases (enterItem,
chooseCashChange, ...) must be identified. For this exploration, only the enterItem point will be
considered, but the same solution applies equally to all points.
Suppose that the software architect wants a design that has low impact on the existing software
components. That is, she or he wants to design for a separation of concerns, and factor out this
rule handling into a separate concern. Furthermore, suppose that the architect is unsure of the
best implementation for this pluggable rule handling, and may want to experiment with different
solutions for representing, loading, and evaluating the rules. For example, rules can be
implemented with the Strategy pattern, or with free open-source rule interpreters that read and
interpret a set of IF-THEN rules, or with commercial, purchased rule interpreters, among other
solutions.
To solve this design problem, the Facade pattern can be used.
Name:
Facade
Problem:
A common, unified interface to a disparate set of implementations or
interfacessuch as within a subsystemis required. There may be undesirable
coupling to many things in the subsystem, or the implementation of the
subsystem may change. What to do?
Solution:
(advice)
Define a single point of contact to the subsystema facade object that wraps
the subsystem. This facade object presents a single unified interface and is
responsible for collaborating with the subsystem components.
<<<PDF_PAGE 628>>>
A Facade is a "front-end" object that is the single point of entry for the services of a subsystem[2]
; the implementation and other components of the subsystem are private and can't be seen by
external components. Facade provides Protected Variations from changes in the implementation
of a subsystem.
[2] "Subsystem" is here used in an informal sense to indicate a separate grouping of related components, not exactly as
defined in the UML.
For example, we will define a "rule engine" subsystem, whose specific implementation is not yet
known.[3]
 It will be responsible for evaluating a set of rules against an operation (by some hidden
implementation), and then indicating if any of the rules invalidated the operation.
[3] There are several free open source and commercial rule engines. For example, Jess, a free-for-academic-use rule engine
available at http://herzberg.ca.sandia.gov/jess/
.
The facade object to this subsystem will be called POSRuleEngineFacade. See Figure 26.20
. The
designer decides to place calls to this facade near the start of the methods that have been defined
as the points for pluggable rules, as in this example:
public class Sale
{
public void makeLineItem( ProductDescription desc, int quantity )
{
   
SalesLineItem sli = new SalesLineItem( desc, quantity );
      
// call to the Facade
   
if ( POSRuleEngineFacade.getInstance().isInvalid( sli, this ) )
      
return;
   
lineItems.add( sli );
}
// ...
} // end of class
Figure 26.20. UML package diagram with a Facade.
[View full size image]
<<<PDF_PAGE 629>>>
Note the use of the Singleton pattern. Facades are often accessed via Singleton.
With this design, the complexity and implementation of how rules will be represented and
evaluated are hidden in the "rules engine" subsystem, accessed via the POSRuleEngineFacade
facade. Observe that the subsystem hidden by the facade object could contain dozens or
hundreds of classes of objects, or even a non-object-oriented solution, yet as a client to the
subsystem, we see only its one public access point.
And a separation of concerns has been achieved to some degreeall the rule-handling concerns
have been delegated to another subsystem.
Summary
The Facade pattern is simple and widely used. It hides a subsystem behind an object.
Related Patterns
Facades are usually accessed via the Singleton pattern. They provide Protected Variations from
the implementation of a subsystem, by adding an Indirection object to help support Low Coupling.
External objects are coupled to one point in a subsystem: the facade object.
As described in the Adapter pattern, an adapter object may be used to wrap access to external
systems with varying interfaces. This is a kind of facade, but the emphasis is to provide
adaptation to varying interfaces, and thus it is more specifically called an adapter.
 

<<<PDF_PAGE 630>>>
 
26.10. Observer/Publish-Subscribe/Delegation Event
Model (GoF)
Another requirement for the iteration is adding the ability for a GUI window to refresh its display
of the sale total when the total changes (see Figure 26.21
). The idea is to solve the problem for
this one case, and then in later iterations, extend the solution to refreshing the GUI display for
other changing data as well.
Figure 26.21. Updating the interface when the sale total changes.
Why not do the following as a solution? When the Sale changes its total, the Sale object sends a
message to a window, asking it to refresh its display.
To review, the Model-View Separation principle discourages such solutions. It states that "model"
objects (non-UI objects such as a Sale) should not know about view or presentation objects such
as a window. It promotes Low Coupling from other layers to the presentation (UI) layer of
objects.
A consequence of supporting this low coupling is that it allows the replacement of the view or
presentation layer by a new one, or of particular windows by new windows, without impacting the
non-UI objects. If model objects do not know about Java Swing objects (for example), then it is
possible to unplug a Swing interface, or unplug a particular window, and plug in something else.
Thus, Model-View Separation supports Protected Variations with respect to a changing user
interface.
To solve this design problem, the Observer pattern can be used.
<<<PDF_PAGE 631>>>
Name:
Observer (Publish-Subscribe)
Problem:
Different kinds of subscriber objects are interested in the state changes or
events of a publisher object, and want to react in their own unique way when
the publisher generates an event. Moreover, the publisher wants to maintain
low coupling to the subscribers. What to do?
Solution:
(advice)
Define a "subscriber" or "listener" interface. Subscribers implement this
interface. The publisher can dynamically register subscribers who are
interested in an event and notify them when an event occurs.
An example solution is described in detail in Figure 26.22
.
Figure 26.22. The Observer pattern.
[View full size image]
The major ideas and steps in this example:
An interface is defined; in this case, PropertyListener with the operation onPropertyEvent.1.
Define the window to implement the interface.
2.
3.
<<<PDF_PAGE 632>>>
SaleFrame1 will implement the method onPropertyEvent.
2.
When the SaleFrame1 window is initialized, pass it the Sale instance from which it is
displaying the total.
3.
The SaleFrame1 window registers or subscribes to the Sale instance for notification of
"property events," via the addPropertyListener message. That is, when a property (such as
total) changes, the window wants to be notified.
4.
Note that the Sale does not know about SaleFrame1 objects; rather, it only knows about
objects that implement the PropertyListener interface. This lowers the coupling of the Sale to
the windowthe coupling is only to an interface, not to a GUI class.
5.
The Sale instance is thus a publisher of "property events." When the total changes, it
iterates across all subscribing PropertyListeners, notifying each.
6.
The SaleFrame1 object is the observer/subscriber/listener. In Figure 26.23
, it subscribes to
interest in property events of the Sale, which is a publisher of property events. The Sale adds the
object to its list of PropertyListener subscribers. Note that the Sale does not know about the
SaleFrame1 as a SaleFrame1 object, but only as a PropertyListener object; this lowers the
coupling from the model up to the view layer.
Figure 26.23. The observer SaleFrame1 subscribes to the publisher
Sale.
As illustrated in Figure 26.24
, when the Sale total changes, it iterates across all its registered
subscribers, and "publishes an event" by sending the onPropertyEvent message to each.
Figure 26.24. The Sale publishes a property event to all its subscribers.
<<<PDF_PAGE 633>>>
Applying UML: Note the approach to handing polymorphic messages in an interaction diagram,
in Figure 26.24
. The onPropertyEvent message is polymorphic; the specific cases of polymorphic
implementation will be shown in other diagrams, as in Figure 26.25
.
Figure 26.25. The subscriber SaleFrame1 receives notification of a
published event.
[View full size image]
SaleFrame1, which implements the PropertyListener interface, thus implements an
onPropertyEvent method. When the SaleFrame1 receives the message, it sends a message to its
JTextField GUI widget object to refresh with the new sale total. See Figure 26.25
.
In this pattern, there is still some coupling from the model object (the Sale) to the view object
(the SaleFrame1). But it is a loose coupling to an interface independent of the presentation
layerthe PropertyListener interface. And the design does not require any subscriber objects to
actually be registered with the publisher (no objects have to be listening). That is, the list of
registered PropertyListeners in the Sale can be empty. In summary, coupling to a generic
interface of objects that do not need to be present, and which can be dynamically added (or
removed), supports low coupling. Therefore, Protected Variations with respect to a changing user
interface has been achieved through the use of an interface and polymorphism.
Why Is It Called Observer, Publish-Subscribe, or Delegation Event
Model?
<<<PDF_PAGE 634>>>
Originally, this idiom was called publish-subscribe, and it is still widely known by that name. One
object "publishes events," such as the Sale publishing the "property event" when the total
changes. No object may be interested in this event, in which case, the Sale has no registered
subscribers. But objects that are interested, "subscribe" or register to interest in an event by
asking the publishing to notify them. This was done with the Sale.addPropertyListener message.
When the event happens, the registered subscribers are notified by a message.
It has been called Observer because the listener or subscriber is observing the event; that term
was popularized in Smalltalk in the early 1980s.
It has also been called the Delegation Event Model (in Java) because the publisher delegates
handling of events to "listeners" (subscribers; see Figure 26.26
).
Figure 26.26. Who is the observer, listener, subscriber, and publisher?
[View full size image]
Observer Is Not Only for Connecting UIs and Model Objects
The previous example illustrated connecting a non-UI object to a UI object with Observer.
However, other uses are common.
The most prevalent use of this pattern is for GUI widget event handling, in both Java technologies
(AWT and Swing) and in Microsoft's .NET. Each widget is a publisher of GUI-related events, and
other objects can subscribe to interest in these. For example, a Swing JButton publishes an
"action event" when it is pressed. Another object will register with the button so that when it is
pressed, the object is sent a message and can take some action.
As another example, Figure 26.27
 illustrates an AlarmClock, which is a publisher of alarm events
and various subscribers. This example is illustrative in that it emphasizes that many classes can
implement the AlarmListener interface, many objects can simultaneously be registered listeners,
and all can react to the "alarm event" in their own unique way.
<<<PDF_PAGE 635>>>
Figure 26.27. Observer applied to alarm events, with different
subscribers.
[View full size image]
One Publisher Can Have Many Subscribers for an Event
As suggested in Figure 26.27
, one publisher instance could have from zero to many registered
subscribers. For example, one instance of an AlarmClock could have three registered
AlarmWindows, four Beepers, and one ReliabilityWatchDog. When an alarm event happens, all
eight of these AlarmListeners are notified via an onAlarmEvent.
Implementation
Events
In both the Java and C# .NET implementations of Observer, an "event" is communicated via a
regular message, such as onPropertyEvent. Moreover, in both cases, the event is more formally
defined as a class, and filled with appropriate event data. The event is then passed as a
parameter in the event message.
For example:
<<<PDF_PAGE 636>>>
class PropertyEvent extends Event
{
   
private Object sourceOfEvent;
   
private String propertyName;
   
private Object oldValue;
   
private Object newValue;
   
//...
}
//...
class Sale
{
   
private void publishPropertyEvent(
      
String name, Object old, Object new )
   
{
      
PropertyEvent evt =
       
new PropertyEvent( this, "sale.total", old, new);
      
for each AlarmListener al in alarmListeners
       
al.onPropertyEvent( evt );
   
}
   
//...
}
Java
When the JDK 1.0 was released in January 1996, it contained a weak publish-subscribe
implementation based on a class and interface called Observable and Observer, respectively. This
was essentially copied without improvement from an early 1980s approach to publish-subscribe
implemented in Smalltalk.
Therefore, in late 1996, as part of the JDK 1.1 effort, the Observable-Observer design was
effectively replaced by the more robust Java Delegation Event Model (DEM) version of publish-
subscribe, although the original design was kept for backward-compatibility (but in general to be
avoided).
The designs that have been described in this chapter are consistent with the DEM, but slightly
simplified to emphasize the core ideas.
Summary
Observer provides a way to loosely couple objects in terms of communication. Publishers know
about subscribers only through an interface, and subscribers can register (or de-register)
dynamically with the publisher.
Related Patterns
Observer is based on Polymorphism, and provides Protected Variations in terms of protecting the
<<<PDF_PAGE 637>>>
publisher from knowing the specific class of object, and number of objects, that it communicates
with when the publisher generates an event.
 

<<<PDF_PAGE 638>>>
 
26.11. Conclusion
The main lesson to draw from this exposition is that objects can be designed and responsibilities
assigned with the support of patterns. These provide an explainable set of idioms by which well-
designed object-oriented systems can be built.
 

<<<PDF_PAGE 639>>>
 
26.12. Recommended Resources
Design Patterns by Gamma, Helm, Johnson, and Vlissides is the seminal patterns text, and
essential reading for all object designers.
Each year there is a "Pattern Languages of Programs" (PLOP) conference, from which is published
an annual compendium of patterns, in the series Pattern Languages of Program Design, volumes
1, 2, and so forth. The entire series is recommended.
Pattern-Oriented Software Architecture, volumes 1 and 2, furthered the discussion of patterns to
larger-scale architectural concerns. Volume 1 presented a taxonomy of patterns.
There are hundreds of published patterns. The Pattern Almanac by Rising summarizes a
respectable percentage of them.
 

# Chapter 33. Architectural Analysis


<<<PDF_PAGE 734>>>
 
Chapter 33. Architectural Analysis
Error, no keyboard press F1 to continue.
early PC BIOS message
Objectives
Create architectural factor tables.
Create technical memos that record architectural decisions.
 

<<<PDF_PAGE 735>>>
 
Introduction
Architectural analysis can be viewed as a specialization of requirements analysis, with a focus on
requirements that strongly influence the "architecture." For example, identifying the need for a
highly-secure system.
The essence of architectural analysis is to identify factors that should influence the architecture,
understand their variability and priority, and resolve them. The difficult part is knowing what
questions to ask, weighing the trade-offs, and knowing the many ways to resolve an
architecturally significant factor, ranging from benign neglect, to fancy designs, to third-party
products.
A good architect earns her salary by having the experience to know what questions to ask and
choosing skillful means to resolve the factors.
[View full size image]
Why is architectural analysis important? It's useful to:
reduce the risk of missing something centrally important in the design of the systems
avoid applying excessive effort to low priority issues
help align the product with business goals
This chapter is an introduction to basic steps and ideas in architectural analysis from a UP
perspective; that is, to the method, rather than to tips and tricks of master architects. Thus, it is
not a cookbook of architectural solutionsa very large and context-dependent subject that is
beyond the scope of this introductory book. Nevertheless, the NextGen POS case study comments
in the chapter do provide concrete examples of architectural solutions.
 

<<<PDF_PAGE 736>>>
 
33.1. Process: When Do We Start Architectural
Analysis?
In the UP, architectural analysis should start even before the first development iteration, as
architectural issues need to be identified and resolved in early development work. Failure to do so
is a high risk. For example, deferring an architecturally-significant factor such as "must be
internationalized to support English, Chinese, and Hindi" or "must handle 500 concurrent
transactions with on-average one-second response time" until late in development is a recipe for
pain and suffering.
However, since the UP is iterative and evolutionarynot the waterfallwe start programming and
testing in early iterations before all the architectural analysis is complete. Analysis and early
development proceed hand-in-hand.
But this important topic was deferred until this point of the book so that fundamentals of OOA/D
could be first presented.
 

<<<PDF_PAGE 737>>>
 
33.2. Definition: Variation and Evolution Points
First, two points of change in a software system (first introduced in the Protected Variations
pattern) are worth reiterating:
variation point Variations in the existing current system or requirements, such as the
multiple tax calculator interfaces that must be supported.
evolution point Speculative points of variation that may arise in the future, but which are
not present in the existing requirements.
As will be seen, variation and evolution points are recurring key elements in architectural analysis.
 

<<<PDF_PAGE 738>>>
 
33.3. Architectural Analysis
Architectural analysis is concerned with the identification and resolution of the system's non-
functional requirements (for example, security), in the context of the functional requirements (for
example, processing sales). It includes identifying variation points and the most probable
evolution points.
In the UP, the term encompasses both architectural investigation (identification) and architectural
design (resolution). Here are some examples of the many issues to be identified and resolved at
an architectural level:
How do reliability and fault-tolerance requirements affect the design?
For example, in the NextGen POS, for what remote services (e.g., tax calculator) will
fail-over to local services be allowed? Why? Do they provide exactly the same services
locally as remotely, or are there differences?
How do the licensing costs of purchased subcomponents affect profitability?
For example, the producer of the excellent database server, Clueless, wants 2% of
each NextGen POS sale, if their product is used as a subcomponent. Using their
product will speed development (and time to market) because it is robust and provides
many services, and many developers know it, but at a price. Should the team instead
use the less robust, open source YourSQL database server? At what risk? How does it
restrict the ability to charge for the NextGen product?
How do the adaptability and configurability requirements affect the design?
For example, most retailers have variations in business rules they want represented in
their POS applications. What are the variations? What is the "best" way to design for
them? What is the criteria for best? Can NextGen make more money by requiring
customized programming for each customer (and how much effort will that be?), or
with a solution that allows the customer to add the customization easily themselves?
Should "more money" be the goal in the short-run?
How does brand name and branding affect the architecture?
A little-known story is that Microsoft's Windows XP was not originally named "Windows
XP." The name was a relatively last-minute change from the marketing department.
You may appreciate that the operating system name is displayed in many places, both
as raw text and as a graphic image. Because the Microsoft architects did not identify a
name change as a likely evolution point, there was no Protected Variation solution for
this point, such as the label existing in only one place in a configuration file. Therefore,
at the last minute, a small team scoured the millions of lines of source code and image
files, and made hundreds of changes.
Similarly, how should potential changes to the brand name of the NextGen product and
related logos, icons, and so forth affect its architecture?
<<<PDF_PAGE 739>>>
How do the adaptability and configurability requirements affect the design?
For example, most retailers have variations in business rules they want represented in
their POS applications. What are the variations? What is the "best" way to design for
them? What is the criteria for best? Can Next Gen make more money by requiring
customized programming for each customer (and how much effort will that be?), or
with a solution that allows the customer to add the customization easily themselves?
Should "more money" be the goal in the short-run?
 

<<<PDF_PAGE 740>>>
 
33.4. Common Steps in Architectural Analysis
There are several methods of architectural analysis. Common to most of these is some variation
of the following steps:
1.
Identify and analyze the non-functional requirements that have an impact on the
architecture. Functional requirements are also relevant (especially in terms of variability or
change), but the non-functional are given thorough attention. In general, all these may be
called architectural factors (also known as the architectural drivers).
This step could be characterized as regular requirements analysis, but since it is done in
the context of identifying architectural impact and deciding high-level architectural
solutions, it is considered a part of architectural analysis in the UP.
In terms of the UP, some of these requirements will be roughly identified and recorded
in the Supplementary Specification or use cases during inception. During architectural
analysis, which occurs in early elaboration, the team investigates these requirements
more closely.
2.
For those requirements with a significant architectural impact, analyze alternatives and
create solutions that resolve the impact. These are architectural decisions.
Decisions range from "remove the requirement," to a custom solution, to "stop the
project," to "hire an expert."
This presentation introduces these basic steps in the context of the NextGen POS case study. For
simplicity, it avoids architectural deployment issues such as the hardware and operating system
configuration, which are very context and time sensitive.
 

<<<PDF_PAGE 741>>>
 
33.5. The Science: Identification and Analysis of
Architectural Factors
Architectural Factors
Any and all of the FURPS+ requirements may have a significant influence on the architecture of a
system, ranging from reliability, to schedule, to skills, and to cost constraints. For example, a
case of tight schedule with limited skills and sufficient money probably favors buying or
outsourcing to specialists, rather than building all components in-house.
FURPS+ p. 56
However, the factors with the strongest architectural influence tend to be within the high-level
FURPS+ categories of functionality, reliability, performance, supportability, implementation, and
interface. Interestingly, it is usually the non-functional quality attributes (such as reliability or
performance) that give a particular architecture its unique flavor, rather than its functional
requirements. For example, the design in the NextGen system to support different third-party
components with unique interfaces, and the design to support easily plugging in different sets of
business rules.
In the UP, these factors with architectural implications are called architecturally significant
requirements. "Factors" is used here for brevity.
Many technical and organizational factors can be characterized as constraints that restrict the
solution in some way (such as, must run on Linux, or, the budget for purchasing third-party
components is X).
Quality Scenarios
When defining quality requirements during architectural factor analysis, quality scenarios[1]
 are
recommended, as they define measurable (or at least observable) responses, and thus can be
verified. It is not much use to vaguely state "the system will be easy to modify" without some
measure of what that means.[2]
[1] A term used in various architectural methods promoted by the Software Engineering Institute (SEI); for example, in the
Architecture Based Design method.
[2] Tom Gilb, the creator of perhaps the first iterative and evolutionary method, Evo, is also a long-time proponent of the need
to quantify and measure non-functional goals. His PLanguage structured requirements language emphasizes quantification.
Quantifying some things, such as performance goals and mean time between failure, are well
known practices, but quality scenarios extend this idea and encourage recording all (or at least,
<<<PDF_PAGE 742>>>
most) factors as measurable statements.
Quality scenarios are short statements of the form <stimulus> <measurable response>; for
example:
When the completed sale is sent to the remote tax calculator to add the taxes, the result is
returned within 2 seconds "most" of the time, measured in a production environment under
"average" load conditions.
When a bug report arrives from a NextGen beta test volunteer, reply with a phone call
within 1 working day.
Note that "most" and "average" will need further investigation and definition by the NextGen
architect; a quality scenario is not really valid until it is testable, which implies fully specified. Also,
observe the qualification in the first quality scenario in terms of the environment to which it
applies. It does little good to specify a quality scenario, verify that it passes in a lightly loaded
development environment, but fail to evaluate it in a realistic production environment.
Pick Your Battles
A caution: Writing these quality scenarios can be a mirage of usefulness. It's easy to write these
detailed specifications, but not to realize them. Will anyone ever really test them? How and by
whom? A strong dose of realism is required when writing these; there's no point in listing many
sophisticated goals if no one will ever really follow through on testing them.
pick your battles
 p. 432
There is a relationship here to the "pick your battles" discussion that was presented in an earlier
chapter on the Protected Variations pattern. What are the really critical make-or-break quality
scenarios? For example, in an airline reservation system, consistently fast transaction completion
under very high load conditions is truly critical to the success of the systemit must definitely be
tested. In the NextGen system, the application really must be fault-tolerant and fail over to local
replicated services when the remote ones failit must definitely be properly tested and validated.
Therefore, focus on writing quality scenarios for the important battles, and follow through with a
plan for their evaluation.
Describing Factors
One important goal of architectural analysis is to understand the influence of the factors, their
priorities, and their variability (immediate need for flexibility and future evolution). Therefore,
most architectural methods (for example, see [HNS00
]) advocate creating a table or tree with
variations of the following information (the format varies depending on the method). The following
style shown in Table 33.1
 is called a factor table, which in the UP is part of the Supplementary
Specification.
Table 33.1. Sample factor table. Legend: H-high. M-medium. SME-
<<<PDF_PAGE 743>>>
subject matter expert.
Factor
Measures
and quality
scenarios
Variability (current
flexibility and future
evolution)
Impact of factor (and
its variability) on
stakeholders,
architecture and other
factors
Priority
for
Success
Difficulty
or Risk
ReliabilityRecoverability
Recovery
from
remote
service
failure
When a
remote
service fails,
reestablish
connectivity
with it within
1 minute of
its detected
re-
availability,
under
normal store
load in a
production
environment.
current flexibility - our
SME says local client-side
simplified services are
acceptable (and desirable)
until reconnection is
possible.
evolution - within 2 years,
some retailers may be
willing to pay for full local
replication of remote
services (such as the tax
calculator). Probability?
High.
High impact on the
large-scale design.
Retailers really dislike
it when remote
services fail, as it
prevents or restricts
them from using a
POS to make sales.
H
M
…
…
…
…
 
 
Notice the categorization scheme: ReliabilityRecoverability (from the FURPS+ categories). This
isn't presented as the best or only scheme, but it is useful to group architectural factors into
categories. For example, certain categories (such as reliability and performance) strongly relate to
identifying and defining test plans, and thus it is useful to group them.
The basic priority and risk code values of H/M/L are simply suggestive of using some codes the
team finds useful; there are a variety of coding schemes (numeric and qualitative) from different
architectural methods and standards (such as ISO 9126). A caution: If the extra effort of using a
more complex scheme does not lead to any practical action, it isn't worthwhile.
Factors and UP Artifacts
The central functional requirements repository in the UP are the use cases, and they, along with
the Vision and Supplementary Specification, are an important source of inspiration when creating
a factor table. In the use cases, the Special Requirements, Technology Variations, and Open
Issues should be reviewed, and their implied or explicit architectural factors consolidated in the
Supplementary Specification.
It is reasonable to at first record use-case related factors with the use case during its creation,
because of the obvious relationship, but it is ultimately more convenient (in terms of content
management, tracking, and readability) to consolidate all the architectural factors in one
locationin the factor table in the Supplementary Specification.
<<<PDF_PAGE 744>>>
Use Case UC1: Process Sale
Main Success Scenario:
…1.
Special Requirements:
- Credit authorization response within 30 seconds 90% of the time.
- Somehow, we want robust recovery when access to remote services such the inventory
system is failing.
- …
Technology and Data Variations List:
2a. Item identifier entered by bar code laser scanner (if bar code is present) or keyboard.
…
Open Issues:
- What are the tax law variations?
- Explore the remote service recovery issue.
 

<<<PDF_PAGE 745>>>
 
33.6. Example: Partial NextGen POS Architectural
Factor Table
The partial factor table in Table 33.2
 shows some factors related to later discussion.
Table 33.2. Partial factor table for the NextGen architectural analysis.
Factor
Measures
and quality
scenarios
Variability (current flexibility and
future evolution)
Impact of
factor (and
its
variability)
on
stakeholders,
architecture
and other
factors
Priority
for
Success
Difficulty
or Risk
ReliabilityRecoverability
Recovery
from
remote
service
failure
When a
remote
service fails,
reestablish
connectivity
with it within
1 minute of
its detected
re-
availability,
under normal
store load in
a production
environment.
current flexibility - our SME says
local client-side simplified
services are acceptable (and
desirable) until reconnection is
possible.
evolution - within 2 years, some
retailers may be willing to pay
for full local replication of
remote services (such as the tax
calculator). Probability? High.
High impact
on the large-
scale design.
Retailers
really dislike
it when
remote
services fail,
as it
prevents
them from
using a POS
to make
sales.
H
M
Recovery
from
remote
product
database
failure
as above
current flexibility - our SME says
local client-side use of cached
"most common" product info is
acceptable (and desirable) until
reconnection is possible.
evolution - within 3 years,
client-side mass storage and
replication solutions will be
cheap and effective, allowing
permanent complete replication
and thus local usage.
Probability? High.
as above
H
M
<<<PDF_PAGE 746>>>
Factor
Measures
and quality
scenarios
Variability (current flexibility and
future evolution)
Impact of
factor (and
its
variability)
on
stakeholders,
architecture
and other
factors
Priority
for
Success
Difficulty
or Risk
ReliabilityRecoverability
Supportability - Adaptability
Support
many third-
party
services
(tax
calculator,
inventory,
HR,
accounting).
They will
vary at each
installation.
When a new
third-party
system must
be
integrated, it
can be, and
within 10
person days
of effort.
current flexibility - as described
by factor
evolution - none
Required for
product
acceptance.
Small impact
on design.
H
L
Support
wireless
PDA
terminals
for the POS
client?
When
support is
added, it
does not
require a
change to
the design of
the non-UI
layers of the
architecture.
current flexibility - not required
at present
evolution - within 3 years, we
think the probability is very high
that wireless "PDA" POS clients
will be desired by the market.
High design
impact in
terms of
protected
variation
from many
elements.
For example,
the operating
systems and
UIs are
different on
small
devices.
L
H
Other - Legal
Current tax
rules must
be applied.
When the
auditor
evaluates
conformance,
100%
conformance
will be found.
When tax
rules change,
they will be
operational
within the
period
current flexibility - conformance
is inflexible, but tax rules can
change almost weekly because
of the many rules and levels of
government taxation (national,
state, ...)
evolution - none
Failure to
comply is a
criminal
offense.
Impacts tax
calculation
services.
Difficult to
write our
own service-
-complex
rules,
H
L
Supportability - Adaptability
Support
many third-
party
services
(tax
calculator,
inventory,
HR,
accounting).
They will
vary at each
installation.
When a new
third-party
system must
be
integrated, it
can be, and
within 10
person days
of effort.
current flexibility - as described
by factor
evolution - none
Required for
product
acceptance.
Small impact
on design.
H
L
Support
wireless
PDA
terminals
for the POS
client?
When
support is
added, it
does not
require a
change to
the design of
the non-UI
layers of the
architecture.
current flexibility - not required
at present
evolution - within 3 years, we
think the probability is very high
that wireless "PDA" POS clients
will be desired by the market.
High design
impact in
terms of
protected
variation
from many
elements.
For example,
the operating
systems and
UIs are
different on
small
devices.
L
H
Other - Legal
Current tax
rules must
be applied.
When the
auditor
evaluates
conformance,
100%
conformance
will be found.
When tax
rules change,
they will be
operational
within the
current flexibility - conformance
is inflexible, but tax rules can
change almost weekly because
of the many rules and levels of
government taxation (national,
state, ...)
evolution - none
Failure to
comply is a
criminal
offense.
Impacts tax
calculation
services.
Difficult to
write our
own service-
-complex
H
L
<<<PDF_PAGE 747>>>
Factor
Measures
and quality
scenarios
Variability (current flexibility and
future evolution)
Impact of
factor (and
its
variability)
on
stakeholders,
architecture
and other
factors
Priority
for
Success
Difficulty
or Risk
ReliabilityRecoverability
within the
period
allowed by
government.
-complex
rules,
constant
change, need
to track all
levels of
government.
But,
easy/low risk
if buy a
package.
 
within the
period
allowed by
government.
-complex
rules,
constant
change, need
to track all
levels of
government.
But,
easy/low risk
if buy a
package.
 

<<<PDF_PAGE 748>>>
 
33.7. The Art: Resolution of Architectural Factors
One could say the science of architecture is the collection and organization of information about
the architectural factors, as in the factor table. The art of architecture is making skillful choices to
resolve these factors, in light of trade-offs, interdependencies, and priorities.
Adept architects have knowledge in a variety of areas (for example, architectural styles and
patterns, technologies, products, pitfalls, and trends) and apply this to their decisions.
Recording Architectural Alternatives, Decisions, and Motivation
Ignoring for now principles of architectural decision-making, virtually all architectural methods
recommend keeping a record of alternative solutions, decisions, influential factors, and
motivations for the noteworthy issues and decisions.
Such records have been called technical memos [Cunningham96
], issue cards [HNS00
], and
architectural approach documents (SEI architectural proposals), with varying degrees of
formality and sophistication. In some methods, these memos are the basis for yet another step of
review and refinement.
In the UP, the memos should be recorded in the SAD.
An important aspect of the technical memo is the motivation or rationale. When a future
developer or architect needs to modify the system,[3]
 it is immensely helpful to understand the
motivations behind the design, such as why a particular approach to recovery from remote
service failure in the NextGen POS was chosen and others rejected, in order to make informed
decisions about changing the system.
[3] Or when four weeks have passed and the original architect has forgotten their own rationale!
Explaining the rationale of rejecting the alternatives is important, as during future product
evolution, an architect may reconsider these alternatives, or at least want to know what
alternatives were considered, and why one was chosen.
A sample technical memo follows that records an architectural decision for the NextGen POS. The
exact format is, of course, not important. Keep it simple and just record information that will help
the future reader make an informed decision when changing the system.
<<<PDF_PAGE 749>>>
Technical Memo: Issue: ReliabilityRecovery from Remote
Service Failure
Solution Summary: Location transparency using service lookup, failover
from remote to local, and local service partial replication.
Factors
Robust recovery from remote service failure (e.g., tax calculator, inventory)
Robust recovery from remote product (e.g., descriptions and prices) database
failure
Solution
Achieve protected variation with respect to location of services using an Adapter
created in a ServicesFactory. Where possible, offer local implementations of remote
services, usually with simplified or constrained behavior. For example, the local tax
calculator will use constant tax rates. The local product information database will be a
small cache of the most common products. Inventory updates will be stored and
forwarded at reconnection.
See also the AdaptabilityThird-Party Services technical memo for the adaptability
aspects of this solutions, because remote service implementations will vary at each
installation.
To satisfy the quality scenarios of reconnection with the remote services ASAP, use
smart Proxy objects for the services, that on each service call test for remote service
reactivation, and redirect to them when possible.
Motivation
Retailers really don't want to stop making sales! Therefore, if the NextGen POS offers
this level of reliability and recovery, it will be a very attractive product, as none of our
competitors provide this capability. The small product cache is motivated by very
limited client-side resources. The real third-party tax calculator is not replicated on
the client primarily because of the higher licensing costs, and configuration efforts (as
each calculator installation requires almost weekly adjustments). This design also
supports the evolution point of future customers willing and able to permanently
replicate services such as the tax calculator to each client terminal.
Unresolved Issues
none
Alternatives Considered
A "gold level" quality of service agreement with remote credit authorization services
to improve reliability. It was available, but much too expensive.
Note as illustrated in this exampleand this is a key pointthat an architectural decision described in
<<<PDF_PAGE 750>>>
one technical memo may resolve a group of factors, not only one.
Priorities
There is a hierarchy of goals that guides architectural decisions:
Inflexible constraints, including safety and legal compliance.
The NextGen POS must correctly apply tax policies.
1.
Business goals.
Demo of noteworthy features ready for the POSWorld trade show in Hamburg in 18
months.
Has qualities and features attractive to department stores in Europe (for example,
multi-currency support and customizable business rules).
2.
All other goals
These can often be traced back to directly stated business goals, but are indirect. For
example, "easily extendible: can add <some unit of functionality> in 10 person weeks"
could trace to a business goal of "new release every six months."
3.
In the UP, many of these goals are recorded in the Vision artifact. Mind that the Priority for
Success scores in the factor table should reflect the priority of these goals.
There is a distinguishing aspect of decision-making at this level vs. small-scale object design: one
has to simultaneously consider more (and often globally influential) goals and their trade-offs.
Furthermore, the business goals become central to the technical decisions (or at least they
should). For example:
<<<PDF_PAGE 751>>>
Technical Memo: Issue: LegalTax Rule Compliance
Solution Summary: Purchase a tax calculator component.
Factors
Current tax rules must be applied, by law.
Solution
Purchase a tax calculator with a licensing agreement to receive ongoing tax rule
updates. Note that different calculators may be used at different installations.
Motivation
Time-to-market, correctness, low maintenance requirements, and happy developers
(see alternatives). These products are costly, which affects our cost-containment and
product pricing business goals, but the alternative is considered unacceptable.
Unresolved Issues
What are the leading products and their qualities?
Alternatives Considered
Build one by the NextGen team? It is estimated to take too long, be error prone, and
create an ongoing costly and uninteresting (to the company's developers)
maintenance responsibility, which affects the goal of "happy developers" (surely, the
most important goal of all).
Priorities and Evolution Points: Under- and Over-engineering
Another distinguishing feature of architectural decision-making is prioritization by probability of
evolution pointspoints of variability or change that may arise in the future. For example, in
NextGen, there is a chance that wireless handheld client terminals will become desirable.
Designing for this has a significant impact because of differences in operating systems, user
interface, hardware resources, and so forth.
The company could spend a huge amount of money (and increase a variety of risks) to achieve
this "future proofing." If it turns out in the future that this was not relevant, doing it would be a
very expensive exercise in over-engineering. Note also that future proofing is arguably rarely
perfect, since it is speculation; even if the predicted change occurs, some change in the
speculated design is likely.
On the other hand, future proofing against the Y2K date problem would have been money very
well spent; instead, there was under-engineering with a wickedly expensive result.
<<<PDF_PAGE 752>>>
The art of the architect is knowing what battles are worth fightingwhere it's worth
investing in designs that provide protection against evolutionary change.
To decide if early "future-proofing" should be avoided, realistically consider the scenario of
deferring the change to the future, when it is called for. How much of the design and code will
actually have to change? What will be the effort? Perhaps a close look at the potential change will
reveal that what was at first considered a gigantic issue to protect against, is estimated to
consume only a few person-weeks of effort.
This is just a hard problem; "Prediction is very difficult, especially if it's about the future"
(unverifiably attributed to Niels Bohr).
Basic Architectural Design Principles
The core design principles explored in much of this book that were applicable to small-scale object
design are still dominant principles at the large-scale architectural level:
low coupling
high cohesion
protected variation (interfaces, indirection, service lookup, and so forth)
However, the granularity of the components is largerit is low coupling between applications,
subsystems, or process rather than between small objects.
Furthermore, at this larger scale, there are more or different mechanisms to achieve qualities
such as low coupling and protected variation. For example, consider this technical memo:
Technical Memo: Issue: AdaptabilityThird-Party Services
Solution Summary: Protected Variation using interfaces and Adapters
Factors
Support many, changeable third-party services (tax calculators, credit
authorization, inventory, ...)
Solution
Achieve protected variation as follows: Analyze several commercial tax calculator
products (and so forth for the other product categories) and construct common
interfaces for the lowest common denominators of functionality. Then use Indirection
via the Adapter pattern. That is, create a resource Adapter object that implements
the interface and acts as connection and translator to a particular back-end tax
<<<PDF_PAGE 753>>>
calculator. See also the ReliabilityRecovery from Remote Service Failure technical
memo for the location transparency aspects of this solution.
Motivation
Simple. Cheaper, and faster communication than using a messaging service (see
alternatives), and in any event a messaging service can't be used to directly connect
to the external credit authorization service.
Unresolved Issues
Will the lowest common denominator interfaces create an unforeseen problem, such
as too limited?
Alternatives Considered
Apply indirection by using a messaging or publish-subscribe service (e.g., a JMS
implementation) between the client and tax calculator, with adapters. But not directly
usable with a credit authorizer, costly (for reliable ones), and more reliability in
message delivery than is practically needed.
The point is that at the architectural level, there are usually new mechanisms to achieve
protected variation (and other goals), often in collaboration with third-party components, such as
using a Java Messaging Service (JMS) or EBJ server.
Separation of Concerns and Localization of Impact
Another basic principle applied during architectural analysis is to achieve a separation of
concerns. It is also applicable at the scale of small objects, but achieves prominence during
architectural analysis.
Cross-cutting concerns are those with a wide application or influence in the system, such as
data persistence or security. One could design persistence support in the NextGen application
such that each object (that contained application logic code) itself also communicated with a
database to save its data. This would weave the concern of persistence in with the concern of
application logic, in the source code of the classesso too with security. Cohesion drops and
coupling rises.
In contrast, designing for a separation of concerns factors out persistence support and security
support into separate "things" (there are very different mechanisms for this separation). An
object with application logic just has application logic, not persistence or security logic. Similarly,
a persistence subsystem focuses on the concern of persistence, not security. A security
subsystem doesn't do persistence.
Separation of concerns is a large-scale way of thinking about low coupling and high cohesion at an
architectural level. It also applies to small-scale objects, because its absence results in incohesive
objects that have multiple areas of responsibility. But it is especially an architectural issue
because the concerns are broad, and the solutions involve major, fundamental design choices.
There are several large-scale techniques to achieve a separation of concerns:
Modularize the concern into a separate component (for example, subsystem) and invoke its
services.
1.
<<<PDF_PAGE 754>>>
This is the most common approach. For example, in the NextGen system, the
persistence support could be factored into a subsystem called the persistence service.
Via a facade, it can offer a public interface of services to other components. Layered
architectures also illustrate this separation of concerns.
1.
Use decorators.
This is the second most common approach; first popularized in the Microsoft
Transaction Service, and afterwards with EJB servers. In this approach, the concern
(such as security) is decorated onto other objects with a Decorator object that wraps
the inner object and interposes the service. The Decorator is called a container in EJB
terminology. For example, in the NextGen POS system, security control to remote
services such as the HR system can be achieved with an EJB container that adds
security checks in the outer Decorator, around the application logic of the inner object.
2.
Use post-compilers and aspect-oriented technologies.
For example, with EJB entity beans one can add persistence support to classes such as
Sale. One specifies in a property descriptor file the persistence characteristics of the
Sale class. Then, a post-compiler (by which I mean another compiler that executes
after the "regular" compiler) will add the necessary persistence support in a modified
Sale class (modifying just the bytecode) or subclass. The developer continues to see
the original class as a "clean" application-logic-only class. Another variation is aspect-
oriented technologies such as AspectJ (www.aspectj.org
), which similarly support
post-compilation weaving in of cross-cutting concerns into the code, in a manner that
is transparent to the developer. These approaches maintain the illusion of separation
during development work, and weave in the concern before execution.
3.
Promotion of Architectural Patterns
An exploration of architectural patterns and how they could apply (or misapply) to the NextGen
case study is out of scope in this introductory text. However, a few pointers:
Probably the most common mechanism to achieve low coupling, protected variation, and a
separation of concerns at the architectural level is the Layers pattern, which has been introduced
a previous chapter. This is an example of the most common separation techniquemodularizing
concerns into separate components or layers.
There is a large and growing body of written architectural patterns. Studying these is the fastest
way I know of to learn architectural solutions. Please see the recommended readings.
 

<<<PDF_PAGE 755>>>
 
33.8. Summary of Themes in Architectural Analysis
The first theme to note is that "architectural" concerns are especially related to non-functional
requirements, and include an awareness of the business or market context of the application. At
the same time, the functional requirements (for example, processing sales) cannot be ignored;
they provide the context within which these concerns must be resolved. Further, identification of
their variability is architecturally significant.
A second theme is that architectural concerns involve system-level, large-scale, and broad
problems whose resolution usually involves large-scale or fundamental design decisions; for
example, the choice ofor even use ofan application server.
A third theme in architectural analysis is interdependencies and trade-offs. For example,
improved security may affect performance or usability, and most choices affect cost.
A fourth theme in architecture analysis is the generation and evaluation of alternative solutions.
A skilled architect can offer design solutions that involve building new software, and also suggest
solutions (or partial solutions) using commercial or publicly available software and hardware. For
example, recovery in a remote server of the NextGen POS can be achieved through designing and
programming "watchdog" processes, or perhaps through clustering, replication, and fail-over
services offered by some operating system and hardware components. Good architects know
third-party hardware and software products.
The opening definition of architectural concerns provides the framework for how to think about
the subject of architecture: identifying the issues with large-scale or system-level implications,
and resolving them.
Definition
Architectural analysis is concerned with the identification and resolution of the
system's non-functional requirements in the context of the functional requirements.
 

<<<PDF_PAGE 756>>>
 
33.9. Process: Iterative Architecture in the UP
The UP is an architecture-centric iterative and evolutionary method. This does not mean a
waterfall attempt to fully identify all architectural requirements before development, nor an
attempt to fully design the "correct" architecture before program and test. Rather, it means that
early iterations focus on programming and testing architecturally significant concerns (such as
security) and using, proving, developing and stabilizing the key architectural elements
(subsystems, interfaces, frameworks, and so on).
In the UP, the architecture evolves and stabilizes through early development and test with an
architecture-focus, not through speculation on paper, or "PowerPoint Architecture."
In the UP, the architectural factorsor requirementsare recorded in the Supplementary
Specification, and the architectural decisions that resolve them are recorded in the Software
Architecture Document (SAD). Because the UP is not the waterfall, the SAD is not fully created
before programming, but rather, after programmingonce the code has stabilized. Then, the SAD
documents the actual system as a learning aid for others.
documenting architecture and the SAD
 p. 655
Architectural analysis starts early, during the inception phase, and is a focus of the elaboration
phase; it is a high-priority and very influential activity in software development.
Architectural Information in the UP Artifacts
The architectural factors (for example, in a factor table) are recorded in the Supplementary
Specification.
The architectural decisions are recorded in the SAD. This includes the technical memos and
descriptions of the architectural views.
Phases
Inception If it is unclear whether it is technically possible to satisfy the architecturally significant
requirements, the team may implement an architectural proof-of-concept (POC) to determine
feasibility. In the UP, its creation and assessment is called Architectural Synthesis. This is
distinct from plain old small POC programming experiments for isolated technical questions. An
architectural POC lightly covers many of the architecturally significant requirements to assess
their combined feasibility.
Elaboration A major goal of this phase is to implement the core risky architectural elements,
thus most architectural analysis is completed during elaboration. It is normally expected that the
<<<PDF_PAGE 757>>>
majority of factor table, technical memo, and SAD content can be completed by the end of
elaboration.
Transition Although ideally the architecturally significant factors and decisions were resolved
long before transition, the SAD will need a review and possible revision at the end of this phase to
ensure it accurately describes the final deployed system.
Subsequent evolution cycles Before the design of new versions, it is common to revisit
architectural factors and decisions. For example, the decision in version 1.0 to create a single
remote tax calculator service, rather than one duplicated on each POS node, could have been
motivated by cost (to avoid multiple licenses). But perhaps in the future the cost of tax
calculators is reduced, and thus, for fault tolerance or performance reasons, the architecture is
changed to use multiple local tax calculators.
 

<<<PDF_PAGE 758>>>
 
33.10. Recommended Resources
There is a growing body of architecture-related patterns, and general software architecture
advice. Suggestions:
Beyond Software Architecture [Hohman03
]. This useful guide, from someone experienced as
both architect and product manager, brings a business-oriented emphasis to architecture.
Hohman shares his experience with important issues seldom covered, such as the impact of
the business model, licensing, and upgrades on the software architecture.
Patterns of Enterprise Application Architecture [Fowler02
].
Software Architecture in Practice [BCK98
].
Pattern-Oriented Software Architecture, both volumes.
Pattern Languages of Program Design, all volumes. Each volume has a section on
architecture-related patterns.
 

# Chapter 34. Logical Architecture Refinement


<<<PDF_PAGE 759>>>
 
Chapter 34. Logical Architecture
Refinement
Alcohol and calculus don't mix… Don't drink and derive.
anonymous
Objectives
Explore more issues in logical architecture and the Layers pattern, including
inter-layer collaboration.
Present the logical architecture for this iteration of the case studies.
Apply the Facade, Observer, and Controller patterns in the context of
architectural layers.
 

<<<PDF_PAGE 760>>>
 
Introduction
Logical architecture and the Layers pattern was introduced starting on p. 197
. This chapter dives
a bit deeperlooking at some intermediate topics related to layered architectures.
[View full size image]
 
 

<<<PDF_PAGE 761>>>
 
34.1. Example: NextGen Logical Architecture
example of common layers
 p. 202
Figure 34.1
 illustrates a partial logical layered architecture for this iteration of NextGen
application.
Figure 34.1. Partial logical view of layers in the NextGen application.
[View full size image]
Note the absence of an Application layer for this iteration of the design; as discussed later, it is
<<<PDF_PAGE 762>>>
not always necessary.
Since this is iterative development, it is normal to create a design of layers that starts simple, and
evolves over the iterations of the elaboration phase. One goal of this phase is to have the core
architecture established (designed and implemented) by the end of the iterations in elaboration,
but this does not mean doing a large up-front speculative architectural design before starting to
program. Rather, a tentative logical architecture is designed in the early iterations, and it evolves
incrementally through the elaboration phase.
Observe that just a few sample types are present in this package diagram; this is not only
motivated by limited page space in formatting this book, but is a signature quality of an
architectural view diagramit only shows a few noteworthy elements in order to concisely
convey the big ideas of the architecturally significant aspects. The idea in a UP architectural view
document is to say to the reader, "I've chosen this small set of instructive elements to convey the
big ideas."
Comments on Figure 34.1
:
There are other types in these packages; only a few are shown to indicate noteworthy
aspects.
The Foundation layer was not shown in this view; the architect (me) decided it did not add
interesting information, even though the development team will certainly be adding some
Foundation classes, such as more advanced String manipulation utilities.
For now, a separate Application layer is not used. The responsibilities of control or session
objects in the Application layer are handled by the Register object. The architect will add an
Application layer in a later iteration as the behavior grows in complexity, and alternative
client interfaces are introduced (such as a Web browser and wireless networked handheld
PDA).
Inter-Layer and Inter-Package Coupling
To help someone understand the NextGen logical architecture, it's also informative to include a
diagram in the logical view that illustrates noteworthy coupling between the layers and packages.
A partial example is illustrated in Figure 34.2
.
Figure 34.2. Partial coupling between packages.
[View full size image]
<<<PDF_PAGE 763>>>
Applying UML:
Observe that dependency lines can be used to communicate coupling between packages or
types in packages. Plain dependency lines are excellent when the communicator does not
care to be more specific on the exact dependency (attribute visibility, subclassing, …), but
just wants to highlight general dependencies.
Note also the use of a dependency line emitting from a package rather than a particular
type, such as from the Sales package to POSRuleEngineFacade class, and the Domain
package to the Log4J package. This is useful when either the specific dependent type is not
interesting, or the communicator wants to suggest that many elements of the package may
share that dependency.
Another common use of a package diagram is to hide the specific types, and focus on illustrating
the package-package coupling, as in the partial diagram of Figure 34.3
.
Figure 34.3. Partial package coupling.
<<<PDF_PAGE 764>>>
In fact, Figure 34.3
 illustrates probably the most common style of logical architecture diagram in
the UMLa package diagram that shows between perhaps 5 to 20 major packages, and their
dependencies.
Inter-Layer and Inter-Package Interaction Scenarios
Package diagrams show static information. To help someone understand the dynamics in the
NextGen logical architecture, it's also useful to include a diagram of how objects across the layers
connect and communicate. Thus, an interaction diagram is helpful. In the spirit of an
"architectural view" which hides uninteresting details, and emphasizes what the architect wants to
convey, an interaction diagram in the logical view of the architecture focuses on the collaborations
as they cross layer and package boundaries. A set of interaction diagrams that illustrate
architecturally significant scenarios (in the sense that they illustrate many aspects of the
large-scale or big ideas in the design) is thus useful.
For example, Figure 34.4
 illustrates part of a Process Sale scenario that emphasizes the
connection points across the layers and packages.
<<<PDF_PAGE 765>>>
Figure 34.4. An architecturally significant interaction diagram that
emphasizes cross-boundary connections.
[View full size image]
Applying UML:
The package of a type can optionally be shown by qualifying the type with the UML path
name expression <PackageName>::<TypeName>. For example, Domain::Sales::Register.
This can be exploited to highlight to the reader the inter-package and inter-layer
connections in the interaction diagram.
Note also the use of the «subsystem» stereotype. In the UML, a subsystem is a discrete
entity that has behavior and interfaces. A subsystem can be modeled as a special kind of
package, oras shown hereas an object, which is useful when one wants to show inter-
subsystem (or system) collaborations. In the UML, the entire system is also a "subsystem"
(the root one), and thus can also be shown as an object in interaction diagrams (such as an
SSD).
Note the use of the '1' in the top right corner to indicate a singleton, and suggest access
using the GoF Singleton pattern.
Observe that the diagram ignores showing some messages, such as certain Sale collaborations, in
order to highlight architecturally significant interactions.
 

<<<PDF_PAGE 766>>>
 
34.2. Collaborations with the Layers Pattern
Two design decisions at an architectural level are:
What are the big parts?1.
How are they connected?2.
Whereas the architectural Layers pattern guides defining the big parts, micro-architectural design
patterns such as Facade, Controller, and Observer are commonly used for the design of the
connections between layers and packages. This section examines patterns in connection and
communication between layers and packages.
Simple Packages versus Subsystems
Some packages or layers are not just conceptual groups of things, but are true subsystems with
behavior and interfaces. To contrast:
The Pricing package is not a subsystem; it simply groups the factory and strategies used in
pricing. Likewise with Foundation packages such as java.util.
On the other hand, the Persistence, POSRuleEngine, and Jess packages are subsystems.
They are discrete engines with cohesive responsibilities that do work.
In the UML, a subsystem can be identified with a stereotype, as in Figure 34.5
.
Figure 34.5. Subsystem stereotypes.

<<<PDF_PAGE 767>>>
Facade
For packages that represent subsystems, the most common pattern of access is Facade, a GoF
design pattern. That is, a public facade object defines the services for the subsystem, and clients
collaborate with the facade, not internal subsystem components. This is true of the
POSRuleEngineFacade and the PersistenceFacade for access to the rules engine and persistence
subsystem.
The facade should not normally expose many low-level operations. Rather, it is desirable for the
facade to expose a small number of high-level operationsthe coarse-grained services. When a
facade does expose many low-level operations, it tends to become incohesive. Furthermore, if the
facade will be, or might become, a distributed or remote object (such as an EJB session bean, or
RMI server object), fine-grained services lead to remote communication performance
problemslots of little remote calls are a performance bottleneck in distributed systems.
Also, a facade does not normally do its own work. Rather, it is consolidator or mediator to the
underlying subsystem objects, which do the work.
For example, the POSRuleEngineFacade is the wrapper and single point of access into the rules
engine for the POS application. Other packages do not see the implementation
 of this subsystem,
as it is hidden behind the facade. Suppose (this is just one of many implementations) that the
POS rules engine subsystem is implemented by collaborating with the Jess rules engine. Jess is a
subsystem that exposes many fine-grained operations (this is common for very general, third-
party subsystems). But the POSRuleEngineFacade does not expose the low-level Jess operations
in its interface. Rather, it provides only a few high-level operation such as isInvalid(lineItem,
sale).
If the application has only a "small" number of system operations, then it is common for the
Application or Domain layer to expose only one object to an upper layer. On the other hand, the
Technical Services layer, which contains several subsystems, exposes at least one facade (or
several public objects, if facades aren't used) for each subsystem to upper layers. See Figure
34.6
.
Figure 34.6. Number of interfaces exposed to upper layers.
<<<PDF_PAGE 768>>>
Session Facades and the Application Layer
In contrast to Figure 34.6
, when an application has many system operations and supports many
use cases, it is common to have more than one object mediating between the UI and Domain
layers.
In the current version of the NextGen system, there is a simple design of a single Register object
acting as the facade onto the Domain layer (by virtue of the GRASP controller pattern).
However, as the system grows to handle many use cases and system operations, it is not
uncommon to introduce an Application layer of objects that maintain session state for the
operations of a use case, where each session instance represents a session with one client. These
are called Session Facades, and their use is another recommendation of the GRASP Controller
pattern, such as in the use-case session facade controller variant of the pattern. See Figure 34.7
for an example of how the NextGen architecture may evolve with an Application layer and session
facades.
Figure 34.7. Session facades and an Application Layer.
<<<PDF_PAGE 769>>>
Controller
The GRASP Controller pattern describes common choices in client-side handlers (or controllers, as
they've been called) for system operation requests emitting from the UI layer. Figure 34.8
illustrates.
Figure 34.8. The Controller choices.
<<<PDF_PAGE 770>>>
System Operations and Layers
The SSDs illustrate the system operations, hiding UI objects from the diagram. The system
operations being invoked on the system in Figure 34.9
 are requests being generated by an actor
via the UI layer, onto the Application or Domain layer.
Figure 34.9. System operations in the SSDs and in terms of layers.
[View full size image]

<<<PDF_PAGE 771>>>
Upward Collaboration with Observer
The Facade pattern is commonly used for "downward" collaboration from a higher to a lower
layer, or for access to services in another subsystem of the same layer. When the lower
Application or Domain layer needs to communicate upward with the UI layer, it is usually via the
Observer pattern. That is, UI objects in the higher UI layer implement an interface such as
PropertyListener or AlarmListener, and are subscribers or listeners to events (such as property or
alarm events) coming from objects in the lower layers. The lower layer objects are directly
sending messages to the upper layer UI objects, but the coupling is only to the objects viewed as
things that implement an interface, such as PropertyListener, not viewed as specific GUI windows.
This was examined when the Observer pattern was introduced. Figure 34.10
 summarizes the idea
in relation to layers.
Figure 34.10. Observer for "upward" communication to the UI layer.
[View full size image]
Relaxed Layered Coupling
The layers in most layered architectures are not coupled in the same limited sense as a network
protocol based on the OSI 7-Layer Model. In the protocol model, there is strict restriction that
elements of layer N only access the services of the immediate lower layer N-1.
This is rarely followed in information system architectures. Rather, the standard is a "relaxed
layered" or "transparent layered" architecture [BMRSS96
], in which elements of a layer
collaborate with or are coupled to several other layers.
Comments on typical coupling between layers:
<<<PDF_PAGE 772>>>
All higher layers have dependencies on the Technical Services and Foundations layer.
For example, in Java all layers depend on java.util package elements.
It is primarily the Domain layer that has dependency on the Business Infrastructure layer.
The UI layer makes calls on the Application layer, which makes service calls on the Domain
layer; the UI layer does not call on the Domain, unless there is no Application layer.
If it is a single-process "desktop" application, software objects in the Domain layer are
directly visible to, or passed between, UI, Application, and to a lesser extent, Technical
Services.
For example, assuming the NextGen POS system is of this type, a Sale and a Payment
object could be directly visible to the GUI UI Layer, and also passed into the
Persistence subsystem in the Technical Services layer.
On the other hand, if it is a distributed system, then serializable replicates (also known as
data holder or value objects) of objects in the Domain layer are usually passed to a UI
layer. In this case, the Domain layer is deployed on a server computer, and client nodes get
copies of server data.
Isn't Coupling to Technical and Foundation Layers Dangerous?
As the GRASP Protected Variations and Low Coupling discussions explored, it is not coupling per
se that is a problem, but unnecessary coupling to variation and evolution points that are unstable
and expensive to fix. There is very little justification in spending time and money attempting to
abstract or hide something that is unlikely to change, or if it did, the change impact cost would be
negligible. For example, if building a Java technologies application, what value is there in hiding
the application from access to the Java libraries? High coupling into many points of the libraries is
an unlikely problem, as they are (relatively) stable and ubiquitous.
 

<<<PDF_PAGE 773>>>
 
34.3. Other Layer Pattern Issues
In addition to the structural and collaboration issues discussed above for the Layers pattern, other
issues include the following.
Logical versus Process and Deployment Views of the Architecture
The architectural layers are a logical view of the architecture, not a deployment view of elements
to processes and processing nodes. Depending on the platform, all layers could be deployed
within the same process on the same node, such as an application within a handheld PDA, or
spread across many computers and processes for a large-scale Web application.
The UP Deployment Model that maps this logical architecture to processes and nodes is strongly
influenced by the choice of software and hardware platform and associated application
frameworks. For example, J2EE versus .NET influence the deployment architecture.
There are many ways to slice and dice these logical layers for deployment, and in general the
subject of deployment architecture will only be lightly introduced, as it is non-trivial, largely
outside the scope of the book, and dependent on detailed discussion of the chosen software
platform, such as J2EE.
Is the Application Layer Optional?
If present, the Application layer contains objects responsible for knowing the session state of
clients, mediating between the UI and Domain layers, and controlling the flow of work.
The flow may be organized by controlling the order of windows or web pages, for example.
In terms of the GRASP patterns, GRASP Controller objects such as a use case facade controller
are part of this layer. In distributed systems, components such as EJB session beans (and stateful
session objects in general) are part of this layer.
In some applications, this layer is not required. It is useful (this is not an exhaustive list) when
one or more of the following is true:
Multiple user interfaces (for example, web pages and a Swing GUI) will be used for the
system. The Application layer objects can act as Adapters that collect and consolidate the
data as needed for different UIs, and as Facades that wrap and hide access to the Domain
layer.
It is a distributed system and the Domain layer is on a different node than the UI layer, and
shared by multiple clients. It is usually necessary to keep track of session state, and
Application layer objects are a useful choice for this responsibility.
The Domain Layer cannot or should not maintain session state.
There is a defined workflow in terms of the controlled order of windows or Web pages that
must be presented.
<<<PDF_PAGE 774>>>
Fuzzy Set Membership in Different Layers
Some elements are strongly a member of one layer; a Math class is part of the Foundation layer.
However, especially between the Technical Services and Foundation layers, and Domain and
Business Infrastructure, some elements are harder to classify, because the differentiation
between these layers is, roughly, "high" versus "low," or "specific" versus "general." which are
fuzzy set terms. This is normal, and it is seldom necessary to decide upon a definitive
categorizationthe development team may consider an element roughly part of the Technical
Services and/or Foundations layer considered as a group, broadly called the Infrastructure
layer.[1]
[1] Note that there are not well-established naming conventions for layers, and name overloading and contradiction in the
architecture literature is common.
For example:
Suppose this is a Java technologies project, and the open source logging framework Log4J
(part of the Jakarta project) has been chosen. Is logging part of the Technical Service or
Foundation layer? Log4J is a low-level, small, general framework. It is moderately a member
of both the Technical Services and the Foundations fuzzy sets.
Suppose this is a Web application, and the Jakarta Struts framework for web applications
has been chosen. Struts is a relatively high-level, large, specific technical framework. It is
arguably strongly a member of the Technical Services set, and weakly a member of the
Foundation set.
But, one person's High-level Technical Service is another's Foundation…
Finally, it is not the case that the libraries provided by a software platform only represent low-
level Foundation services. For example, in both .NET and J2SE+J2EE, services include relatively
high-level functions such as naming and directory services.
Contraindications and Liabilities for Layers
In some contexts, adding layers introduces performance problems. For example, in a high-
performance graphics-intensive game, adding layers of abstraction and indirection on top of
direct access to graphics card components may introduce performance problems.
The Layers pattern is one of several core architectural patterns; it is not applicable to every
problem. For example, an alternate is Pipes and Filters [BMRSS96
]. This is useful when the
main theme of the application involves processing something through a series
transformations, such as image transformations, and the ordering of the transformations is
changeable. Yet even in the case when the highest level architectural pattern is Pipes and
Filters, individual pipes or filters can be design, with Layers.
Known Uses
A vast number of modern object-oriented systems (from desktop applications to distributed J2EE
Web systems) are developed with Layers; it might be harder to find one that is not, than is. Going
<<<PDF_PAGE 775>>>
farther back in history:
Virtual Machines and Operating Systems
Starting in the 1960s, operating system architects advocated the design of operating systems in
terms of clearly defined layers, where the "lower" layers encapsulated access to the physical
resources and provided process and I/O services, and higher layers called on these services.
These included Multics [CV65
] and the THE system [Dijkstra68
].
Earlier stillin the 1950sresearchers suggested the idea of a virtual machine (VM) with a bytecode
universal machine language (for example, UNCOL [Conway1958]), so that applications could be
written at higher layers in the architecture (and executed without recompilation across different
platforms), on top of the virtual machine layer, which in turn would sit on top of the operating
system and machine resources. A VM layered architecture was applied by Alan Kay in his
landmark Flex object-oriented personal computer system [Kay68
] and later (1972) by Kay and
Dan Ingalls in the influential Smalltalk virtual machine [GK76
]the progenitor of more recent VMs
such as the Java Virtual Machine.
Information Systems: The Classic Three-Tier Architecture
An early influential description of a layered architecture for information systems that included a
user interface and persistent storage of data was known as a three-tier architecture (Figure
34.11
), described in the 1970s in [TK78
]. The phrase did not achieve popularity until the mid
1990s, in part due to its promotion in [Gartner95
] as a solution to problems associated with the
widespread use of two-tier architectures.
Figure 34.11. Classic view of a three-tier architecture.
The original term is now less common, but its motivation is still relevant.
A classic description of the vertical tiers in a three-tier architecture is:
1.
<<<PDF_PAGE 776>>>
Interface windows, reports, and so on.1.
Application Logic tasks and rules that govern the process.2.
Storage persistent storage mechanism.3.
The singular quality of a three-tier architecture is the separation of the application logic into a
distinct logical middle tier of software. The interface tier is relatively free of application
processing; windows or Web pages forward task requests to the middle tier. The middle tier
communicates with the back-end storage layer.
There was some misunderstanding that the original description implied or required a physical
deployment on three computers, but the intended description was purely logical; the allocation of
the tiers to compute nodes could vary from one to three. See Figure 34.12
.
Figure 34.12. A three-tier logical division deployed in two physical
architectures.
[View full size image]
The three-tier architecture was contrasted by the Gartner Group with a two-tier design, in which,
for example, application logic is placed within window definitions, which read and write directly to
a database; there is no middle tier that separates out the application logic. Two-tier client-server
architectures became especially popular with the rise of tools such as Visual Basic and
PowerBuilder.
Two-tier designs have (in some cases) the advantage of initial quick development, but can suffer
the complaints covered in the Problems section. Nevertheless, there are applications that are
primarily simple CRUD (create, retrieve, update, delete) data intensive systems, for which this is
a suitable choice.
Related Patterns
Indirection layers can add a level of indirection to lower-level services.
<<<PDF_PAGE 777>>>
Protected Variation layers can protect against the impact of varying implementations.
Low Coupling and High Cohesion layers strongly support these goals.
Its application specifically to object-oriented information systems is described in [Fowler96
].
Also Known As
The Layers pattern is also known as Layered Architecture [Shaw96
, Gemstone00
].
 

<<<PDF_PAGE 778>>>
 
34.4. Model-View Separation and "Upward"
Communication
How can windows obtain information to display? Usually, it is sufficient for them to send messages
to domain objects, querying for information which they then display in widgetsa polling or pull-
from-above model of display updates.
However, a polling model is sometimes insufficient. For example, polling every second across
thousands of objects to discover only one or two changes, which are then used to refresh a GUI
display, is not efficient. In this case it is more efficient for the few changing domain objects to
communicate with windows to cause a display update as the state of domain objects changes.
Typical situations of this case include:
Monitoring applications, such as telecommunications network management.
Simulation applications that require visualization, such as aerodynamics modeling.
In these situations, a push-from-below model of display update is required. Because of the
restriction of the Model-View Separation pattern, this leads to the need for "indirect"
communication from lower objects up to windowspushing up notification to update from below.
There are two common solutions:
The Observer pattern, via making the GUI object simply appear as an object that
implements an interface such as PropertyListener.
1.
A UI facade object. That is, adding a facade within the UI layer that receives requests from
below. This is an example of adding Indirection to provide Protected Variation if the GUI
changes. For example, see Figure 34.13
.
Figure 34.13. A UI layer UIFacade is occasionally used for push-
from-below designs.
2.
<<<PDF_PAGE 779>>>
 

<<<PDF_PAGE 780>>>
 
34.5. Recommended Resources
There's a wealth of literature on layered architectures, both in print and on the Web. A series of
patterns in Pattern Languages of Program Design, volume 1, [CS95
] first address the topic in
pattern form, although layered architectures have been used and written about since at least the
1960s; volume 2 continues with further layers-related patterns. Pattern-Oriented Software
Architecture volume 1 [BMRSS96
] provides a good treatment of the Layers pattern.
 

# Chapter 38. Designing a Persistence Framework with Patterns


<<<PDF_PAGE 833>>>
 
Chapter 38. Designing a Persistence
Framework with Patterns
The most likely way for the world to be destroyed, most experts agree, is by accident. That's
where we come in; we're computer professionals. We cause accidents.
Nathaniel Borenstein
Objectives
Design part of a framework with the Template Method, State, and Command
patterns.
Introduce issues in object-relational (O-R) mapping.
Implement lazy materialization with Virtual Proxies.
 

<<<PDF_PAGE 834>>>
 
Introduction
The point of this chapter is not actually the design of a persistence framework, but, more
generally, to introduce key OO framework design principles and patterns, using persistence as an
interesting case study.
[View full size image]
The NextGen applicationlike mostrequires storing and retrieving information in a persistent
storage mechanism, such as a relational database (RDB). This chapter explores the design of a
framework for storing persistent objects.
Caution! Don't Try This at Home!
There are excellent free, robust, industrial-strength open source persistence
frameworks, and thus seldom a need to create one yourself. For example, Hibernate
is very widely used in the Java domain (www.hibernate.org). It solves most or all
problems in object-relational mapping, performance, transaction support, and so
forth.
This persistence framework is presented to introduce framework design applied to a
common and problem-rich domain. It is not recommended for an industrial
persistence service. At least for Java technologies, there is no need to create one
yourself.
 

<<<PDF_PAGE 835>>>
 
38.1. The Problem: Persistent Objects
Assume that in the NextGen application, ProductDescription data resides in a relational database.
It must be brought into local memory during application use. Persistent objects
 are those that
require persistent storage, such as ProductDescription instances.
Storage Mechanisms and Persistent Objects
Object databases If an object database is used to store and retrieve objects, no additional
custom or third-party persistence services are required. This is one of several attractions for its
use. However, they are relatively rare.
Relational databases Because of the prevalence of RDBs, their use is often required, rather
than the more OO-natural object databases. If this is the case, a number of problems arise due to
the mismatch between record-oriented and object-oriented representations of data; these
problems are explored later. A special O-R mapping service is required.
Other In addition to RDBs, it is sometimes desirable to store objects in other storage
mechanisms or formats, such as flat files, XML structures, Palm OS PDB files, hierarchical
databases, and so on. As with relational databases, a representation mismatch exists between
objects and these non-object-oriented formats. And as with RDBs, special services are required to
make them work with objects.
 

<<<PDF_PAGE 836>>>
 
38.2. The Solution: A Persistence Service from a
Persistence Framework
A persistence framework is a general-purpose, reusable, and extendable set of types that
provides functionality to support persistent objects. A persistence service (or subsystem)
actually provides the service, and will be created with a persistence framework. A persistence
service is usually written to work with RDBs, in which case it is also called an O-R mapping
service. Typically, a persistence service must translate objects into records (or some other form
of structured data such as XML) and save them in a database, and translate records into objects
when retrieving from a database.
In terms of the layered architecture of the NextGen application, a persistence service is a
subsystem within the technical services layer.
 

<<<PDF_PAGE 837>>>
 
38.3. Frameworks
At the risk of oversimplification, a framework is an extendable set of objects for related functions.
The quintessential example is a GUI framework, such as Java's Swing framework.
The signature quality of a framework is that it provides an implementation for the core and
unvarying functions, and includes a mechanism to allow a developer to plug in the varying
functions, or to extend the functions.
For example, Java's Swing GUI framework provides many classes and interfaces for core GUI
functions. Developers can add specialized widgets by subclassing from the Swing classes and
overriding certain methods. Developers can also plug in varying event response behavior to
predefined widget classes (such as JButton) by registering listeners or subscribers based on the
Observer pattern. That's a framework.
In general, a framework
:
Is a cohesive set of interfaces and classes that collaborate to provide services for the core,
unvarying part of a logical subsystem.
Contains concrete (and especially) abstract classes that define interfaces to conform to,
object interactions to participate in, and other invariants.
Usually (but not necessarily) requires the framework user to define subclasses of existing
framework classes to make use of, customize, and extend the framework services.
Has abstract classes that may contain both abstract and concrete methods.
Relies on the Hollywood Principle "Don't call us, we'll call you." This means that the user-
defined classes (for example, new subclasses) will receive messages from the predefined
framework classes. These are usually handled by implementing superclass abstract
methods.
The following persistence framework example will demonstrate these principles.
Frameworks Are Reusable
Frameworks offer a high degree of reusemuch more so than individual classes. Consequently, if
an organization is interested (and who isn't?) in increasing its degree of software reuse, then it
should emphasize the creation of frameworks.
 

<<<PDF_PAGE 838>>>
 
38.4. Requirements for the Persistence Service and
Framework
For the NextGen POS application, we need a persistence service to be built with a persistence
framework (which could be used to also create other persistence services). Let's call the
framework PFW (Persistence Framework). PFW is a simplified frameworka full-blown, industrial-
strength persistence framework is outside the scope of this introduction.
The framework should provide functions such as:
store and retrieve objects in a persistent storage mechanism
commit and rollback transactions
The design should be extendable to support different storage mechanisms and formats, such as
RDBs, records in flat files, or XML in files.
 

<<<PDF_PAGE 839>>>
 
38.5. Key Ideas
The following key ideas will be explored in subsequent sections:
Mapping There must be some mapping between a class and its persistent store (for
example, a table in a database), and between object attributes and the fields (columns) in a
record. That is, there must be a schema mapping between the two schemas.
Object identity To easily relate records to objects, and to ensure there are no
inappropriate duplicates, records and objects have a unique object identifier.
Database mapper A Pure Fabrication database mapper is responsible for materialization
and dematerialization.
Materialization and dematerialization Materialization is the act of transforming a non-
object representation of data (for example, records) from a persistent store into objects.
Dematerialization is the opposite activity (also known as passivation).
Caches Persistence services cache materialized objects for performance.
Transaction state of object It is useful to know the state of objects in terms of their
relationship to the current transaction. For example, it is useful to know which objects have
been modified (are dirty) so that it is possible to determine if they need to be saved back to
their persistent store.
Transaction operations Commit and rollback operations.
Lazy materialization Not all objects are materialized at once; a particular instance is only
materialized on-demand, when needed.
Virtual proxies Lazy materialization can be implemented using a smart reference known as
a virtual proxy.
 

<<<PDF_PAGE 840>>>
 
38.6. Pattern: Representing Objects as Tables
How do you map an object to a record or relational database schema?
The Representing Objects as Tables pattern [BW96
] proposes defining a table in an RDB for
each persistent object class. Object attributes containing primitive data types (number, string,
boolean, and so on) map to columns.
If an object has only attributes of primitive data types, the mapping is straightforward. But as we
will see, matters are not that simple, since objects may have attributes that refer to other
complex objects, while the relational model requires that values be atomic (that is, First Normal
Form) (see Figure 38.1
).
Figure 38.1. Mapping objects and tables.
[View full size image]
 

<<<PDF_PAGE 841>>>
 
38.7. UML Data Modeling Profile
While on the subject of RDBs, not surprisingly, the UML has become a popular notation for data
models. Note that one of the official UP artifacts is the Data Model, which is part of the Design
discipline. Figure 38.2
 illustrates some notation in the UML for data modeling.
Figure 38.2. UML Data Modeling Profile example.
These stereotypes are not part of the core UMLthey are an extension. To generalize, the UML has
the concept of a UML profile: a coherent set of UML stereotypes, tagged values, and constraints
for a particular purpose. Figure 38.2
 illustrates part of a proposed Data Modeling Profile.
 

<<<PDF_PAGE 842>>>
 
38.8. Pattern: Object Identifier
It is desirable to have a consistent way to relate objects to records, and to be able to ensure that
repeated materialization of a record does not result in duplicate objects.
The Object Identifier pattern [BW96
] proposes assigning an object identifier (OID) to each
record and object (or proxy of an object).
An OID is usually an alphanumeric value; each is unique to a specific object. There are various
approaches to generating unique IDs for OIDs, ranging from unique to one database, to globally
unique: database sequence generators, the High-Low key generation strategy [Ambler00
], and
others.
Within object land, an OID is represented by an OID interface or class that encapsulates the
actual value and its representation. In an RDB, it is usually stored as a fixed length character
value.
Every table will have an OID as primary key, and each object will (directly or indirectly) also have
an OID. If every object is associated with an OID, and every table has an OID primary key, every
object can be uniquely mapped to some row in some table (see Figure 38.3
).
Figure 38.3. Object identifiers link objects and records.
[View full size image]
This is a simplified view of the design. In reality, the OID may not actually be placed in the
persistent objectalthough that is possible. Instead, it may be placed in a Proxy object wrapping
the persistent object. The design is influenced by the choice of language.
An OID also provides a consistent key type to use in the interface to the persistence service.
 

<<<PDF_PAGE 843>>>
 
38.9. Accessing a Persistence Service with a Facade
Step one in the design of this subsystem is to define a facade for its services; recall that Facade is
a common pattern to provide a unified interface to a subsystem. To begin, an operation is needed
to retrieve an object given an OID. But in addition to an OID, the subsystem needs to know what
type of object to materialize; therefore, the class type will also be provided. Figure 38.4
 illustrates
some operations of the facade and its use in collaboration with one of the NextGen service
adapters.
Figure 38.4. The PersistenceFacade.
[View full size image]
 

<<<PDF_PAGE 844>>>
 
38.10. Mapping Objects: Database Mapper or Database
Broker Pattern
The PersistenceFacadeas true of all facadesdoes not do the work itself, but delegates requests to
subsystem objects.
Who should be responsible for materialization and dematerialization of objects (for example, a
ProductDescription) from a persistent store?
The Information Expert pattern suggests that the persistent object class itself
(ProductDescription) is a candidate, because it has some of the data (the data to be saved)
required by the responsibility.
If a persistent object class defines the code to save itself in a database, it is called a direct
mapping design. Direct mapping is workable if the database related code is automatically
generated and injected into the class by a post-processing compiler, and the developer never has
to see or maintain this complex database code cluttering his or her class.
But if direct mapping is manually added and maintained, it has a number of defects and does not
tend to scale well in terms of programming and maintenance. Problems include:
Strong coupling of the persistent object class to persistent storage knowledgeviolation of
Low Coupling.
Complex responsibilities in a new and unrelated area to what the object was previously
responsible forviolation of High Cohesion and maintaining a separation of concerns.
Technical service concerns are mixing with application logic concerns.
We will explore a classic indirect mapping approach, that uses other objects to do the mapping
for persistent objects.
Part of this approach is to use the Database Broker pattern [BW95
]. It proposes making a class
that is responsible for materialization, dematerialization, and object caching. This has also been
called the Database Mapper pattern in [Fowler01
], which is a better name than Database
Broker, as it describes its responsibility, and the term "broker" in distributed systems [BMRSS96
]
design has a long-standing and different meaning.[1]
[1] In distributed systems, a broker is a front-end server process that delegates tasks to back-end server processes.
A different mapper class is defined for each persistent object class. Figure 38.5
 illustrates that
each persistent object may have its own mapper class, and that there may be different kinds of
mappers for different storage mechanisms. A snippet of code:
class PersistenceFacade
{
//
...
public Object get( OID oid, Class persistenceClass )
{
   
// an IMapper is keyed by the Class of the persistent object
   
IMapper mapper = (IMapper) mappers.get( persistenceClass );
<<<PDF_PAGE 845>>>
   
// delegate
   
return mapper.get( oid );
}
//...
}
Figure 38.5. Database Mappers.
[View full size image]
Although this diagram indicates two ProductDescription mappers, only one will be active within a
running persistence service.
Metadata-Based Mappers
More flexible, but more involved, is a mapper design based on metadata (data about data). In
contrast to hand-crafting individual mapper classes for different persistent types, metadata-based
mappers dynamically generate the mapping from an object schema to another schema (such as
relational) based on reading in metadata that describes the mapping, such as "TableX maps to
Class Y; column Z maps to object property P" (it gets much more complex). This approach is
feasible for languages with reflective programming capabilities, such as Java, C#, or Smalltalk,
and awkward for those that don't, such as C++.
With metadata-based mappers, we can change the schema mapping in an external store and it
will be realized in the running system, without changing source codeProtected Variations with
respect to schema variations.
<<<PDF_PAGE 846>>>
Nevertheless, a useful quality of the framework presented here is that hand-coded or metadata
mappers can be used without affecting clientsencapsulation of the implementation.
 

<<<PDF_PAGE 847>>>
 
38.11. Framework Design with the Template Method
Pattern
The next section describes some of the essential design features of the Database Mappers, which
are a central part of the PFW. These design features are based on the Template Method GoF
design pattern [GHJV95
].[2]
 This pattern is at the heart of framework design,[3]
 and is familiar to
most OO programmers by practice if not by name.
[2] This pattern is unrelated to C++ templates. It describes the template of an algorithm.
[3] More specifically, of whitebox frameworks. These are usually class hierarchy and subclassing-oriented frameworks that
require the user to know something about their design and structure; hence, whitebox.
The idea is to define a method (the Template Method) in a superclass that defines the skeleton of
an algorithm, with its varying and unvarying parts. The Template Method invokes other methods,
some of which are methods that may be overridden in a subclass. Thus, subclasses can override
the varying methods in order to add their own unique behavior at points of variability (see Figure
38.6
).
Figure 38.6. Template Method pattern in a GUI framework.
[View full size image]
 

<<<PDF_PAGE 848>>>
 
38.12. Materialization with the Template Method Pattern
If we were to program two or three mapper classes, some commonality in the code would become
apparent. The basic repeating algorithm structure for materializing an object is:
if (object in cache)
   
return it
else
   
create the object from its representation in storage
   
save object in cache
   
return it
The point of variation is how the object is created from storage.
We will create the get method to be the template method in an abstract superclass
AbstractPersistenceMapper that defines the template, and use a hook method in subclasses for
the varying part. Figure 38.7
 shows the essential design.
Figure 38.7. Template Method for mapper objects.
[View full size image]
As shown in this example, it is common for the template method to be public, and the hook
method to be protected. AbstractPersistenceMapper and IMapper are part of the PFW. Now, an
application programmer can plug into this framework by adding a subclass, and overriding or
implementing the getObjectFromStorage hook method. Figure 38.8
 shows an example.
<<<PDF_PAGE 849>>>
Figure 38.8. Overriding the hook method.[4]
[View full size image]
[4] In Java as an example, the dbRec that is returned from executing a SQL query will be a JDBC ResultSet.
Assume in the hook method implementation of Figure 38.8
 that the beginning part of the
algorithmdoing a SQL SELECTis the same for all objects, only the database table name varies.[5]
If that assumption held, then once again, the Template Method pattern could be applied to factor
out the varying and unvarying parts of the algorithm. In Figure 38.9
, the tricky part is that
AbstractRDBMapper.getObjectFromStorage is a hook method with respect to
AbstractPersistenceMapper.get, but a template method with respect to the new hook method
getObjectFromRecord.
[5] In many cases, the situation is not so simple. An object may be derived from data from two or more tables or from multiple
databases, in which case, the first version of the Template Method design offers more flexibility.
Figure 38.9. Tightening up the code with the Template Method again.
[View full size image]
<<<PDF_PAGE 850>>>
UML In Figure 38.9
 observe how constructors can be declared in the UML. The stereotype is
optional, and if the naming convention of constructor name equal to class name is used, probably
unnecessary.
Now, IMapper, AbstractPersistenceMapper, and AbstractRDBMapper are part of the framework.
The application programmer needs only to add his or her subclass, such as
ProductDescriptionRDBMapper, and ensure it is created with the table name (to pass via
constructor chaining up to the AbstractRDBMapper).
The Database Mapper class hierarchy is an essential part of the framework; new subclasses may
be added by the application programmer to customize it for new kinds of persistent storage
mechanisms or for new particular tables or files within an existing storage mechanism. Figure
38.10
 shows some of the package and class structure. Notice that the NextGen-specific classes do
not belong in the general technical services Persistence package. I think this diagram, combined
with Figure 38.9
, illustrates the value of a visual language like the UML to describe parts of
software; this succinctly conveys much information.
Figure 38.10. The persistence framework.
[View full size image]
<<<PDF_PAGE 851>>>
In Figure 38.10
 notice the class ProductDescriptionInMemoryTestDataMapper. Such classes can
be used to serve up hard-coded objects for testing, without accessing any external persistent
store.
The UP and the Software Architecture Document
In terms of the UP and documentation, recall that the SAD is a learning aid for future developers,
which contains architectural views of key noteworthy ideas. Including diagrams such as Figure
38.9
 and Figure 38.10
 in the SAD for the NextGen project is very much in the spirit of the kind of
information an SAD should contain.
Synchronized or Guarded Methods in the UML
The AbstractPersistenceMapper.get method contains critical section code that is not thread
safethe same object could be materializing concurrently on different threads. As a technical
service subsystem, the persistence service needs to be designed with thread safety in mind.
Indeed, the entire subsystem may be distributed to a separate process on another computer, with
the PersistenceFacade transformed into a remote server object, and with many threads
simultaneously running in the subsystem, serving multiple clients.
The method should therefore have thread concurrency controlif using Java, add the synchronized
keyword. Figure 38.11
 illustrates a synchronized method in a class diagram.
Figure 38.11. Guarded methods in the UML.
<<<PDF_PAGE 852>>>
[View full size image]
 

<<<PDF_PAGE 853>>>
 
38.13. Configuring Mappers with a MapperFactory
Similar to previous examples of factories in the case study, the configuration of the
PersistenceFacade with a set of IMapper objects can be achieved with a factory object,
MapperFactory. However, as a slight twist, it is desirable to not name each mapper with a
different operation. For example, this is not desirable:
class MapperFactory
{
public IMapper getProductDescriptionMapper() {...}
public IMapper getSaleMapper() {...}
...
}
This does not support Protected Variations with respect to a growing list of mappersand it will
grow. Consequently, the following is preferred:
class MapperFactory
{
public Map getAllMappers() {...}
...
}
where the java.util.Map (probably implemented with a HashMap) keys are the Class objects (the
persistent types), and the IMappers are the values.
Then, the facade can initialize its collection of IMappers as follows:
class PersistenceFacade
{
private java.util.Map mappers =
   
MapperFactory.getInstance().getAllMappers();
...
}
The factory can assign a set of IMappers using a data-driven design. That is, the factory can read
system properties to discover which IMapper classes to instantiate. If a language with reflective
programming capabilities is used, such as Java, then the instantiation can be based on reading in
the class names as strings, and using something like a Class.newInstance operation for
instantiation. Thus, the mapper set can be reconfigured without changing the source code.
 

<<<PDF_PAGE 854>>>
 
38.14. Pattern: Cache Management
It is desirable to maintain materialized objects in a local cache to improve performance
(materialization is relatively slow) and support transaction management operations such as a
commit.
The Cache Management pattern [BW96
] proposes making the Database Mappers responsible
for maintaining its cache. If a different mapper is used for each class of persistent object, each
mapper can maintain its own cache.
When objects are materialized, they are placed in the cache, with their OID as the key.
Subsequent requests to the mapper for an object will cause the mapper to first search the cache,
thus avoiding unnecessary materialization.
 

<<<PDF_PAGE 855>>>
 
38.15. Consolidating and Hiding SQL Statements in One
Class
Hard-coding SQL statements into different RDB mapper classes is not a terrible sin, but it can be
improved upon. Suppose instead:
There is a single Pure Fabrication class (and it's a singleton) RDBOperations where all SQL
operations (SELECT, INSERT, ...) are consolidated.
The RDB mapper classes collaborate with it to obtain a DB record or record set (for example,
ResultSet).
Its interface looks something like this:
class RDBOperations
{
public ResultSet getProductDescriptionData( OID oid ) {...}
public ResultSet getSaleData( OID oid ) {...}
...
}
So that, for example, a mapper has code like this:
class ProductDescriptionRDBMapper extends AbstractPersistenceMapper
{
protected Object getObjectFromStorage( OID oid )
{
ResultSet rs =
   
RDBOperations.getInstance().getProductDescriptionData( oid );
ProductDescription ps = new ProductDescription();
ps.setPrice( rs.getDouble( "PRICE" ) );
ps.setOID( oid );
return ps;
}
The following benefits accrue from this Pure Fabrication:
Ease of maintenance and performance tuning by an expert. SQL optimization requires a SQL
aficionado, rather than an object programmer. With all the SQL embedded in this one class,
it is easy for the SQL expert to find and work on it.
<<<PDF_PAGE 856>>>
Encapsulation of the access method and details. For example, hard-coded SQL could be
replaced by a call to a stored procedure in the RDB in order to obtain the data. Or a more
sophisticated metadata-based approach to generating the SQL could be inserted, in which
SQL is dynamically generated from a metadata schema description read from an external
source.
As an architect, the interesting aspect of this design decision is that it is influenced by developer
skills. A trade-off between high cohesion and convenience for a specialist was made. Not all
design decisions are motivated by "pure" software engineering concerns such as coupling and
cohesion.
 

<<<PDF_PAGE 857>>>
 
38.16. Transactional States and the State Pattern
Transactional support issues can get complex, but to keep things simple for the presentto focus
on the GoF State patternassume the following:
Persistent objects can be inserted, deleted, or modified.
Operating on a persistent object (for example, modifying it) does not cause an immediate
database update; rather, an explicit commit operation must be performed.
In addition, the response to an operation depends on the transactional state of the object. As an
example, responses may be as shown in the statechart of Figure 38.12
.
Figure 38.12. Statechart for PersistentObject.
[View full size image]
For example, an "old dirty" object is one retrieved from the database and then modified. On a
commit operation, it should be updated to the databasein contrast to one in the "old clean" state,
which should do nothing (because it hasn't changed). Within the object-oriented PFW, when a
delete or save operation is performed, it does not immediately cause a database delete or save;
rather, the persistent object transitions to the appropriate state, awaiting a commit or rollback to
really do something.
As a UML comment, this is a good example of where a statechart is helpful in succinctly
communicating information that is otherwise awkward to express.
In this design, assume that we will make all persistent object classes extend a PersistentObject
class,[6]
 that provides common technical services for persistence.[7]
 For example, see Figure
38.13
.
[6] [Ambler00b
] is a good reference on a PersistentObject class and persistence layers, although the idea is older.
[7] Some issues with extending a PersistentObject class are discussed later. Whenever a domain object class extends a
<<<PDF_PAGE 858>>>
technical services class, it should be pause for reflection, as it mixes architectural concerns (persistence and application
logic).
Figure 38.13. Persistent objects.
Nowand this is the issue that will be resolved with the State patternnotice that commit and
rollback methods require similar structures of case logic, based on a transactional state code.
commit and rollback perform different actions in their cases, but they have similar logic
structures.
public void commit()
{
switch ( state )
{
case OLD_DIRTY:
    
// ...
    
break;
case OLD_CLEAN:
    
//...
   
break;
...
}
public void rollback()
{
switch ( state )
{
case OLD_DIRTY:
    
// ...
    
break;
case OLD_CLEAN:
    
//...
   
break;
...
}
An alternative to this repeating case logic structure is the GoF State pattern.
<<<PDF_PAGE 859>>>
State
Context/Problem
An object's behavior is dependent on its state, and its methods contain case logic
reflecting conditional state-dependent actions. Is there an alternative to conditional
logic?
Solution
Create state classes for each state, implementing a common interface. Delegate
state-dependent operations from the context object to its current state object. Ensure
the context object always points to a state object reflecting its current state.
Figure 38.14
 illustrates its application in the persistence subsystem.
Figure 38.14. Applying the State pattern.[10]
[View full size image]

<<<PDF_PAGE 860>>>
[10] The Deleted class is omitted due to space constraints in the diagram.
State-dependent methods in PersistentObject delegate their execution to an associated state
object. If the context object is referencing the OldDirtyState, then 1) the commit method will
cause a database update, and 2) the context object will be reassigned to reference the
OldCleanState. On the other hand, if the context object is referencing the OldCleanState, the
inherited do-nothing commit method executes and does nothing (as to be expected, since the
object is clean).
Observe in Figure 38.14
 that the state classes and their behavior correspond to the state chart of
Figure 38.12
. The State pattern is one mechanism to implement a state transition model in
software.[8]
 It causes an object to transition to different states in response to events.
[8] There are others, including hard-coded conditional logic, state machine interpreters, and code generators driven by state
tables.
As a performance comment, these state objects areironicallystateless (no attributes). Thus, there
does not need to be multiple instances of a classeach is a singleton. Thousands of persistent
objects can reference the same OldDirtyState instance, for example.
 

<<<PDF_PAGE 861>>>
 
38.17. Designing a Transaction with the Command
Pattern
The last section took a simplified view of transactions. This section extends the discussion, but
does not cover all transaction design issues. Informally, a transaction is a unit of worka set of
taskswhose tasks must all complete successfully, or none must be completed. That is, its
completion is atomic.
In terms of the persistence service, the tasks of a transaction include inserting, updating, and
deleting objects. One transaction could contain two inserts, one update, and three deletes, for
example. To represent this, a Transaction class is added [Ambler00b
].[9]
 As pointed out in
[Fowler01
], the order of database tasks within a transaction can influence its success (and
performance).
[9] This is called a UnitOfWork in [Fowler02
].
For example:
Suppose the database has a referential integrity constraint such that when a record is
updated in TableA that contains a foreign key to a record in TableB, the database requires
that the record in TableB already exists.
1.
Suppose a transaction contains an INSERT task to add the TableB record, and an UPDATE
task to update the TableA record. If the UPDATE executes before the INSERT, a referential
integrity error is raised.
2.
Ordering the database tasks can help. Some ordering issues are schema-specific, but a general
strategy is to first do inserts, then updates, and then deletes.
Mind that the order in which tasks are added to a transaction by an application may not reflect
their best execution order. The tasks need to be sorted just before their execution.
This leads to another GoF pattern: Command.
Command
Context/Problem
How to handle requests or tasks that need functions such as sorting (prioritizing),
queueing, delaying, logging, or undoing?
Solution
Make each task a class that implements a common interface.
<<<PDF_PAGE 862>>>
This is a simple pattern with many useful applications; actions become objects, and thus can be
sorted, logged, queued, and so forth. For example, in the PFW, Figure 38.15
 shows Command (or
task) classes for the database operations.
Figure 38.15. Commands for database operations.
[View full size image]
There is much more to completing a transaction solution, but the key idea of this section is to
represent each task or action in the transaction as an object with a polymorphic execute method;
this opens up a world of flexibility by treating the request as an object itself.
The quintessential example of Command is for GUI actions, such as cut and paste. For example,
the CutCommand's execute method does a cut, and its undo method reverses the cut. The
CutCommand will also retain the data necessary to perform the undo. All the GUI commands can
be kept in a history stack, so that they can be popped in turn, and each undone.
Another common use of Command is for server-side request handling. When a server object
receives a (remote) message, it creates a Command object for that request, and hands it off to a
CommandProcesser [BMRSS96
], which can queue, log, prioritize, and execute the commands.
 

<<<PDF_PAGE 863>>>
 
38.18. Lazy Materialization with a Virtual Proxy
It is sometimes desirable to defer the materialization of an object until it is absolutely required,
usually for performance reasons. For example, suppose that ProductDescription objects reference
a Manufacturer object, but only very rarely does it need to be materialized from the database.
Only rare scenarios cause a request for manufacturer information, such as manufacturer rebate
scenarios in which the company name and address are required.
The deferred materialization of "children" objects is known as lazy materialization. Lazy
materialization can be implemented using the Virtual Proxy GoF patternone of many variations of
Proxy.
A Virtual Proxy is a proxy for another object (the real subject) that materializes the real subject
when it is first referenced; therefore, it implements lazy materialization. It is a lightweight object
that stands for a "real" object that may or may not be materialized.
A concrete example of the Virtual Proxy pattern with ProductDescription and Manufacturer is
shown in Figure 38.16
. This design is based on the assumption that proxies know the OID of their
real subject, and when materialization is required, the OID is used to help identify and retrieve
the real subject.
Figure 38.16. Manufacturer Virtual Proxy.
[View full size image]

<<<PDF_PAGE 864>>>
Note that the ProductDescription has attribute visibility to an IManufacturer instance. The
Manufacturer for this ProductDescription may not yet be materialized in memory. When the
ProductDescription sends a getAddress message to the ManufacturerProxy (as though it were the
materialized manufacturer object), the proxy materializes the real Manufacturer, using the OID of
the Manufacturer to retrieve and materialize it.
Who Creates the Virtual Proxy?
Observe in Figure 38.16
 that the ManufacturerProxy collaborates with the PersistenceFacade in
order to materialize its real subject. But who creates the ManufacturerProxy? Answer: The
database mapper class for ProductDescription. The mapper class is responsible for deciding, when
it materializes an object, which of its "child" objects should also be eagerly materialized, and
which should be lazily materialized with a proxy.
Consider these alternative solutions: one uses eager materialization, the other lazy
materialization.
// EAGER MATERIALIZATION OF MANUFACTURER
class ProductDescriptionRDBMapper extends AbstractPersistenceMapper
{
protected Object getObjectFromStorage( OID oid )
{
ResultSet rs =
   
RDBOperations.getInstance().getProductDescriptionData( oid );
ProductDescription ps = new ProductDescription();
ps.setPrice( rs.getDouble( "PRICE" ) );
   
// here's the essence of it
String manufacturerForeignKey = rs.getString( "MANU_OID" );
OID manuOID = new OID( manufacturerForeignKey );
ps.setManufacturer( (IManufacturer)
   
PersistenceFacade.getInstance().get(manuOID,Manufacturer.class);
...
}
Here is the lazy materialization solution:
// LAZY MATERIALIZATION OF MANUFACTURER
class ProductDescriptionRDBMapper extends AbstractPersistenceMapper
{
protected Object getObjectFromStorage( OID oid )
{
ResultSet rs =
<<<PDF_PAGE 865>>>
   
RDBOperations.getInstance().getProductDescriptionData( oid );
ProductDescription ps = new ProductDescription();
ps.setPrice( rs.getDouble( "PRICE" ) );
   
// here's the essence of it
String manufacturerForeignKey = rs.getString( "MANU_OID" );
OID manuOID = new OID( manufacturerForeignKey );
ps.setManufacturer( new ManufacturerProxy( manuOID ) );
...
}
Implementation of a Virtual Proxy
The implementation of a Virtual Proxy varies by language. The details are outside the scope of
this chapter, but here is a synopsis:
Language
Virtual Proxy Implementation
C++
Define a templatized smart pointer class. No IManufacturer interface
definition is actually needed.
Java
The ManufacturerProxy class is implemented. The IManufacturer interface is
defined.
However, these are not normally manually coded. Rather, one creates a
code generator that analyzes the subject classes (e.g., Manufacturer) and
generates IManufacturer and ProxyManufacturer.
Another Java alternative is the Dynamic Proxy API.
Smalltalk
Define a Virtual Morphing Proxy (or Ghost Proxy), which uses
#doesNotUnderstand: and #become: to morph into the real subject. No
IManufacturer definition is needed.
 

<<<PDF_PAGE 866>>>
 
38.19. How to Represent Relationships in Tables
The code in the prior section relies on a MANU_OID foreign key in the PRODUCT_SPEC table to
link to a record in the MANUFACTURER table. This highlights the question: How are object
relationships represented in the relational model?
The answer is given in the Representing Object Relationships as Tables pattern {BW96
],
which proposes the following:
one-to-one associations
Place an OID foreign key in one or both tables representing the objects in relationship.
Or, create an associative table that records the OIDs of each object in relationship.
one-to-many associations, such as a collection
Create an associative table that records the OIDs of each object in relationship.
many-to-many associations
Create an associative table that records the OIDs of each object in relationship.
 

<<<PDF_PAGE 867>>>
 
38.20. PersistentObject Superclass and Separation of
Concerns
A common partial design solution to providing persistence for objects is to create an abstract
technical services superclass PersistentObject that all persistence objects inherit from (see Figure
38.17
). Such a class usually defines attributes for persistence, such as a unique OID, and
methods for saving to a database.
Figure 38.17. Problems with a PersistentObject superclass.
This is not wrong, but it suffers from the weakness of coupling the class to the PersistentObject
classdomain classes end up extending a technical services class.
This design does not illustrate a clear separation of concerns. Rather, technical services concerns
are mixed with domain layer business logic concerns by virtue of this extension.
On the other hand, "separation of concerns" is not an absolute virtue that must be followed at all
costs. As discussed in the Protected Variations introduction, designers need to pick their battles at
the truly likely points of expensive instability. If in a particular application making the classes
extend from PersistentObject leads to a neat and easy solution and does not create longer-term
design or maintenance problems, why not? The answer lies in understanding the evolution of the
requirements and design for the application. It is also influenced by the language: Those with
single inheritance (such as Java) have had their single precious superclass consumed.
 

<<<PDF_PAGE 868>>>
 
38.21. Unresolved Issues
This has been a very brief introduction to the problems and design solutions in a persistence
framework and service. Many important issues have been glossed over, including:
dematerializing objects
Briefly, the mappers must define putObjectToStorage methods. Dematerializing
composition hierarchies requires collaboration between multiple mappers and the
maintenance of associative tables (if an RDB is used).
materialization and dematerialization of collections
queries for groups of objects
thorough transaction handling
error handling when a database operation fails
multiuser access and locking strategies
securitycontrolling access to the database
 
