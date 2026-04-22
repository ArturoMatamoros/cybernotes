# Lab — DVWA CSFR CSS

**Goal:** 
- being able to hack through the CSFR level low 
- I have to create an html page so I will be able to insert a link
	- that will let me change the password 
**Attempt:**
- create the [[Docker]] container with DVWA 
- setting up [[Burpsuite]] so that I can access all the information 
- writing a simple form [[HTML]] with a button option able to bring us to a desired link
- getting inside the CSRF page and using a change of password
- since we have bs on we will be able to copy the link 
	- in my case the link is  http://172.17.0.1:81/vulnerabilities/csrf/?password_new=password&password_conf=password&Change=Change 
	- thanks to this link we know the name of the variables used by the program and the link where the call is made
- In the HTML I use all the information that I got to:
	- create a fake change password page that has no effect for the user
	- bring him back to the desired page once pressed the button 
	- use hidden to change the password in the one I decide
**Broke:** 
- I struggled very much with the HTML side of the project and the programming. I had many trials where I would bring myself to the copied link above instead of using the information.
**Fixed:** 
- I look at how the actual process works inside, by doing this I understood that simply using the link for my "change password" form would not work. 
**Learned:**
- how burp suite will be important to truly understand the inside of a site
- how HTML works and some features like hidden that can manipulate anything we want inside the document

**links:** 
- [[Docker]]
- [[Burpsuite]]
- [[HTML]]