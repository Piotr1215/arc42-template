# Arc42 documentation structure with explanations

## Introduction and Goals

Describes the relevant requirements and the driving forces that software
architects and development team must consider. These include

-   underlying business goals, essential features and functional
    requirements for the system

-   quality goals for the architecture

-   relevant stakeholders and their expectations

### Requirements Overview

**Contents.**

Short description of the functional requirements, driving forces,
extract (or abstract) of requirements. Link to (hopefully existing)
requirements documents (with version number and information where to
find it).

**Motivation.**

From the point of view of the end users a system is created or modified
to improve support of a business activity and/or improve the quality.

**Form.**

Short textual description, probably in tabular use-case format. If
requirements documents exist this overview should refer to these
documents.

Keep these excerpts as short as possible. Balance readability of this
document with potential redundancy w.r.t to requirements documents.

### Quality Goals

**Contents.**

The top three (max five) quality goals for the architecture whose
fulfillment is of highest importance to the major stakeholders. We
really mean quality goals for the architecture. Don't confuse them with
project goals. They are not necessarily identical.

**Motivation.**

You should know the quality goals of your most important stakeholders,
since they will influence fundamental architectural decisions. Make sure
to be very concrete about these qualities, avoid buzzwords. If you as an
architect do not know how the quality of your work will be judged ...

**Form.**

A table with quality goals and concrete scenarios, ordered by priorities

### Stakeholders

Explicit overview of stakeholders of the system, i.e. all person, roles
or organizations that

-   should know the architecture

-   have to be convinced of the architecture

-   have to work with the architecture or with code

-   need the documentation of the architecture for their work

-   have to come up with decisions about the system or its development

**Motivation.**

You should know all parties involved in development of the system or
affected by the system. Otherwise, you may get nasty surprises later in
the development process. These stakeholders determine the extent and the
level of detail of your work and its results.

**Form.**

Table with role names, person names, and their expectations with respect
to the architecture and its documentation.

Role/Name|Contact|Expectations
-----|-----|-----
A|B|C

## Architecture Constraints

**Contents.**

Any requirement that constrains software architects in their freedom of
design and implementation decisions or decision about the development
process. These constraints sometimes go beyond individual systems and
are valid for whole organizations and companies.

**Motivation.**

Architects should know exactly where they are free in their design
decisions and where they must adhere to constraints. Constraints must
always be dealt with; they may be negotiable, though.

**Form.**

Simple tables of constraints with explanations. If needed you can
subdivide them into technical constraints, organizational and political
constraints and conventions (e.g. programming or versioning guidelines,
documentation or naming conventions)

## System Scope and Context

**Contents.**

System scope and context - as the name suggests - delimits your system
(i.e. your scope) from all its communication partners (neighboring
systems and users, i.e. the context of your system). It thereby
specifies the external interfaces.

If necessary, differentiate the business context (domain specific inputs
and outputs) from the technical context (channels, protocols, hardware).

**Motivation.**

The domain interfaces and technical interfaces to communication partners
are among your system's most critical aspects. Make sure that you
completely understand them.

**Form.**

Various options:

-   Context diagrams

-   Lists of communication partners and their interfaces.

### Business Context

**Contents.**

Specification of **all** communication partners (users, IT-systems, ...)
with explanations of domain specific inputs and outputs or interfaces.
Optionally you can add domain specific formats or communication
protocols.

**Motivation.**

All stakeholders should understand which data are exchanged with the
environment of the system.

**Form.**

All kinds of diagrams that show the system as a black box and specify
the domain interfaces to communication partners.

Alternatively (or additionally) you can use a table. The title of the
table is the name of your system, the three columns contain the name of
the communication partner, the inputs, and the outputs.

**\<Diagram or Table\>**

**\<optionally: Explanation of external domain interfaces\>**

### Technical Context

**Contents.**

Technical interfaces (channels and transmission media) linking your
system to its environment. In addition a mapping of domain specific
input/output to the channels, i.e. an explanation with I/O uses which
channel.

**Motivation.**

Many stakeholders make architectural decision based on the technical
interfaces between the system and its context. Especially infrastructure
or hardware designers decide these technical interfaces.

**Form.**

E.g. UML deployment diagram describing channels to neighboring systems,
together with a mapping table showing the relationships between channels
and input/output.

**\<Diagram or Table\>**

**\<optionally: Explanation of technical interfaces\>**

**\<Mapping Input/Output to Channels\>**

## Solution Strategy

**Contents.**

A short summary and explanation of the fundamental decisions and
solution strategies, that shape the system's architecture. These include

-   technology decisions

-   decisions about the top-level decomposition of the system, e.g.
    usage of an architectural pattern or design pattern

-   decisions on how to achieve key quality goals

-   relevant organizational decisions, e.g. selecting a development
    process or delegating certain tasks to third parties.

**Motivation.**

These decisions form the cornerstones for your architecture. They are
the basis for many other detailed decisions or implementation rules.

**Form.**

Keep the explanation of these key decisions short.

Motivate what you have decided and why you decided that way, based upon
your problem statement, the quality goals and key constraints. Refer to
details in the following sections.

## C4 Diagrams: Building Block View

**Content.**

The building block view shows the static decomposition of the system
into building blocks (modules, components, subsystems, classes,
interfaces, packages, libraries, frameworks, layers, partitions, tiers,
functions, macros, operations, datas structures, ...) as well as their
dependencies (relationships, associations, ...)

This view is mandatory for every architecture documentation. In analogy
to a house this is the *floor plan*.

**Motivation.**

Maintain an overview of your source code by making its structure
understandable through abstraction.

This allows you to communicate with your stakeholder on an abstract
level without disclosing implementation details.

**Form.**

The building block view is a hierarchical collection of progressivelly detailed PlantUML component diagrams.

**Level 1 - System Context (MANDATORY)**
A System Context diagram is a good starting point for diagramming and documenting a software system, allowing you to step back and see the big picture. Draw a diagram showing your system as a box in the centre, surrounded by its users and the other systems that it interacts with.

**Level 2 - Container Diagrams (MANDATORY)** Once you understand how your system fits in to the overall IT environment, a really useful next step is to zoom-in to the system boundary with a Container diagram. A "container" is something like a server-side web application, single-page application, desktop application, mobile app, database schema, file system, etc. Essentially, a container is a separately runnable/deployable unit (e.g. a separate process space) that executes code or stores data. 

**Level 3 - Component Diagrams (OPTIONAL)** Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

**Level 4 - Code Diagrams (OPTIONAL)** Those diagrams are optional and depend on the project. Finally, you can zoom in to each component to show how it is implemented as code; using UML class diagrams, entity relationship diagrams or similar.

### C4: System Context

Describe here the decomposition of the overall system.

Detail isn't important here as this is your zoomed out view showing a big picture of the system landscape. The focus should be on people (actors, roles, personas, etc) and software systems rather than technologies, protocols and other low-level details. It's the sort of diagram that you could show to non-technical people.

**Scope**: A single software system.2

**Primary elements**: The software system in scope.
Supporting elements: People (e.g. users, actors, roles, or personas) and software systems (external dependencies) that are directly connected to the software system in scope. Typically these other software systems sit outside the scope or boundary of your own software system, and you don?t have responsibility or ownership of them.

**Intended audience**: Everybody, both technical and non-technical people, inside and outside of the software development team.

[System context diagram documentation](https://c4model.com/#SystemContextDiagram)

### C4: Container Diagrams
 
The Container diagram shows the high-level shape of the software architecture and how responsibilities are distributed across it. It also shows the major technology choices and how the containers communicate with one another. It's a simple, high-level technology focussed diagram that is useful for software developers and support/operations staff alike.

**Scope**: A single software system.

**Primary elements**: Containers within the software system in scope.
Supporting elements: People and software systems directly connected to the containers.

**Intended audience**: Technical people inside and outside of the software development team; including software architects, developers and operations/support staff.

**Notes**: This diagram says nothing about deployment scenarios, clustering, replication, failover, etc.

[System container diagram documentation](https://c4model.com/#ContainerDiagram)

### C4: Component Diagrams

The Component diagram shows how a container is made up of a number of "components", what each of those components are, their responsibilities and the technology/implementation details.

**Scope**: A single container.

**Primary elements**: Components within the container in scope.
Supporting elements: Containers (within the software system in scope) plus people and software systems directly connected to the components.

**Intended audience**: Software architects and developers.

**Recommended for most teams**: No, only create component diagrams if you feel they add value, and consider automating their creation for long-lived documentation.

[System component diagram documentation](https://c4model.com/#ComponentDiagram)

### C4: Code Diagrams

This is an optional level of detail and is often available on-demand from tooling such as IDEs. Ideally this diagram would be automatically generated using tooling (e.g. an IDE or UML modelling tool), and you should consider showing only those attributes and methods that allow you to tell the story that you want to tell. This level of detail is not recommended for anything but the most important or complex components.

**Scope**: A single component.

**Primary elements**: Code elements (e.g. classes, interfaces, objects, functions, database tables, etc) within the component in scope.

**Intended audience**: Software architects and developers.

**Recommended for most teams**: No, for long-lived documentation, most IDEs can generate this level of detail on demand.

[System code diagram documentation](https://c4model.com/#CodeDiagram)

## Runtime View

**Contents.**

The runtime view describes concrete behavior and interactions of the
system's building blocks in form of scenarios from the following areas:

-   important use cases or features: how do building blocks execute
    them?

-   interactions at critical external interfaces: how do building blocks
    cooperate with users and neighboring systems?

-   operation and administration: launch, start-up, stop

-   error and exception scenarios

Remark: The main criterion for the choice of possible scenarios
(sequences, workflows) is their **architectural relevance**. It is
**not** important to describe a large number of scenarios. You should
rather document a representative selection.

**Motivation.**

You should understand how (instances of) building blocks of your system
perform their job and communicate at runtime. You will mainly capture
scenarios in your documentation to communicate your architecture to
stakeholders that are less willing or able to read and understand the
static models (building block view, deployment view).

**Form.**

There are many notations for describing scenarios, e.g.

-   numbered list of steps (in natural language)

-   activity diagrams or flow charts

-   sequence diagrams

-   BPMN or EPCs (event process chains)

-   state machines


### Runtime Scenario 1

* *\<insert runtime diagram or textual description of the scenario\>*

* *\<insert description of the notable aspects of the interactions
    between the building block instances depicted in this diagram.\>*

### Runtime Scenario 2

* *\<insert runtime diagram or textual description of the scenario\>*

* *\<insert description of the notable aspects of the interactions
    between the building block instances depicted in this diagram.\>*

### Runtime Scenario n

* *\<insert runtime diagram or textual description of the scenario\>*

* *\<insert description of the notable aspects of the interactions
    between the building block instances depicted in this diagram.\>*

## Deployment View

**Content.**

The deployment view describes:

1.  the technical infrastructure used to execute your system, with
    infrastructure elements like geographical locations, environments,
    computers, processors, channels and net topologies as well as other
    infrastructure elements and

2.  the mapping of (software) building blocks to that infrastructure
    elements.

Often systems are executed in different environments, e.g. development
environment, test environment, production environment. In such cases you
should document all relevant environments.

Especially document the deployment view when your software is executed
as distributed system with more then one computer, processor, server or
container or when you design and construct your own hardware processors
and chips.

From a software perspective it is sufficient to capture those elements
of the infrastructure that are needed to show the deployment of your
building blocks. Hardware architects can go beyond that and describe the
infrastructure to any level of detail they need to capture.

**Motivation.**

Software does not run without hardware. This underlying infrastructure
can and will influence your system and/or some cross-cutting concepts.
Therefore, you need to know the infrastructure.

Maybe the highest level deployment diagram is already contained in
section 3.2. as technical context with your own infrastructure as ONE
black box. In this section you will zoom into this black box using
additional deployment diagrams:

-   UML offers deployment diagrams to express that view. Use it,
    probably with nested diagrams, when your infrastructure is more
    complex.

-   When your (hardware) stakeholders prefer other kinds of diagrams
    rather than the deployment diagram, let them use any kind that is
    able to show nodes and channels of the infrastructure.

### Infrastructure Level 1

Describe (usually in a combination of diagrams, tables, and text):

-   the distribution of your system to multiple locations, environments,
    computers, processors, .. as well as the physical connections
    between them

-   important justification or motivation for this deployment structure

-   Quality and/or performance features of the infrastructure

-   the mapping of software artifacts to elements of the infrastructure

For multiple environments or alternative deployments please copy that
section of arc42 for all relevant environments.

***\<Overview Diagram\>***

Motivation

:   *\<explanation in text form\>*

Quality and/or Performance Features

:   *\<explanation in text form\>*

Mapping of Building Blocks to Infrastructure

:   *\<description of the mapping\>*

#### Infrastructure Level 2

##### *\<Infrastructure Element 1\>*

*\<diagram + explanation\>*

##### *\<Infrastructure Element 2\>*

*\<diagram + explanation\>*

...

##### *\<Infrastructure Element n\>*

*\<diagram + explanation\>*

## Cross-cutting Concerns {#section-concepts}

**Content.**

This section describes overall, principal regulations and solution ideas
that are relevant in multiple parts (= cross-cutting) of your system.
Such concepts are often related to multiple building blocks. They can
include many different topics, such as

-   domain models

-   architecture patterns or design patterns

-   rules for using specific technology

-   principal, often technical decisions of overall decisions

-   implementation rules

**Motivation.**

Concepts form the basis for *conceptual integrity* (consistency,
homogeneity) of the architecture. Thus, they are an important
contribution to achieve inner qualities of your system.

Some of these concepts cannot be assigned to individual building blocks
(e.g. security or safety). This is the place in the template that we
provided for a cohesive specification of such concepts.

**Form.**

The form can be varied:

-   concept papers with any kind of structure

-   cross-cutting model excerpts or scenarios using notations of the
    architecture views

-   sample implementations, especially for technical concepts

-   reference to typical usage of standard frameworks (e.g. using
    Hibernate for object/relational mapping)

**Structure.**

A potential (but not mandatory) structure for this section could be:

* Business or domain aspects: domain, entity or data models, the ubiquitous language from domain-driven design 
* Architecture and design patterns: What (recurring) patterns have been applied, and how?
* User Experience concepts (UX): How is the UI of the system implemented, what conventions or rules apply? How is usability achieved? User interface aspects, i18n, validation, accessibility
* Safety and security concepts: These qualities are among the most fundamental or important for some systems.
* Development: Build and build management, code generation, configuration, (automated) testing, migration
* Under the hood: persistence, distribution, transactions, session-handling, caching, threading, exception and error handling, security
* Operations concepts: deployment, installation, monitoring

Note: it might be difficult to assign individual concepts to one
specific topic on this list.

![Possible topics for crosscutting
concepts](media/08-Crosscutting-Concepts-Structure-EN.png)

### *\<Concept 1\>*

*\<explanation\>*

### *\<Concept 2\>*

*\<explanation\>*

...

### *\<Concept n\>*

*\<explanation\>*

## Design Decisions

**Contents.**

Important, expensive, large scale or risky architecture decisions
including rationals. With \"decisions\" we mean selecting one
alternative based on given criteria.

Please use your judgement to decide whether an architectural decision
should be documented here in this central section or whether you better
document it locally (e.g. within the white box template of one building
block).

Avoid redundancy. Refer to section 4, where you already captured the
most important decisions of your architecture.

**Motivation.**

Stakeholders of your system should be able to comprehend and retrace
your decisions.

**Form.**

Various options:

-   List or table, ordered by importance and consequences or:

-   more detailed in form of separate sections per decision

-   ADR (architecture decision record) for every important decision

## Quality Requirements

**Content.**

This section contains all quality requirements as quality tree with
scenarios. The most important ones have already been described in
section 1.2. (quality goals)

Here you can also capture quality requirements with lesser priority,
which will not create high risks when they are not fully achieved.

**Motivation.**

Since quality requirements will have a lot of influence on architectural
decisions you should know for every stakeholder what is really important
to them, concrete and measurable.


### Quality Tree

**Content.**

The quality tree (as defined in ATAM -- Architecture Tradeoff Analysis
Method) with quality/evaluation scenarios as leafs.

**Motivation.**

The tree structure with priorities provides an overview for a sometimes
large number of quality requirements.

**Form.**

The quality tree is a high-level overview of the quality goals and
requirements:

-   tree-like refinement of the term \"quality\". Use \"quality\" or
    \"usefulness\" as a root

-   a mind map with quality categories as main branches

In any case the tree should include links to the scenarios of the
following section.

### Quality Scenarios

**Contents.**

Concretization of (sometimes vague or implicit) quality requirements
using (quality) scenarios.

These scenarios describe what should happen when a stimulus arrives at
the system.

For architects, two kinds of scenarios are important:

-   Usage scenarios (also called application scenarios or use case
    scenarios) describe the system's runtime reaction to a certain
    stimulus. This also includes scenarios that describe the system's
    efficiency or performance. Example: The system reacts to a user's
    request within one second.

-   Change scenarios describe a modification of the system or of its
    immediate environment. Example: Additional functionality is
    implemented or requirements for a quality attribute change.

**Motivation.**

Scenarios make quality requirements concrete and allow to more easily
measure or decide whether they are fulfilled.

Especially when you want to assess your architecture using methods like
ATAM you need to describe your quality goals (from section 1.2) more
precisely down to a level of scenarios that can be discussed and
evaluated.

**Form.**

Tabular or free form text.

## Risks and Technical Debts

**Contents.**

A list of identified technical risks or technical debts, ordered by
priority

**Motivation.**

"Risk management is project management for grown-ups" (Tim Lister,
Atlantic Systems Guild.)

This should be your motto for systematic detection and evaluation of
risks and technical debts in the architecture, which will be needed by
management stakeholders (e.g. project managers, product owners) as part
of the overall risk analysis and measurement planning.

**Form.**

List of risks and/or technical debts, probably including suggested
measures to minimize, mitigate or avoid risks or reduce technical debts.

## Glossary

**Contents.**

The most important domain and technical terms that your stakeholders use
when discussing the system.

You can also see the glossary as source for translations if you work in
multi-language teams.

**Motivation.**

You should clearly define your terms, so that all stakeholders

-   have an identical understanding of these terms

-   do not use synonyms and homonyms

```{=html}
<!-- -->
```
-   A table with columns \<Term\> and \<Definition\>.

-   Potentially more columns in case you need translations.

Term|Definition
-----|-----|
Term1|Definition1
