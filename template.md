**Software Requirements Specification**

**For BizRay -- "X-Ray for Business"**

Prepared by : Artur Volkov

Group: 2

Date created: 15. October 2025

**1. Introduction**

**1.1 Document Purpose**

This document defines the requirements for the BizRay web application.

It specifies what the system will do and how it will behave.

It is intended for:

- Project supervisors (such as teachers) and tutors reviewing our work.

- End users (e.g students) who will use the system.

**1.2 Product Scope**

BizRay ("Business X-Ray") is a web application that collects and
analyzes open-sourced company register data from EU and Austrian sources
(e.g Firmenbuch).

Its main goal is to give users insight into company information,
financial situation, and its risk indicators.

The system will allow searching for companies, viewing their details and
connections, and generating basic risk evaluation.

Its main purpose is to project business transparency and helps users
make safer decisions when selecting business partners.

**1.3 Definitions, Acronyms and Abbreviations**

| **Term** | **Definition**                     |
|----------|------------------------------------|
| API      | Application Programming Interface  |
| EU HVD   | European Union High Value Datasets |
| GUI      | Graphical User Interface           |
| KPI      | Key Performance Indicator          |
| REST     | Representational State Transfer    |
| GDPR     | General Data Protection Regulation |

**1.4 References**

- Practical Project 01a Slides

- <https://justizonline.gv.at/jop/web/iwg> - API of "Austrian
  Firmenbuch"

- Example usage:
  [[https://openfirmenbuch.at]{.underline}](https://openfirmenbuch.at)

- Template used as refference: https://github.com/jam01/SRS-Template

**1.5 Document Overview**

Part 2 gives a general overview of BizRay and its users.

Part 3 defines all system requirements.

Part 4 explains how the system will be verified.

Part 5 lists references.

**2. Product Overview**

**2.1 Product Overview**

BizRay is built as a web application. It will access public company
register APIs and datasets, process that data, and present analytics.

**2.2 Product Functionality**

- Search companies by name or ID

- Display company profile and key details

- Calculate financial indicators

- Compute network-based risk metrics

- Generate downloadable PDF reports

- Manage users with different access roles

**2.3 Product Restrictions**

- Access limited by open data API rate limits.

- Must follow GDPR for user accounts.

- Web app must run in commonly-used browsers (such as Chrome, Firefox,
  Edge).

**2.4 User Characteristics**

| **User Type** | **Description**                        | **Technical Skill** |
|---------------|----------------------------------------|---------------------|
| Analyst       | Uses the app to estimate company risks | Intermediate        |
| Business User | Looks up partner company information   | Basic               |
| Administrator | Maintains system, manages users        | Advanced            |

**2.5 Dependencies**

- API and bulk data from data.gv.at and justizonline.gv.at remain
  accessible.

- Users have an internet connection.

**2.6 Apportioning of Requirements**

Future versions may include:

- AI-based company bankruptcy prediction

- Interactive charts with various timestampts

- Company comparison dashboard

**3. Requirements**

**3.1 External Interfaces**

**3.1.1 User Interfaces**

The web interface will include:

- A search bar for company lookup

- A dashboard showing company details

- Graphical visualization of company connections

- A "Risk Indicators" tab with metrics

- A "Generate Report" button (converts into PDF)

- Login and Admin panel pages

Usability requirements:

- Clean, simple layout

- Mobile responsive design

- Reliable and consistent navigation

- Color scheme fitting the UI

**3.1.2 Hardware Interfaces**

BizRay runs entirely in a browser. Nothing needs to be downloaded on the
computer, no specific hardware beyond a standard computer or smartphone
is required.

**3.2 Functional**

| **№** | **Requirement Description**                                       | **Priority** |
|-------|-------------------------------------------------------------------|--------------|
| 1\.   | System shall allow searching for companies by name or ID.         | High         |
| 2\.   | System shall display company details (name, ID, address, status). | High         |
| 3\.   | System shall display company relationships as a network graph.    | High         |
| 4\.   | System shall calculate financial ratios.                          | Medium       |
| 5\.   | System shall calculate network-based risk indicators.             | Medium       |
| 6\.   | System shall generate downloadable PDF reports.                   | Medium       |
| 7\.   | System shall provide role-based login (Admin, Analyst).           | High         |
| 8\.   | System shall synchronize open data from the Firmenbuch API.       | Medium       |
| 9\.   | System shall allow admins to manage user accounts.                | Medium       |

**3.3 Quality of Service**

**3.3.1 Performance**

- Loading of **Dashboard** should not take longer than a **couple of
  seconds**.

- API response time should not exceed for typical queries and requests.

**3.3.2 Security**

- User login with password hashing.

- HTTPS for all communications.

**3.3.3 Reliability**

- Data backups every **24 hours.**

- API error handling for network.

**3.3.4 Availability**

- System uptime target: **≥ 99%**.

- Maintenance downtime scheduled in advance.

**3.4 Compliance**

- Must comply with data licences and terms of services.

- Reports must display source attribution (e.g. "Data: Austrian
  Firmenbuch").

- Logging system of users actions on the website(e.g. search of a
  certain company).

**3.5 Design and Implementation**

**3.5.1 Installation**

No installation needed for users; accessible via browser.

Developers will provide the instructions as **requirements.txt.**

**3.5.2 Distribution**

BizRay will be hosted online in order for a regular user to gain the
access to it via browser and find it using any search engine.

Database access limited to authorized admins.

**3.5.3 Maintainability**

Code must be documented and committed in GitHub.

**3.5.4 Re-usability**

The data analysis and visualization modules should be reusable for
similar APIs. It can always be changed to a different one.

**3.5.5 Portability**

The system should run on Windows, macOS, or Linux via a web browser.

**3.5.6 Cost**

No external license costs. Development done with open-source tools.

**3.5.7 Deadline**

Project duration: **3 months (October--December 2025)**.

First prototype delivery after 6 weeks.

**4. Verification**

Verification will ensure that all requirements are implemented and
tested.

- Each functional requirement will have a specific test case.

- The system will be tested with real sample company data.

- Usability will be evaluated through gathered feedback.

- Performance tests will measure response times and uptime.

Example mappings:

| **Requirement** | **Verification Method**                           |
|-----------------|---------------------------------------------------|
| Step 1-3        | Manual functional testing                         |
| Step 4-5        | Unit tests for financial and network calculations |
| Step 6          | Export function tested with sample report         |
| Step 7-9        | Login and role tests with dummy accounts          |

**5. Extra Information**

- **Material A:** Company network visualization mockup

- **Material B:** Risk indicator formula examples

- **Material C:** References to public datasets
