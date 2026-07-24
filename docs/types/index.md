# Types of Architechs

| Attribute | Enterprise Architect (EA) | Solutions Architect (SA) | Software Architect (SwA) |
| :--- | :--- | :--- | :--- |
| **Primary Scope** | Whole organization & business ecosystem | A specific business project or application | A single software component or codebase |
| **Core Focus** | Business-IT alignment and long-term strategy | Problem-solving and integrating systems | Code quality, design patterns, and framework choice |
| **Target Audience** | C-Suite, Executives, Stakeholders | Product Managers, Project Managers, Engineering Leads | Software Developers, DevOps Engineers |
| **Time Horizon** | 3 to 5+ years into the future | Current project lifecycle (months to 1-2 years) | Immediate sprint delivery and ongoing maintenance |
| **Required Skills** | Business strategy, governance, financial modeling | Cloud platforms, system integration, APIs | Coding expertise, design patterns, data modeling |

1. `Enterprise Architect` `(The Global Planner)Action`: Decides how the ride-hailing app fits into the company's broader portfolio (e.g., integrating it with existing food delivery and freight logistics systems).Key Choice: Establishes a mandate that all company tech must use cloud-native infrastructure to reduce global server costs by 15% over 3 years.

<br/>

2. `Solutions Architect` `(The Bridge)Action`: Designs the specific system that handles real-time ride requests and connects drivers with riders.Key Choice: Decides to use AWS for cloud hosting, Stripe for payment processing, and Google Maps API for location tracking, ensuring all three parts pass data safely to one another.

<br/>

3. `Software Architect` `(The Code Builder)Action`: Dictates how the actual matching engine or payment module inside the app is written and structured.Key Choice: Decides that the matching engine must be written in Go (Golang) for fast concurrency, uses a microservices pattern, and establishes the database schema for active rides.
