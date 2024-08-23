# Serverless-Email-Sending-Application

In this project, We can send an mail through simple  email service automatically.

Services used:
1.Aws SES(Simple Email Service) - for send mails
2.Lambda                        - for serverless with automatically functioned
3.S3                            - for storing email templates and list of contents
4.Event Bridge                  - for setup schedule and trigger lambda function
5.IAM                           - For give permissions

Procedure : 
1.To store email templates and list of contacts.
  Go to s3->create one bucket with blocking all public access->upload html,css files in that bucket(you can get thease files in this repo or chatgpt)

2.Configure SES to send mails
  Go to SES->Add email address and sending domain
  Go to SES->Send test mail->Also add 2identities by clicking viwe all identities(To verify SES service)

3.To merge email templates with contacts and send them to SES
  Go to Aws Lambda->Create function->select create newrole with basic lamda fuctions->paste the lamda fuctioncode which is attached in this repo->click deploy
  Go to Aws Lambds->Click configuration ->Select a role ->Click Addpermission->Create one new policy with attached code in this repo and add that policy in this role
  You can test the lamda function by creating test event using attached code in this repo.

4.To trigger lamda function using event brigde
  Go to Event Bridge->Create a schedule->Select date and time->Select target as lamda ->select lamda function->Create schedule
  Now you will receive mail at specified time.
  
