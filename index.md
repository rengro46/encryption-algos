
---

## Validation of encryption algos in use:

<img src="./algos.jpg?raw=true" width=450 height=300>

---

Checking the current set of communication encryption algorithms in use (Data in Transit) as well as the encryption status of disk volumes (Data at Rest). Finally to compare compliance of the encryption algos in use to the published company standard and generating exception based reporting in PowerBI dashboard

---

### Project Purpose and Justification

The purpose of this project is to assess the encryption algorithms currently in use within [Your Organization’s Name] to ensure they meet the organization's security standards and industry best practices. This assessment is critical to maintaining data confidentiality, integrity, and compliance with regulatory requirements. Specifically, all encryption mechanisms used for data in transit, data at rest, data volume encryption, and SSL/TLS web certificates must have a minimum key length of 256 bits.

This project originated from a security directive issued by the Chief Information Security Officer (CISO) to ensure that all encryption implementations align with organizational security policies and industry standards.

---

### Project Objectives

* Identify and document all encryption algorithms used for data at rest, data in transit, data volume encryption, and SSL/TLS certificates.
* Assess compliance with organizational security policies requiring a minimum key length of 256 bits.
* Identify any outdated or vulnerable encryption mechanisms and propose remediation strategies.
* Ensure encryption configurations align with industry standards such as NIST, ISO 27001, and regulatory requirements.
* Provide a detailed report with recommendations for enhancements and necessary upgrades.

---

### Scope
#### In Scope

* Review of encryption algorithms used for:
** Data at Rest (Databases, file storage, backups, data volume encryption, etc.)
** Data in Transit (Network communications, VPNs, internal APIs, etc.)
** SSL/TLS certificates for web applications
* Key management practices and their alignment with security best practices
* Compliance verification with relevant regulations and industry frameworks
* Risk assessment of non-compliant encryption mechanisms

#### Out of Scope

* Implementation of encryption upgrades (will be addressed in a separate project if necessary)
* Third-party vendor systems outside the organization’s control

---

### Key Deliverables

* **Encryption Inventory Report** – A comprehensive document listing all encryption mechanisms in use, including data volume encryption algorithms.
* **Compliance Assessment Report** – A gap analysis identifying non-compliant encryption implementations.
* **Risk Analysis Report** – Documentation of security risks associated with outdated encryption algorithms.
* **Recommendation Report** – Actionable recommendations for encryption enhancements and compliance improvements.
* **Executive Summary** – A high-level overview for senior management outlining key findings and next steps.

---

### Timelines & Milestones

| Milestone | Target Completion Date |
| --------- | ---------------------- |
| Project Kickoff | Start Date |
| Data Collection and Encryption Inventory | +2 weeks |
| Compliance Assessment and Risk Analysis | + 4 weeks |
| Recommendations and Final report | + 2 weeks |
| Presentation to Leadership | + 1 week |

---

### Resources and Stakeholders

#### Project Team

* Security Analyst Lead
* IT Security Engineers
* Network Administrators
* Database Administrators
* Compliance Officer(s)

#### Stakeholders

* Chief Information Security Officer (RISO)
* IT Operations Team
* Legal and Compliance Teams
* Applications Owners

---

### Assumptions & Constraints

#### Assumtions

* The organization has up-to-date documentation of encryption implementations.
* Relevant stakeholders will provide necessary access to encryption configurations.
* Assessment tools are available for encryption analysis.

#### Constraints

* Limited access to third-party vendor encryption details.
* Potential downtime considerations for testing or remediation efforts.
* Resource availability for conducting assessments.

---

### Risks and mitigation Strategies

| Risk  | Likelihood | Impact | Mitigation Strategy |
|-------|------------|--------|---------------------|
|Lack of documentation on encryption use | Medium | High | Conduct stakeholder interviesv and use scanning tools |
| Resitance to upgrading encryption due to compatibility concerns | High | High | Provide phased upgrade plans with risk assessments |
| Discovery of non-compliant encryption close to audit deadlines | high | High | Prioritise remediation efforts and document risk acceptance where necessary | 

---

### Approval

Approved by:
* Project Sponsor
* CISO/RISO
* Information Security Manager

---

This project serves to ensure the successful assessment and compliance of encryption standards within the organization.

