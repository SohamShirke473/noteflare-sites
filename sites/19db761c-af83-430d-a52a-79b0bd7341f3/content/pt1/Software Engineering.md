---
title: Software Engineering
---

# Question Bank
## Q1. Software Requirements Specification (SRS)

An **SRS (Software Requirements Specification)** is a formal document that describes completely what the proposed software system should do (functionally and non-functionally), without describing how it will be implemented. It acts as a contract between the client and the development team, and forms the basis for design, coding, testing, and validation. Below, an SRS is developed for a generic **"Online Library Management System"** as an example.

### a. Product Perspective

The Online Library Management System (OLMS) is a **standalone, web-based application** that automates the manual process of book issuing, returning, and cataloguing in a library. It is not dependent on any other existing system but interfaces with:

- A **database server** for storing book records, member records, and transaction history.
- An **email/SMS gateway** for sending due-date reminders.
- An **authentication module** for admin/librarian/student login.

The system replaces the traditional register-based/manual method, is accessed through a browser, and can be integrated later with a college ERP system.

### b. Scope and Objective

**Scope:** The system will allow librarians to add/update/delete book records, issue and return books, track fines, and generate reports. Students/members will be able to search the catalogue, check availability, and view their issued-book history online.

**Objectives:**

1. To reduce manual paperwork and human error in library operations.
2. To provide real-time book availability information to users.
3. To automate fine calculation and overdue reminders.
4. To generate statistical reports (most issued books, defaulters list, etc.) for management decisions.

### c. Functional Requirements (minimum 3)

1. **Book Search:** The system shall allow a user to search for books by title, author, ISBN, or category and display availability status.
2. **Issue/Return Book:** The system shall allow the librarian to issue a book to a registered member and update the book's status to "Issued"; upon return, the system shall update status to "Available" and calculate fine (if any) based on the number of overdue days.
3. **Member Registration and Login:** The system shall allow new members to register with valid credentials and allow existing members/librarians to log in securely using a username and password.
4. **Report Generation:** The system shall generate reports such as the list of overdue books, total books issued in a month, and defaulter members.

### d. Non-Functional Requirements (minimum 3)

1. **Performance:** The system shall respond to a search query within 2 seconds under normal load (up to 500 concurrent users).
2. **Reliability/Availability:** The system shall be available 99% of the time excluding scheduled maintenance, and shall not lose transaction data even in case of power failure (via periodic backup).
3. **Security:** The system shall encrypt passwords and restrict access to admin functionalities using role-based authentication.
4. **Usability:** The system shall provide a simple, intuitive GUI usable by non-technical staff with minimal training.
5. **Maintainability:** The system's modules shall be loosely coupled so that new features (e.g., e-book support) can be added without major redesign.

---

## Q2. Spiral Process Model

The **Spiral Model**, proposed by **Barry Boehm in 1986**, is a **risk-driven** software process model that combines the iterative nature of prototyping with the controlled, systematic aspects of the waterfall model. It is often called a **"Meta-Model"** because it incorporates elements of many other models (waterfall, incremental, prototyping) depending on the risk pattern of the project.

Unlike linear models, the Spiral Model represents the development process as a **spiral with many loops**; the exact number of loops is not fixed and varies from project to project — it is decided dynamically by the project manager based on project risk.

### Diagram (conceptual representation)

```
                        Determine objectives,
                        alternatives & constraints
                              |
                    ---------------------
                   |    Quadrant 1       |
                   |   (Planning)        |
                   |                     |
   Quadrant 4 -----|--------(+)----------|----- Quadrant 2
 (Customer          |     SPIRAL          |   (Risk Analysis
  Evaluation)        |    (radius=cost)   |    & Prototyping)
                    |                     |
                   |    Quadrant 3       |
                   |  (Engineering /     |
                   |   Development)      |
                    ---------------------
```

Each **loop (cycle)** of the spiral represents one phase of the software process and passes through **four quadrants**:

1. **Quadrant 1 – Determine Objectives:** Identify objectives of the phase, alternative means of accomplishing them, and constraints.
2. **Quadrant 2 – Risk Analysis:** Evaluate alternatives; identify and resolve risks through analysis, simulation, or building prototypes.
3. **Quadrant 3 – Engineering/Development:** Develop and verify the next-level product (design, code, test).
4. **Quadrant 4 – Planning & Customer Evaluation:** Review results with the customer and plan the next spiral cycle.

The **radius of the spiral** at any point represents the **cumulative cost** of the project so far, and the **angular dimension**represents the **progress** made in the current phase.

### Applications / Suitability

The Spiral Model is most suitable for:

- **Large, complex, and high-risk projects** where requirements are not clearly understood at the start.
- Projects where **risk evaluation is critical**, e.g., defence, aerospace, banking/financial systems.
- Projects that require **incremental releases** and continuous refinement based on customer feedback.
- Projects using **new, unproven technology**.
- Long-term projects where requirements may evolve, since the model allows requirement changes at later stages.

It is not suitable for small, low-risk projects, or projects with a tight, fixed budget/timeline, because the risk-analysis overhead adds cost and time.

---

## Q3. Incremental Model

The **Incremental Model** divides the software product into smaller **builds/increments**, each of which is developed and delivered one after another, adding functionality progressively until the complete system is built. Each increment goes through its own phases of requirement analysis, design, coding, and testing (essentially a mini-waterfall for each build).

### Working

1. The overall requirements are divided into several **builds**.
2. Build 1 (containing core/high-priority functionality) is designed, developed, tested, and delivered.
3. Build 2 adds the next set of features on top of Build 1, and so on, until the final increment completes the whole system.
4. Each increment is a **usable product** in itself.

**Example:** A word-processor might be delivered as: Increment 1 – basic file editing and printing; Increment 2 – spell-check and formatting; Increment 3 – advanced page layout and macros.

### Merits (Advantages)

1. **Working software is generated early**, since core features are delivered in the first increment itself, giving quick value to the customer.
2. **Flexible to changing requirements** — changes can be incorporated in later increments without disturbing earlier ones.
3. **Lower initial cost** and easier to test and debug smaller increments than one large system.
4. **Risk of complete project failure is reduced**, since errors are found early in a smaller module.
5. Customer feedback after each increment helps refine subsequent increments.

### Demerits (Disadvantages)

1. Requires **good planning and design** at the start to properly divide the system into increments; poor division can cause problems in later integration.
2. **Total cost may be higher** than waterfall since each increment adds its own overhead of analysis/design/testing.
3. Problems in system architecture may not surface until later increments, requiring rework.
4. Needs well-defined **interfaces** between modules, since all increments must integrate seamlessly.
5. Not suitable for projects with tightly coupled requirements where modules cannot be separated.

---

## Q4. Applications of AI/ML Concepts in Software Engineering

Artificial Intelligence (AI) and Machine Learning (ML) are increasingly integrated into software engineering to automate, optimize, and improve various stages of the Software Development Life Cycle (SDLC).

1. **Automated Requirement Analysis:** NLP (Natural Language Processing) techniques are used to analyze requirement documents, detect ambiguities, inconsistencies, and even auto-generate use-case diagrams from natural-language requirements.
    
2. **Effort and Cost Estimation:** ML models (regression, neural networks) are trained on historical project data to predict effort, cost, and schedule more accurately than traditional models like COCOMO.
    
3. **Automated Code Generation and Completion:** AI-based tools (e.g., Copilot-like assistants) use large language models trained on code repositories to auto-suggest or generate code snippets, boosting developer productivity.
    
4. **Bug Prediction and Detection:** ML classifiers analyze code metrics (complexity, size, historical defect data) to predict which modules are most likely to contain bugs, allowing testers to prioritize testing effort.
    
5. **Automated Testing:** AI techniques generate test cases automatically, prioritize test cases based on risk, and detect flaky tests; ML models can also perform visual regression testing for UI changes.
    
6. **Software Maintenance:** AI helps in automatically classifying bug reports, assigning them to the right developer, and even suggesting patches based on similar historical bug fixes.
    
7. **Project Risk Management:** Predictive analytics using ML helps identify risk factors early by analyzing patterns from past failed/successful projects.
    
8. **Chatbots for Requirement Elicitation and Support:** Conversational AI assists in gathering requirements from stakeholders and provides automated customer support post-deployment.
    

Overall, AI/ML in software engineering shifts the discipline from purely manual, experience-based decision-making toward **data-driven, predictive, and automated processes**, improving quality and reducing time-to-market.

---

## Q5. RAD (Rapid Application Development) Model

The **RAD Model** was proposed by **IBM in the 1980s**. It is a type of **incremental process model** that emphasizes **very short development cycles** (typically 60–90 days) through the use of **component-based construction**, code reuse, and heavy customer involvement. RAD is best used when requirements are well understood and the project can be modularized so that different teams can work on different modules in parallel.

### Phases of RAD Model

1. **Business Modelling:** The flow of information among various business functions is analyzed and modelled — questions like what information drives the business process, who generates it, where it goes, and who processes it are answered.
    
2. **Data Modelling:** The information gathered in business modelling is refined into a set of data objects (entities) needed to support the business, and their attributes and relationships are identified.
    
3. **Process Modelling:** Data objects defined in data modelling are transformed to achieve the information flow necessary to implement a business function. Processing descriptions are created for adding, modifying, deleting, or retrieving a data object.
    
4. **Application Generation:** RAD relies heavily on **4th Generation Techniques (4GT)** and reusable components rather than writing conventional code, using automated tools to generate the software.
    
5. **Testing and Turnover:** Since RAD emphasizes reuse, many components are already tested; however, new components and interfaces must be thoroughly tested, reducing overall testing time.
    

### Diagram (conceptual)

```
Business Modelling -> Data Modelling -> Process Modelling
        -> Application Generation -> Testing & Turnover
   (each phase time-boxed and iterative, parallel teams work on modules)
```

### Advantages

- Reduced development time due to reusable components and parallel development.
- Customer is involved throughout, ensuring the final product matches expectations.
- Uses powerful CASE/4GT tools, improving productivity.

### Disadvantages

- Requires a team of highly skilled developers/designers.
- Not suitable for projects that cannot be modularized.
- Requires heavy customer commitment throughout the project.
- Risk is higher for technically challenging projects.

RAD is best suited for **information systems** with well-understood requirements, such as inventory management, billing systems, or business applications with a database-centric design.

---

## Q6. Short Notes

### a. SCRUM

**Scrum** is a lightweight **Agile framework** used to manage iterative and incremental software development. It divides work into fixed time-boxed iterations called **Sprints** (usually 2–4 weeks), at the end of which a potentially shippable product increment is delivered.

**Key roles:**

- **Product Owner:** Maintains and prioritizes the **Product Backlog** (list of all desired features).
- **Scrum Master:** Facilitates the process, removes obstacles/impediments, and ensures the team follows Scrum practices.
- **Development Team:** Self-organizing group that designs, builds, and tests the increment.

**Key artifacts:** Product Backlog, Sprint Backlog, and Increment.

**Key ceremonies/events:**

- **Sprint Planning** – deciding what will be done in the sprint.
- **Daily Scrum (Stand-up)** – a short (15-min) daily meeting to sync progress and blockers.
- **Sprint Review** – demonstrating the increment to stakeholders.
- **Sprint Retrospective** – reflecting on what went well/poorly to improve the next sprint.

Scrum promotes transparency, inspection, and adaptation, making it highly suitable for projects with rapidly changing requirements.

### b. CMM (Capability Maturity Model)

The **Capability Maturity Model (CMM)**, developed by the **Software Engineering Institute (SEI)** at Carnegie Mellon University, is a framework used to assess and improve an organization's software development process maturity. It provides a benchmark for judging how well an organization's processes compare to best practices.

CMM defines **five maturity levels**:

1. **Initial:** Processes are ad hoc, chaotic, and largely dependent on individual effort; success is unpredictable.
2. **Repeatable:** Basic project management processes are established to track cost, schedule, and functionality; past successes can be repeated on similar projects.
3. **Defined:** Processes are documented, standardized, and integrated into a organization-wide standard software process.
4. **Managed:** Detailed process and product quality metrics are collected; both process and products are quantitatively understood and controlled.
5. **Optimizing:** Continuous process improvement is enabled through quantitative feedback and by piloting innovative ideas and technologies.

CMM helps organizations move from immature, chaotic processes toward mature, disciplined software processes, thereby improving quality, predictability, and productivity.

---

## Q7. Agile Process Model

The **Agile Model** is a group of software development methodologies based on **iterative and incremental development**, where requirements and solutions evolve through collaboration between self-organizing, cross-functional teams. It was formalized through the **Agile Manifesto (2001)**, which values:

- Individuals and interactions **over** processes and tools.
- Working software **over** comprehensive documentation.
- Customer collaboration **over** contract negotiation.
- Responding to change **over** following a fixed plan.

### Working

1. The project is broken into small iterations/sprints, each lasting 1–4 weeks.
2. In each iteration, cross-functional teams work on planning, requirement analysis, design, coding, unit testing, and acceptance testing.
3. At the end of each iteration, a working product increment is delivered to the customer for feedback.
4. Feedback is incorporated into the next iteration, allowing continuous improvement.

### Characteristics

- Emphasizes **customer satisfaction** through early and continuous delivery.
- Welcomes **changing requirements**, even late in development.
- Promotes **frequent delivery** of working software (weeks rather than months).
- Encourages close, daily cooperation between business people and developers.
- Uses face-to-face conversation as the most efficient means of communication.
- Sustainable development pace and technical excellence are prioritized.

### Advantages

- Highly adaptable to changing requirements.
- Frequent delivery keeps stakeholders engaged and reduces risk of building the wrong product.
- Continuous testing improves quality.

### Disadvantages

- Difficult to estimate cost/time accurately at the start of the project.
- Requires highly skilled, experienced team members.
- Documentation is often minimal, making maintenance harder for new team members later.

Popular Agile methodologies include **Scrum, Extreme Programming (XP), Kanban,** and **Feature-Driven Development (FDD)**.

---

## Q8. DFD (Data Flow Diagram) – Level 0 and Level 1

A **Data Flow Diagram (DFD)** graphically represents the flow of data through a system — showing how data enters, moves through, and leaves the system, without describing control logic. Example system: **"Online Food Ordering System."**

### DFD Level 0 (Context Diagram)

The Level 0 DFD shows the entire system as a **single process**, with external entities interacting with it.

```
   [Customer] --(Order Details)--> ( 0. Online Food     ) --(Order Confirmation)--> [Customer]
                                    ( Ordering System   )
   [Restaurant] <--(Order Info)--- (                    ) --(Delivery Status)--> [Delivery Agent]
```

External Entities: Customer, Restaurant, Delivery Agent Process: 0 — Online Food Ordering System (treated as a black box)

### DFD Level 1 (Decomposition of Process 0)

Level 1 breaks the single process into its major sub-processes and shows internal data stores.

```
[Customer] --Order--> (1. Take Order) --Order Data--> [D1: Order DB]
(1. Take Order) --Order Details--> (2. Process Payment) --Payment Info--> [D2: Payment DB]
(2. Process Payment) --Confirmed Order--> (3. Assign Restaurant) --Order--> [Restaurant]
(3. Assign Restaurant) --Ready Signal--> (4. Assign Delivery Agent) --Delivery Task--> [Delivery Agent]
(4. Assign Delivery Agent) --Status Update--> [Customer]
```

Sub-processes: 1. Take Order, 2. Process Payment, 3. Assign Restaurant, 4. Assign Delivery Agent Data stores: D1 – Order Database, D2 – Payment Database

This decomposition can be further expanded into Level 2 DFDs for each sub-process if more detail is required.

---

## Q9. Requirement Engineering Tasks

**Requirement Engineering (RE)** is the process of gathering, analyzing, documenting, and managing the requirements of a software system. It consists of the following major tasks:

1. **Inception (Requirement Gathering):** The initial task where the project scope and nature of the problem are understood by talking to stakeholders; basic questions about the business context, goals, and benefits are asked.
    
2. **Elicitation:** The process of actively collecting requirements from stakeholders using techniques like interviews, questionnaires, brainstorming, use-case analysis, and workshops (e.g., JAD – Joint Application Development).
    
3. **Elaboration:** The gathered requirements are refined and expanded into more technical detail; analysis models (e.g., use-case diagrams, ER diagrams) are created to define data, functional, and behavioral requirements clearly.
    
4. **Negotiation:** Since different stakeholders may have conflicting requirements (e.g., cost vs. features), this task resolves conflicts by prioritizing requirements based on feasibility, risk, and available resources.
    
5. **Specification:** All finalized requirements are documented formally in the **SRS (Software Requirement Specification)** document, which becomes the reference for design and testing.
    
6. **Validation:** The SRS is reviewed and checked for correctness, completeness, consistency, and feasibility with stakeholders to ensure it truly reflects their needs before development begins.
    
7. **Requirement Management:** Since requirements evolve over time, this ongoing task tracks changes, maintains traceability (linking requirements to design/code/test cases), and manages version control of the requirement document throughout the project lifecycle.
    

These tasks are not strictly sequential — they often overlap and iterate, especially in agile projects where requirements evolve continuously.

---

## Q10. Extreme Programming (XP)

**Extreme Programming (XP)** is one of the most popular **Agile software development methodologies**, proposed by **Kent Beck**. It is designed for small-to-medium teams working with vague or rapidly changing requirements, focusing on improving software quality and responsiveness to customer needs through frequent releases in short development cycles.

### Core Values of XP

1. **Communication** – close, continuous interaction between developers and customers.
2. **Simplicity** – design the simplest solution that works, avoiding unnecessary complexity.
3. **Feedback** – constant feedback from tests, customers, and team members.
4. **Courage** – willingness to make changes and refactor code when needed.
5. **Respect** – mutual respect among all team members.

### Key Practices of XP

1. **Pair Programming:** Two developers work together at one workstation — one writes code while the other reviews it in real time, improving code quality.
2. **Test-Driven Development (TDD):** Test cases are written _before_ the code; code is written only to pass these tests.
3. **Continuous Integration:** Code is integrated and tested multiple times a day to catch integration errors early.
4. **Refactoring:** Code is continuously restructured to improve design without changing its external behaviour.
5. **Small Releases:** The system is delivered to the customer frequently in small, functional increments.
6. **Collective Code Ownership:** Any developer can modify any part of the code, encouraging shared responsibility.
7. **On-Site Customer:** A customer representative is available at all times to clarify requirements and provide feedback.
8. **Coding Standards:** The team follows a consistent coding style throughout the project.

### Advantages

- High-quality code due to TDD and pair programming.
- Rapid response to changing customer requirements.
- Early detection of defects through continuous testing/integration.

### Disadvantages

- Requires high customer involvement, which is not always feasible.
- Can be difficult to scale to very large teams/projects.
- Documentation is often minimal.

XP is best suited for projects with unclear or rapidly evolving requirements and small, co-located teams.

---

## Q11. Requirement Modelling

**Requirement Modelling** is the process of creating an abstract representation (model) of the software requirements gathered during requirement elicitation, so that they can be analyzed, communicated, and verified before actual design and coding begin. The model bridges the gap between the informal, natural-language description of requirements given by stakeholders and the formal specifications needed by designers.

### Purpose

- To clearly represent the **functions**, **data**, and **behaviour** the system must exhibit.
- To help identify errors, omissions, and ambiguities early in the process.
- To provide a common communication medium between customers, analysts, and developers.

### Types of Requirement Models

1. **Scenario-Based Models:** Represent the system from the user's point of view using **Use-Case Diagrams** and **Use-Case descriptions**, showing actors and their interactions with the system.
    
2. **Data Models (Class-Based Models):** Represent the data objects that the system manipulates, along with their attributes and relationships, using **Class Diagrams** and **ER (Entity-Relationship) Diagrams**.
    
3. **Flow-Oriented Models:** Represent how data moves through the system, using **Data Flow Diagrams (DFDs)**.
    
4. **Behavioural Models:** Represent how the system behaves as a consequence of external events, using **State Transition Diagrams (STDs)**.
    

Requirement Modelling is typically supported by tools like UML (Unified Modeling Language), which provides standard notations for use-case, class, sequence, and state diagrams, ensuring the requirements model is unambiguous and can be traced through design and implementation.

---

## Q12. Scenario-Based Model

The **Scenario-Based Model** is a requirement modelling technique that represents the system's functional requirements from the perspective of the **end user**, describing how different actors (users or external systems) interact with the system to achieve specific goals.

### Key Elements

1. **Actor:** Any user or external system that interacts with the software (e.g., Customer, Admin, Payment Gateway).
2. **Use Case:** A specific sequence of actions the system performs that yields an observable result of value to an actor (e.g., "Place Order," "Cancel Booking").
3. **Scenario:** A specific instance/path of a use case, describing a particular way in which the user interacts with the system, including normal flow and exceptional/alternative flows.

### Tools Used

- **Use-Case Diagrams:** Graphically show actors, use cases, and their relationships (association, include, extend, generalization).
- **Use-Case Templates/Descriptions:** Textual descriptions specifying the actor, preconditions, main flow of events, alternative flows, and postconditions for each use case.

### Example

For an **ATM system**, a scenario for the use case "Withdraw Cash" might be:

1. Customer inserts card and enters PIN.
2. System validates PIN.
3. Customer selects "Withdraw Cash" and enters amount.
4. System checks account balance.
5. System dispenses cash and prints receipt. _(Alternative flow: if PIN is invalid, the system displays an error and asks the customer to re-enter it.)_

### Importance

- Helps requirement analysts and customers **visualize** system functionality early, reducing misunderstandings.
- Provides the foundation for designing **test cases**, since each scenario/flow can be mapped directly to a test case.
- Forms the basis for further modelling activities such as class diagrams and sequence diagrams during design.

Scenario-based modelling is widely used in Object-Oriented Analysis and Design (OOAD) as part of the UML methodology.