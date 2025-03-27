
---

### Validation of encryption algo's in use

This project was initiated by receiving a Security Directive from the office of CISO to ensure that all encryption algo's being used in the organisation are secure and have a keylength of at least 256 bits. The directive was focused on addressing three specific security areas of concern for the busesness:
1. Checking the current set of communication encryption algorithms in use (Data in Transit)
2. Checking the
   a. encryption status of disk volumes (Data at Rest)
   b. encryption algo's used for disk encryption
4. Checking the key lengths of the SSL WEB certificates in use

No assessment of current state of the business was received from CISO to point towards specific areas to go remediate, only a blanket statement to review all encryption algo's in use. Therefore I seperated the project into two phases being:
1. Current State Assessement
2. Remediation

1. Investigation
Due to a number of legacy Operating systems existing in the environment (Windows 2012, CentOs6.x, Ubuntu 12,14,16 and 18, Debian 8) still in use throughout the organisation, it was decided to check for the existance of depracated encryption protocols including:
1. SSL 2.0 and SSL 3.0 and 
2. TLS 1.0 and TLS 1.1
  
Using tools like NMAP and SSLSCan, an detailed understanding of how to enumerate and interrogate ports using encryted communication was achieved. This interrogation helped with the identification of a number of QID's associated with SSL1, SSL2 and SSL3 protocols as well as for TLS1.0 and TLS 1.1 and TLS 1.2. In addition, a list of encryption protocols, already deemed insecure by the Security industry was compiled, and QID's associated with each of these depracated encryption algo's was created and appended to the initialv list of QID's identified for insecure transport protocols. 

Using the compiled list of QID's identified, a custom asset report was created in Qualys Asset module, to extract a list of assets with any of the identified QID's found. The resulting asset report was then used as the basis for the remediation plan to address those tiems found lacking compared to the direcive received from CISO  



2. Remediation
   
---
