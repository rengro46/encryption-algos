

---

## Validation of encryption algos in use:
The development of a web portal to create a consolidated matrix view of user accounts across all customer SAP instances to aid in the timely removal of accounts where access is no longer required for a user to a specific SAP instance

---

### Description

This project was initiated by receiving a Security Directive from the office of CISO to ensure that all encryption algo's being used in the organisation are secure and have a key-length of at least 256 bits. The directive was focused on addressing three specific security areas of concern for the business:y
1. Checking the current set of communication encryption algorithms in use (Data in Transit)
2. Checking the encryption status of disk volumes (Data at Rest)
3. Checking the key lengths of the SSL Web certificates in use

No scope of work/assessment of current state of the business was received from CISO to point towards specific areas to go remediate, only a blanket statement to review all encryption algo's in use, therefore I separated the project into two phases being:
- Current State Assessement
- Remediation


---

### Current State Asessment

---

#### Identify Assets associated with insecure communication encryption protocols in use:

Due to a number of legacy Operating systems existing in the environment (Windows 2012, CentOs6.x, Ubuntu 12,14,16 and 18, Debian 8) still in use throughout the organisation, it was decided to check for the existance of depracated encryption protocols including:
- SSL 2.0 and SSL 3.0 and
- TLS 1.0 and TLS 1.1

Using tools like NMAP and SSLSCan in a limited scope evironment identified for a POC, a detailed understanding of how to enumerate and interrogate ports using encryted communication was achieved.
This investigation helped with the identification of all of the QID's associated with SSL1, SSL2, SSL3, TLS 1.0 and TLS 1.1 In addition, a list of encryption protocols, already deemed insecure by the Security industry was compiled, and QID's associated with each of these depracated encryption algo's were identified and appended to the initial list of QID's identified for insecure transport protocols.
Using the complete list of QID's identified, a custom asset report was created in Qualys Asset module, to extract a list of assets with any of the associated QID’s identified. The resulting asset report was then used as the basis for the remediation plan to address those items found lacking ito secure communication protocols, insecure encryption algo’s and the directive received from CISO.

#### Identify Assets associated with insecure disk encryption protocols in use:

The encryption status of disks across the organisation was approached in a simple categorisation method.
All server disks on premise were interrogated with a script based approach, including Powershell for Windows based servers, and python for Linux based server platforms. A number of challenges were experienced, some around the specifics of python regarding the linux distributions but mainly around firewall access to specific systems. Once this was resolved, the disk encryption status results were written into a database, with the intent of using the database for analysis and reporting. The extraction of all cloud based disk partition encryption status (incl. Azure and AWS) was done using their respective CLI’s, with results written to same database as used for on-prem data disks info
A summary report was compiled to portray the full picture of the entire organisation’s disk encryption status, and subsequently published to a WEB page.

#### Identify Assets associated with insecure SSL certificates in use:

Collection of information regarding SSL certificate in use for on-prem servers, was done using a combination of Qualys Certificate Store, New Qualys Agents Scans and Qualys Network scan results, some python scripts and some Powershell scripts to extract info from windows server registry entries.
Extraction of Cloud based certificate info included Azure Entra, Powershell scripts, Azure Key Vault, AWS Certificate Manager, Qualys Certificate Store and Python scripts for 3rd party certificates, results were written to the previously created database.

A custom report was created to:
- Show disk volumes which did not have encryption enabled and
- Those disk volumes using insecure encryption algo’s already identified previously

This report was published to the same website as used previously for the comms protocol info. The entire process to collect, collate and publish this comms, diskand certificate encryption information was automated and implemented as a live data report for use by the organisations Information Security Manager as well as the Regional Information Security Officer going forward.

This concluded the assessment/investigation phase.


---

### Remediation Phase

---

Once the assessment info was published and shared with the operational teams responsible for supporting and updating these platforms, the Remediation initiative was kicked off.
A detailed extract of all server information, including operating systems and versions was provided to each of the technical engineering teams to review and provide feedback.
Upon receiving feedback it became clear that all of the platforms still running End of Life operating systems were constrained by the legacy applications hosted on those systems. A Large number of application owners were contacted and a process was started to either sunset, redevelop or re-host the current set of legacy applications.
Those applications for which the owners could not be found was escalated to the Regional CIO for a decision on how to proceed. An evaluation was made by the regional CIO of the usage of these legacy apps for which owners could not be found. Around 20 of the 25 apps for which owners could not be found were deemed unsuitable for future use and were retired via a Change management process. The other 5, for which the code was still available in the organisational code repo was earmarked for being migrated/replatformed into docker containers
The remaining 67 legacy applications were earmarked for either redevelopment, replatforming of retain status, till their functionality could either be retired or incorporated into one of the applications identified to be redeveloped. This retain period was capped at a maximum of 6 months from the date of decision.

This remediation phase was intended to be completed within 10 months in total, some external factors caused some delays, and was eventually signed off by Exco as complete after a periond of 12 months.

---