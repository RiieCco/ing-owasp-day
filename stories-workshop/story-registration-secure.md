### Priority: High

#### Component: User registration

- **As** a new user
- **i want** to be able to to register myself
- **So** that i can use premium features on the application



###### Acceptance criteria:

- User need to provide a username (e-mail), first and last name 
- User need to provide a phone number with the format as +XX XXX XX XX XXX
- User need to input his date of birth
- Password can not be smaller than 8 symbols and maximum of 25 symbols


###### Acceptance criteria Security (Development):

| ID 	| Control 	|
|----	|---------	|
|2.1.1|Verify that user set passwords are at least 12 characters in length. (C6)
|2.1.2|Verify that passwords 64 characters or longer are permitted.
|2.1.3|Verify that passwords can contain spaces and truncation is not performed. Consecutive multiple spaces MAY optionally be coalesced.
|2.1.7|Verify that passwords submitted during account registration, login, and password change are checked against a set of breached passwords
|2.1.8| Verify that a password strength meter is provided to help users set a stronger password.
|2.1.9|Verify that there are no password composition rules limiting the type of characters permitted. There should be no requirement for upper or lower case or numbers or special characters.
|2.1.11|Verify that "paste" functionality, browser password helpers, and external password managers are permitted.
|2.2.1|Verify that anti-automation controls are effective at mitigating breached credential testing, brute force, and account lockout attacks. Such controls include blocking the most common breached passwords, soft lockouts, rate limiting, CAPTCHA, ever increasing delays between attempts, IP address restrictions, or risk-based restrictions such as location, first login on a device, recent attempts to unlock the account, or similar. Verify that no more than 100 failed attempts per hour is possible on a single accoun
| 5.2.2| Verify that unstructured data is sanitized to enforce safety measures such as allowed  characters and length.
| 5.1.4|Verify that structured data is strongly typed and validated against a defined schema including allowed characters, length and pattern (e.g. credit card numbers or telephone, or validating that two related fields are reasonable, such as checking that suburb and zip/postcode match)
|8.3.4|Verify that all sensitive data created and processed by the application has been identified, and ensure that a policy is in place on how to deal with sensitive data.
|11.1.4 |Verify the application has sufficient anti-automation controls to detect and protect against data exfiltration, excessive business logic requests, excessive file uploads or denial of service attacks.