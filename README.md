# CS-305-8-1-Journal-Portfolio Reflection
Artifact: Artemis Financial Practices for Secure Software Report

1. Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?
The client was Artemis Financial, a financial consulting company. They wanted to modernize their web application and were concerned about software security. Specifically, they wanted to address file verification (ensuring data integrity) and secure communications (protecting data in transit) to ensure their client financial data remained safe and compliant.

2. What did you do well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?
I successfully implemented SHA-256 hashing for file integrity and configured an SSL/TLS certificate to convert the application from HTTP to HTTPS. Coding securely is crucial because it protects a company's reputation and prevents costly data breaches. For a financial firm like Artemis, software security adds immense value by ensuring regulatory compliance (like GLBA and PCI-DSS), maintaining customer trust, and protecting sensitive financial assets from malicious actors.

3. Which part of the vulnerability assessment was challenging or helpful to you?
Integrating and interpreting the OWASP Dependency-Check report was both challenging and helpful. It was challenging to see 254 vulnerabilities and realize they were coming from the pre-existing Spring Boot framework and its transitive dependencies. However, it was highly helpful to learn how to configure the NVD API and analyze which vulnerabilities were actually relevant to the code I was writing versus pre-existing framework issues.

4. How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?
I increased layers of security by adding cryptographic integrity via SHA-256, transport security via TLS/HTTPS, static dependency scanning via OWASP Dependency-Check, and manual code reviews. In the future, I would continue to use static analysis tools (like Dependency-Check or Snyk) alongside manual threat modeling to assess vulnerabilities. I would prioritize mitigations based on the CVSS (Common Vulnerability Scoring System) score—focusing on Critical and High vulnerabilities first.

5. How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?
I ensured the code was functional by running the Maven build (verifying a BUILD SUCCESS) and testing the /hash endpoint in the browser to confirm the SHA-256 checksum generated correctly. To check for new vulnerabilities, I re-ran the OWASP Dependency-Check tool after refactoring. I confirmed that the new code I added (using Java's built-in MessageDigest class) introduced zero new dependencies and zero new vulnerabilities.

6. What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?
I used Java Keytool for certificate generation, OWASP Dependency-Check for static analysis, and Java's MessageDigest class for cryptography. Moving forward, I will definitely use the OWASP Dependency-Check Maven plugin and the practice of using NIST-approved algorithms (like SHA-256) rather than outdated ones (like MD5 or SHA-1).

7. Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?
I would show future employers the refactored SslServerApplication.java code and the Dependency-Check reports. This demonstrates my ability to identify insecure protocols, implement secure hashing, configure SSL/TLS for secure web traffic, and perform static analysis on third-party dependencies. It proves I can take a vulnerable application and apply industry-standard security best practices to harden it.

