# CS-305-PROJECT-TWO

# Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?

Artemis Financial is a financial services firm that provides various plans (savings, retirements, etc.) to their clients and, in doing so, handles sensitive user data. Our goal was to improve the security of their software, and we did so by securing data transmissions using HTTPS and implementing SHA-256 hashing for integrity checks. The original code had some known issues, and my task was to identify those problems and refactor the system to follow industry security practices.

# What did you do well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall well-being?

I quickly spotted that the original SHA-256 hashing output was in an incompatible format. This led me to applying fixes such as creating a hex conversion loop and fixing this issue. Additionally, although it took a bit longer, I managed to find a vital HTTPS issue that occurred due to the misconfiguration of certificates. After trial and error I found the right attributes and identified the SAN issue on the certificate allowing me to implement HTTPS in the program.

Secure code is essential, in our case, working with Artemis, helped us establish a safe way to prevent data leaks and other issues which in turn would help our client build trust with their users. This, of course, is an essential for any company, and especially a financial company like Artemis that handles sensitive data on a daily basis. 

# Which part of the vulnerability assessment was challenging or helpful to you?

The most frustrating, albeit educational, part was trying to get HTTPS to work in the browser. Even after generating a keystore and self-signed certificate, the browser refused to trust it because it didn’t include a SAN. That wasn’t something I expected or understood initially. 

That said, once I fixed it and reinstalled the certificate properly into the system’s trusted root, it worked. 

Now for the helpful side, I would say that using the OWASP Dependency-Check tool was a great way to scan for known vulnerabilities quickly.

# How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?

I improved security by enabling SHA-256 hashing, fixing the formatting with proper hex encoding, setting up HTTPS with a valid certificate, and correctly configuring the keystore in Spring Boot. 
If I were doing this in the real world, I’d probably also use tools like OWASP which is one of the most important tools I learned about in this semester. 

As this tool would easily help me find and fix any issues and vulnerabilities enabled by external 3rd party dependencies.

# How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?

I tested the HTTPS connection in a browser, checked that the certificate was installed correctly, and made sure the SHA-256 hash was printed in the correct format.
After that, I ran the Maven build and executed the OWASP Dependency-Check again to verify that no new issues were introduced by my refactored code. 

After looking at the report and console logs I realized that I had not introduced any new vulnerabilities.

# What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?

I used Java keytool, the OWASP Dependency-Check Maven plugin, SHA-256 documentation from Oracle, and the many other resources and reading provided by the modules. Specifically, our main book Iron-Clad Java is pretty solid, and provided great information on secure development. If I ever work on Java or security projects again, it’s likely that I’d use these resources for help.

# Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?

Great question!

I’d highlight how I became familiar with utilized maven project spring boot with the OWASP plugin to identify third party vulnerabilities, handle SSL setups, certificate generation, and hash encryptions.
I can easily point to this project and it would work as my proof of me knowing how to troubleshoot and apply secure development practices, even when unexpected issues arise. 

This project not only shows that I understand not just how to write code, but how to secure it in a real-world deployment environment.
