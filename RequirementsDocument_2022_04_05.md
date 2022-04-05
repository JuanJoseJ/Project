# Requirements Document

Date: 2 April 2022

Version: 0.0

| Version number | Change |
| -------------- | :----- |
|                |        |

# Homeworks

| Name | Work |
| ---- | :--- |
|      |      |

# Contents

- [Informal description](#informal-description)
- [Stakeholders](#stakeholders)
- [Context Diagram and interfaces](#context-diagram-and-interfaces)
  - [Context Diagram](#context-diagram)
  - [Interfaces](#interfaces)
- [Stories and personas](#stories-and-personas)
- [Functional and non functional requirements](#functional-and-non-functional-requirements)
  - [Functional Requirements](#functional-requirements)
  - [Non functional requirements](#non-functional-requirements)
- [Use case diagram and use cases](#use-case-diagram-and-use-cases)
  - [Use case diagram](#use-case-diagram)
  - [Use cases](#use-cases) + [Relevant scenarios](#relevant-scenarios)
- [Glossary](#glossary)
- [System design](#system-design)
- [Deployment diagram](#deployment-diagram)

# Informal description

Medium companies and retailers need a simple application to manage the relationship with suppliers and the inventory of physical items stocked in a physical warehouse.
The warehouse is supervised by a manager, who supervises the availability of items. When a certain item is in short supply, the manager issues an order to a supplier. In general the same item can be purchased by many suppliers. The warehouse keeps a list of possible suppliers per item.

After some time the items ordered to a supplier are received. The items must be quality checked and stored in specific positions in the warehouse. The quality check is performed by specific roles (quality office), who apply specific tests for item (different items are tested differently). Possibly the tests are not made at all, or made randomly on some of the items received. If an item does not pass a quality test it may be rejected and sent back to the supplier.

Storage of items in the warehouse must take into account the availability of physical space in the warehouse. Further the position of items must be traced to guide later recollection of them.

The warehouse is part of a company. Other organizational units (OU) of the company may ask for items in the warehouse. This is implemented via internal orders, received by the warehouse. Upon reception of an internal order the warehouse must collect the requested item(s), prepare them and deliver them to a pick up area. When the item is collected by the other OU the internal order is completed.

EZWH (EaSy WareHouse) is a software application to support the management of a warehouse.

# Stakeholders

| Stakeholder name  | Description |
| ----------------- | :---------: |
| Company investors |             |
| Company CEO       |             |
| Company workers   |             |
| Suppliers         |             |
| Warehouse manager |             |
| Warehouse workers |             |
| Quality office    |             |
| Costumers         |             |
| Delivery drivers  |             |
| Company owner     |             |

# Context Diagram and interfaces

## Context Diagram

<!-- \<Define here Context diagram using UML use case diagram> -->

![alt text](context_diagram.jpg "Context Diagram")

<!-- \<actors are a subset of stakeholders> -->

## Actors

- Customers <!-- Capire se si deve mettere anche questo o solo OU  -->
- Organizational Units
- Warehouse manager
- Warehouse workers
- Suppliers
- Quality office workers
- IT office

## Interfaces

<!-- \<describe here each interface in the context diagram -->

<!-- \<GUIs will be described graphically in a separate document> -->

| Actor                  |                 Logical Interface                 | Physical Interface |
| ---------------------- | :-----------------------------------------------: | -----------------: |
| Customers              |                 GUI - Make order                  |             Screen |
| Organizational Units   |                 GUI - Make order                  |             Screen |
| Warehouse manager      |    GUI - Crud order, manage items, manage area    |             Screen |
| Warehouse workers      |          GUI - Manage items, manage area          |             Screen |
| Suppliers              | GUI - Recive order, fulfill order, manage returns |             Screen |
| Quality office workers |        GUI - Review items, manage returns         |             Screen |

# Stories and personas

\<A Persona is a realistic impersonation of an actor. Define here a few personas and describe in plain text how a persona interacts with the system>

\<Persona is-an-instance-of actor>

\<stories will be formalized later as scenarios in use cases>

# Functional and non functional requirements

## Functional Requirements

\<In the form DO SOMETHING, or VERB NOUN, describe high level capabilities of the system>

\<they match to high level use cases>

| ID      |     Description      |
| ------- | :------------------: | ----------------------------------- |
| FR1     |   Order Managment    |
| FR1.1   |     Create Order     |
| FR1.2   |      Read Order      |
| FR1.3   |     Update Order     |
| FR1.4   |     Delete Order     |
| FR1.5   |       Shipping       | <!-- Vedere se si deve togliere --> |
| FR1.6   |     Reply Order      |
| FR1.6.1 |    Confirm Order     |
| FR1.6.2 |     Reject Order     |
| FR2     |    Quality Check     |
| FR2.1   |     Aprove order     |
| FR2.2   |     Return order     |
| FR2.3   |    Register test     |
| FR3     | Inventory Management |
| FR3.1   |     Store items      |
| FR3.2   |   Update Position    |
| FR3.3   |      Send items      |
| FR4     |  Account managment   |
| FR4.1   |    Create account    |
| FR4.2   |    Update account    |
| FR4.3   |    Delete account    |

## Non Functional Requirements

<!-- \<Describe constraints on functional requirements> -->

| ID   | Type (efficiency, reliability, ..) |                     Description                     |   Refers to |
| ---- | :--------------------------------: | :-------------------------------------------------: | ----------: | -------------------- |
| NFR1 |            Reliability             |          Must have space in the warehouse           |         FR3 | <!-- Da chiedere --> |
| NFR2 |            Portability             |      Must work on Windows, Linux, Mac, Android      |             |
| NFR3 |              Security              |          Protection from malitious access           | Fr1,FR2,FR3 |
| NFR4 |             Usability              |      Effort needed to learn using the product       |             |
| NFR5 |               Space                | Minimum software memory available to register items |             |

# Use case diagram and use cases

## Use case diagram

\<define here UML Use case diagram UCD summarizing all use cases, and their relationships>

![alt text](DiagrammadeiCasidUso.png "Use Case Diagram")

\<next describe here each use case in the UCD>

### Use case 1 Create Order , UC1

| Actors Involved  |                  Customers, Manager                   |
| ---------------- | :---------------------------------------------------: |
| Precondition     |         Device must be connected on internet          |
| Post condition   |                 The order is received                 |
| Nominal Scenario | order data is inserted correctly and sent by Manager  |
| Variants         | order data is inserted correctly and sent by Customer |
| Exception 1      |     order data is inserted incorrectly by Manager     |
| Exception 2      |    order data is inserted incorrectly by Customer     |

##### Scenario 1.1 Nominal

\<describe here scenarios instances of UC1>

\<a scenario is a sequence of steps that corresponds to a particular execution of one use case>

\<a scenario is a more formal description of a story>

\<only relevant scenarios should be described>

| Scenario 1.1   |                                                                                              |
| -------------- | :------------------------------------------------------------------------------------------: |
| Precondition   | Device must be connected on internet, order data is inserted correctly, user type is manager |
| Post condition |                              the order is received by supplier                               |
| Step#          |                                         Description                                          |
| 1              |                                      user insert items                                       |
| 2              |                                  user insert items quantity                                  |
| 3              |                                     user insert supplier                                     |
| 4              |                                    user press send button                                    |
| 5              |                               application verify inserted data                               |
| 6              |                                    application send order                                    |
| 7              |                                 application show order recap                                 |

##### Scenario 1.2 Variant

| Scenario 1.2   |                                                                                               |
| -------------- | :-------------------------------------------------------------------------------------------: |
| Precondition   | Device must be connected on internet, order data is inserted correctly, user type is customer |
| Post condition |                         the order is received by Warehouse's Manager                          |
| Step#          |                                          Description                                          |
| 1              |                                       user insert items                                       |
| 2              |                                  user insert items quantity                                   |
| 3              |                                 user insert delivery address                                  |
| 4              |                                    user press send button                                     |
| 5              |                               application verify inserted data                                |
| 6              |                                    application send order                                     |
| 7              |                                 application show order recap                                  |

##### Scenario 1.3 Exception 1

| Scenario 1.3   |                                                                                                |
| -------------- | :--------------------------------------------------------------------------------------------: |
| Precondition   | Device must be connected on internet, order data is inserted incorrectly, user type is manager |
| Post condition |                                     the order in not sent                                      |
| Step#          |                                          Description                                           |
| 1              |                                       user insert items                                        |
| 2              |                                   user insert items quantity                                   |
| 3              |                                      user insert supplier                                      |
| 4              |                                     user press send button                                     |
| 5              |                                application verify inserted data                                |
| 6              |                                 application show error message                                 |

##### Scenario 1.4 Exception 2

| Scenario 1.4   |                                                                                                 |
| -------------- | :---------------------------------------------------------------------------------------------: |
| Precondition   | Device must be connected on internet, order data is inserted incorrectly, user type is customer |
| Post condition |                                      the order in not sent                                      |
| Step#          |                                           Description                                           |
| 1              |                                        user insert items                                        |
| 2              |                                   user insert items quantity                                    |
| 3              |                                  user insert delivery address                                   |
| 4              |                                     user press send button                                      |
| 5              |                                application verify inserted data                                 |
| 6              |                                 application show error message                                  |

### Use case 2, UC2

..

### Use case x, UCx

..

# Glossary

\<use UML class diagram to define important terms, or concepts in the domain of the system, and their relationships>

\<concepts are used consistently all over the document, ex in use cases, requirements etc>

# System Design

\<describe here system design>

\<must be consistent with Context diagram>

# Deployment Diagram

\<describe here deployment diagram >
