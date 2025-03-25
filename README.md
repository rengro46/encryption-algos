
---

### Validation of encryption algo's in use

This project was initiated by receiving a Security Directive from the office of CISO to ensure that all encryption algo's being used in the organisation are secure and have a keylength of at least 256 bits. 

No assessment of current state of the business was received from CISO to point towards specific areas to go remediate, only a blanket statement to review all encryption algo's in use. Therefore I sperated the project into two phasesbeing:
1. Investigation
2. Remediation

Due to a number of legacy Operating systems (Windows 2012, CentOs6.x, Ubuntu 12,14,16 and 18) still in use throughout the organisation, it was decided to check for the existance of depracated encryption protocols including:
1. SSL 2.0 and SSL 3.0 and 
2. TLS 1.0 and TLS 1.2
  
  Using tools like NMAP and SSLSCan, a basic understanding of how to enumerate and interrogate ports using encryted communication was achieved. This initial interrogation helped with the identification of a number of QID's associated with SSL1, SSL2 and SSL3 protocal as well as TLS1.0 and TLS 1.1

 Checking the current set of communication encryption algorithms in use (Data in Transit) as well as the encryption status of disk volumes (Data at Rest). Finally to compare compliance of the encryption algos in use to the published company standard and generating exception based reporting in PowerBI dashboard


---
