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

 9. 
 

 


 25. GDPR
