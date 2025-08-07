# reCAPTCHA-AWS-Lambda-GDPR
 Secure Contact Form Integration with reCAPTCHA &amp; AWS Lambda and GDPR 

# Secure Contact Form Integration with reCAPTCHA With AWS Lambda & GDPR. #

I decided to go with reCAPTCHA v2 as it provides a visible protection with less backend coding (minimising attack surface area), providing maximum security and a well known interaction albeit annoying to my visitors but secure.

The other option i had was to Rate-Limit Numers of Emails per IP per Day using AWS Lambda and DynamoDB for Rate limiting but this required users to fill in their IP addresses and for crosschecking with the existing DynamoDB table to see how many messages the user sent on a particular day and if it`s over the limit. 

I didn`t choose this because of VPNs can be used to bypass this and also it`s too cumbersome for my users and doing puzzles is way less annoying. 


 # I Added reCAPTCHA v2 (Checkbox) to My Contact Form by 

 1. Registering my domain denisriungu.de Website on Google reCAPTCHA

 ![alt text](<Bilder/Screenshot (340).png>)

 Site Key is to be used in your HTML

 Secret Key is to be used in Lambda backend to verify responses comming from the frontend.

 2. Updated My HTML Form to include the reCAPTCHA Site Key. 

 ![alt text](<Bilder/Screenshot (341).png>)

 3. Updated My Javascript to Send the g-recaptcha-response from JavaScript
 Update the form submission

 ![alt text](<Bilder/Screenshot (342).png>)

 4. Updated my AWS Lambda Backend (Python 3.12)
 in order to verify the CAPTCHA token server-side before processing the email.

 ![alt text](<Bilder/Screenshot (346).png>)

 5. Test the flow. Try Sending message without solving the CAPTCHA:

 ![alt text](<Bilder/Screenshot (356).png>)

 6. Test the flow. Try sending a message, this time by solving the CAPTCHA.

 ![alt text](<Bilder/Screenshot (357).png>)

 7. Test the Flow. Solved the CAPTCHA and Sent the message
 
 ![alt text](<Bilder/Screenshot (358).png>)

 8. Test the Flow. Message Received on gmail.

 ![alt text](<Bilder/Screenshot (359).png>)

 


 # Including a Secure & Compliant GDPR Strategy #

 This is because users will be submiting their name, email and messages via my
 contac form on my website denisriungu.de. under EU GDPR, i am legally responsible for.
  . Inform and notify my users what data i am collecting and why.
  . Securing that data during collection and transfer.
  . getting explicit consent before collection.
  . Giving users the right to withdraw consent and request data deletion.
  . Ensure no unnecessary tracking without consent (e.g., Google reCAPTCHA cookies, analytics, etc.).


  # I have implemented this by 

1. Adding a GDPR Consent Checkbox to my html Form just above the submit button
on the contact.html page. 

![alt text](<Bilder/Screenshot (363).png>)

2. Then I Created a Privacy Policy Page, this page explains what data I am collecting and how it's used as well
as who i am and how to get in touch with me. 

![alt text](<Bilder/Screenshot (364).png>)

3. I added a Javascript Validation for GDPR checkbox in order to ensure that the checkbox is selected before
allowing message Submission. 

![alt text](<Bilder/Screenshot (366).png>)

4. Push the changes made to the website to github CI/CD with GithubActions to the S3 Bucket.

![alt text](<Bilder/Screenshot (367).png>)

![alt text](<Bilder/Screenshot (368).png>)

5. Test run and see if everthing is working.

  No Submission Without accepting the Datenschütz

![alt text](<Bilder/Screenshot (370).png>)

  No Submission without filling out the CAPTCHA: 

![alt text](<Bilder/Screenshot (371).png>)

 6. Submission accepted once all the Boxes are checked.

 ![alt text](<Bilder/Screenshot (372).png>)

 

 # Bonus Security Transport & Data Protection Notes 

 . The website is already served via HTTPS with CloudFront, so data transmission is encrypted
 . The Lambda function processes and sends the email without storing any data.


 # Include a Cookie Concent Banner

 1. I researched abit and found out that i will need to create a Cookie consent Banner since my website uses Google 
 reCAPTCHA which sets cookies to detect bots, which counts as tracking under the EU GDPR and ePrivacy Directive.

 thus i have to inform my visitors and get their explicit consent once they land on my website. 

 2. To intergrate a cookie consent banner, we will have to build a cookie-consent javascript page. or Cookie-consent.js.

 ![alt text](<Bilder/Screenshot (376).png>)

 3. The cookie-consent.js page shows the banner when the user first visits the website and explains what cookies are used and asks for permission and only loads non-essential cookies (like reCAPTCHA) after consent is given.

 ![alt text](<Bilder/Screenshot (374).png>)

 # How does This Help 

 . Legal Compliance: GDPR, ePrivacy, and German TTDSG.

 . Transparency: Users know what data is collected.

 . Trust: In that we respect Data privacy and legal standards.

 . Banner must be visible until the user takes action (Accept/Reject/Manage).

                 
                 After acceptance, it can disappear.                   
