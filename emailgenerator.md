# Project For Fun! The Email Generator
---
### Have you ever been faced with needing to send personalized emails to a large group of people? I wrote some code for just this problem. 
---
**My Inspiration**: My girlfriend needed to send 100s of emails for her work, all which came from an excel sheet which contained first name, last name, and email address as seen below.

---
### Using the format:
````
Hello [Personalized Name],

Please respond if you are coming to my cookout next Friday. 

Best,

Jordan
````


<img src="images/list.png?raw=true"/>

### Sample of code

`````
# iterate through each email address
for i in range(len(emails)):
  
    server.set_debuglevel(1)
    body = "Hello" + " " + names[i] + "," + "\n" + "\n" +  "I hope this email finds you well and you are enjoying the start of summer. I am excited to reach out to you to see if you are interested in coming to our BBQ! Please RSVP by Friday! !" + "\n"+ "\n" + "Best," + "\n"+ "\n" + "Jordan" +"\n" "TWN"+ "\n"+ "\n"
    msg = MIMEMultipart()
    sender = 'senderemail@gmail.com'
    recipients = emails[i]
    msg['Subject'] = "BBQ"
    msg['From'] = "Your Name"
    msg['To'] = emails[i]
    msg.attach(MIMEText(body, 'plain'))
    msg.attach(part)
    server.sendmail(sender, recipients, msg.as_string())


# close the smtp server
server.close()
print('Mail Sent')

`````

**Note**: This is different from a BCC email because it sends the email with their unique name in it!
