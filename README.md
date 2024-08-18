
# Weclome to this Sentinal lab 
List of tasks to be accomplised in this lab are as follows:
1. creating a sentinel workspace which is free for first 30 days of use of upto 10gb perday of data ingestion so there is no problem setting up a trial account and working towards it
2. setting up onprem and multicloud servers. in this tutorial i used my windows 11 pc and a linux machine on AWS which acts as on prem machine in this case  
3. setting up data connectors to various os and setting up configuration to azure activity logs as well as Entra ID logs. I also went ahead and installed the data connector for AWS cloudtrail which is equivalent to azure activity logs and bring that to Azure sentinel
4. To bring the logs from AWS to sentinel i had to create a stack in cloudformation using a template automatically created in sentinel while setting up the connector
5. installing Azure ARC and then azure monitor to ingest logs in Azure sentinel. Windows logs will be SecurityEvents table and the linux logs will be syslog table in the sentinel. 
6. Now that we will have all the necessary logs ingested in sentinel, we can go ahead and make some analytical rules. We can use build-in rules or we can make our own.
7. I couldnt find the one related to impossible travel login where one user login to azure from distant location within a short period of time which is impossible hence the name, so i made a custom NRT rule query using KQL for this which will run in short intervals of time to detect the suspicious login
8. I made some user accounts in entra for these next rules and made them sign-in from differnet locations using VPN and the results soon started showing on the dashborad of sentinel.
9. i made virustotal account and got the api key needed for the activity of making the playbook and getting the ipreputation of the said address in the query results and then made the playbook using logic app designer
10. Next i used an inbuild rule 'Priviliged role assigned outside of PIM' and then gave some user global admin role in Entra and soon the incident was showing up the dashboard.
11. For on-prem windows machine i used the event id 4720 as new user created on the windows machine as a alert and made an automation rule to select a playbook which emails the analyst about the alert

There are many substeps whithin each of these tasks. I tried to put screenshots for all important ones.__



>>>Setting up sentinel will automatically apply 30 days trial with 10gb per day limit and you continue using it for 30 days without any problem. Please note that sentinel can only run in certain regions https://learn.microsoft.com/en-us/azure/sentinel/geographical-availability-data-residency#supported-regions
![1](https://github.com/user-attachments/assets/1fe7d09d-075b-4e86-88dc-51a6060238e9)
>>>
>>>Installing Azure Activity data connector from content hub in Sentinel
![2](https://github.com/user-attachments/assets/2e28dba4-74d7-4788-bd4c-57e9c4d5708d)
>>>
>>>Configuring build-in analytical rule using activity logs
![2 1](https://github.com/user-attachments/assets/dfe0ae19-6b6a-41c5-8592-d9b967113dd0)
>>>
>>>Configuring activity logs rules
![2 2](https://github.com/user-attachments/assets/64c69c9d-10e8-4584-97f9-fe45c808730d)

>>>Activity logs started showing up in logs in sentinel
![2 3](https://github.com/user-attachments/assets/3d2d9ed5-3e36-4b8b-bd3d-1159833ba958)
![3](https://github.com/user-attachments/assets/b93dbbd3-5f15-44dd-96e0-e090830c954b)
>>>Streaming AWS cloudtrail logs using in-built data connector
![4](https://github.com/user-attachments/assets/0659f2a8-3366-4786-bc4b-aa9f71e259e4)
>>>For this we need an AWS account and role in AWS IAM uri, Microsoft ID and workspace ID
![5](https://github.com/user-attachments/assets/8bdae91f-4e03-4178-8c41-da3a6befd21a)
>>>
![6](https://github.com/user-attachments/assets/4c1ff5a3-4b1f-4d34-aba9-77a9b1ff8251)
![7](https://github.com/user-attachments/assets/31186f73-ffcd-4ab3-a672-bda5bd29bf5e)
![8](https://github.com/user-attachments/assets/b6aa33b9-1de2-470e-b211-285065e982bb)
>>>CloudTrial events started showing up in sentinel logs
![9](https://github.com/user-attachments/assets/46727e3d-f75c-4cfe-89f4-a59f971d0a5a)
>>>ENTRA ID connector configuration from content hub
![10](https://github.com/user-attachments/assets/c7f664c2-5222-4db3-a38e-50f58f292585)
>>>VirusTotal connector for threat intelligence based alerts
![11](https://github.com/user-attachments/assets/6f3ff261-904b-4c5f-b42b-f8dca463ab1c)
>>>AWS connector for Azure Arc
>>>https://learn.microsoft.com/en-us/azure/azure-arc/multicloud-connector/connect-to-aws
![12](https://github.com/user-attachments/assets/33965b7e-a50d-4e52-8b8f-8eae729f8c6d)

![13](https://github.com/user-attachments/assets/0932687d-0a3e-495b-b96b-6ad6eb3e3017)
![14](https://github.com/user-attachments/assets/7c43fc43-e449-4da1-86af-307e9907a012)
>>>For this connector you need to create Cloudformation stack using template provided in Azure

![15](https://github.com/user-attachments/assets/9a312bfe-f790-4b78-84af-cfe86090ef12)
![16](https://github.com/user-attachments/assets/cd81df54-0f17-470d-b994-6ad3f3b0a8b8)

>>>Azure Monitoring agent installation
![17](https://github.com/user-attachments/assets/b79ce393-15ee-4f3a-8a00-0bbe72766c2a)

>>>Logs from windows machine started showing up in log analytics
![18](https://github.com/user-attachments/assets/bd769f4b-732a-42b8-a05a-8e02c3cd8a5c)

![19](https://github.com/user-attachments/assets/520b4b14-5327-4ab8-89d2-f45fb8378176)

>>>Adding AWS enviroment for Defender alerts in Environment setting 
![20](https://github.com/user-attachments/assets/ab4d781d-bd64-4c37-8844-d9734e829b1e)
![21](https://github.com/user-attachments/assets/420b75e8-33c1-4628-9b8d-84e5fb72eee9)
>>>These custom roles will be created in AWS
![22](https://github.com/user-attachments/assets/714607cd-3f9b-4727-88a8-8351c0cf2c24)
>>>AWS is now covered with Defender for cloud
![23](https://github.com/user-attachments/assets/a957b8ec-52ab-4b33-b4c6-0fa7835b3a7f)

![24](https://github.com/user-attachments/assets/07f8943b-35f7-4e43-9c09-9833ff0ebaab)

>>>Sample alerts in Sentinel 
![25](https://github.com/user-attachments/assets/5cc70d2c-9849-4473-9e2a-c9e53dede0fa)

>>>installing Azure Arc agent with windows MSI installer
![26](https://github.com/user-attachments/assets/1d7242a7-1d1f-4a78-9bb0-956aa4d3138e)
>>>You will be asked for azure credentials and machine will be connected
![27](https://github.com/user-attachments/assets/9056e765-7885-4a91-a337-6179489d4368)
>>>This machine can now be added to DCR rules and will show in the following resouces
![28](https://github.com/user-attachments/assets/858bac7d-8afb-41aa-8cb5-5fb4964bba6f)

![29](https://github.com/user-attachments/assets/09916999-0c9a-4670-be9f-47c011883c73)

>>>Now i will install azure arc agent on a linux machine. Instead of using my own machine, i used EC2 instance
![37](https://github.com/user-attachments/assets/4e41f38b-bc91-46b0-ae20-3ac7ad15ef06)
>>>A onboardingcript will be provided in azure to run on linux machine 
![38](https://github.com/user-attachments/assets/b419afa6-9a2b-454e-a4ec-b94ea3f735d1)
>>>first i i will secure copy it to the instance running in ec2 using my KALi linux( as this is not supported OS for azure Arc)
![39](https://github.com/user-attachments/assets/d59a1e09-57ed-4634-88b0-66e79d335f46)
>>>then i SSHed myselfy in to the instance and ran the .sh script
![40](https://github.com/user-attachments/assets/34683837-fa41-468b-b851-1a1940b89aa7)
![41](https://github.com/user-attachments/assets/5aee1e3a-f96f-4205-8d40-c5b7294aaacb)
>>>I had to change the permisiions of the file using chmod command to make it executable
![42](https://github.com/user-attachments/assets/5a338952-0c49-4d00-af45-012100f7dd98)
>>>Running the script i got a code to enter in web console which i added
![43](https://github.com/user-attachments/assets/9786dfc8-8dab-41eb-9e2f-5ac78cb9f2f6)
![44](https://github.com/user-attachments/assets/dc8bd5e9-9e44-4503-b8f8-4a1ff2d1a316)

>>>Azure Arc succesfully installed on Amazon linux
![45](https://github.com/user-attachments/assets/ff88fadb-27e2-42a3-a7e8-925d7544645e)
![46](https://github.com/user-attachments/assets/587ec078-bf43-4fd5-87ca-d6445690dee4)
![47](https://github.com/user-attachments/assets/00dc2e4c-e236-45ba-841b-7187945380d0)

Select the sidebar select analytics and then make a new sechduled rule 
![Screenshot 2024-08-15 235443](https://github.com/user-attachments/assets/63d41201-5319-47f0-8e74-41a560dbc434)

![Screenshot 2024-08-16 223545](https://github.com/user-attachments/assets/a9aea133-a3b2-4f91-bc5e-a663b5b765fe)

I used the follwing query for the analytics rule.This basically produce results if their is login in entra id from distant plwce in short interval of time

![Screenshot 2024-08-16 223710](https://github.com/user-attachments/assets/9846407b-b256-45b5-927e-a6b60bf939ca)
![Screenshot 2024-08-16 223726](https://github.com/user-attachments/assets/a4ac93ee-1165-4405-90fe-0bea00147814)

Activating an inbuilt rule whuch identifies a privilaged user account created outside of PIM

![Screenshot 2024-08-16 223756](https://github.com/user-attachments/assets/4d28e625-3539-4b47-ae18-5853db0cce88)

![Screenshot 2024-08-16 223805](https://github.com/user-attachments/assets/23831cd6-48a5-44f8-a8f5-f04c54159d6c)


![Screenshot 2024-08-16 223822](https://github.com/user-attachments/assets/c8e544f8-3f43-4eca-ae52-e438dce79633)

Incidents are created in the dashboard

![Screenshot 2024-08-16 223921](https://github.com/user-attachments/assets/f1b13056-dd95-48a0-b942-8136ddab02bd)




![Screenshot 2024-08-16 223934](https://github.com/user-attachments/assets/bf99cc40-57a8-43cf-be91-2301c0c2c5c3)
![Screenshot 2024-08-16 224007](https://github.com/user-attachments/assets/54544b93-17da-4053-b534-1addc808ea5a)
created automation rule to assign owner to the alert when it will be generated
![Screenshot 2024-08-16 224113](https://github.com/user-attachments/assets/e92edc76-26a5-4dd4-9ed3-cc555b3a160c)

I also created the users in my on prem windows machine and made analytical rule to triiger alert on the new user creation

![Screenshot 2024-08-18 132937](https://github.com/user-attachments/assets/28c3c298-4541-47c9-9115-0d17605cf468)

Made a kql query for securityevnets table like this 

![Screenshot 2024-08-18 133900](https://github.com/user-attachments/assets/e6698493-c4d9-4015-8537-00ad03e69747)

For sending an email when the alert is triggerd i made a playbook using logic apps desginer like this 

![Screenshot 2024-08-18 134220](https://github.com/user-attachments/assets/0c93416c-378c-4578-bdb3-05b3d9bbeaa5)

![Screenshot 2024-08-18 134345](https://github.com/user-attachments/assets/1d0cbe66-c7e6-4576-a795-a411a82233a5)


Next i made the automation rule from the alert creation menu and added logic app when alert of this type is created

![Screenshot 2024-08-18 134752](https://github.com/user-attachments/assets/93e29597-9fa6-4cea-90b6-8d284e60704c)

incident created for new user alerts

![Screenshot 2024-08-18 134939](https://github.com/user-attachments/assets/86664a67-bfc0-4009-b803-f88625d3eb14)

![Screenshot 2024-08-18 135322](https://github.com/user-attachments/assets/8d747290-c22d-4169-bed0-cd7295c97c0c)

The simple query i used for this rule

![Screenshot 2024-08-18 135608](https://github.com/user-attachments/assets/02b62cf8-32c1-4a02-a6de-5965ecb56cb7)

Be sure to give access to Logic app for sentinel reader and sentinel contributor if required

![Screenshot 2024-08-18 140156](https://github.com/user-attachments/assets/2c84774b-9729-423e-9959-2ac0538d024f)

also permission to sentinel for resource group where logic apps are present

![Screenshot 2024-08-17 000631](https://github.com/user-attachments/assets/7c9ff91b-23bc-4da8-b486-66cdda4bdc4e)


email started showing up


![Screenshot 2024-08-18 141005](https://github.com/user-attachments/assets/0d939eab-6b92-4b9d-9aeb-a86da14e3d5d)


Now i created a newplaybook for the a;erts i got from impossible sign in to entra id. we will search the ip address in the database of virus total useing the api key that we will obtain from virustoatal page, and then getting the ip repution for that and if its not good we can choose to do number of task 
for the next part i created a account with virus total to get the api key need for the next part of automation with playbook and logic apps

![Screenshot 2024-08-16 224842](https://github.com/user-attachments/assets/3070a473-8a2b-44d6-b21b-b4adc10f8df1)

creating the playbook and ensuring i have dataconectors for all the serives used in the app

![Screenshot 2024-08-16 225733](https://github.com/user-attachments/assets/63d58d24-dc83-4069-8cd7-e9ddc118f038)


![Screenshot 2024-08-16 225955](https://github.com/user-attachments/assets/dd754637-3d10-4b0e-9bab-639b2ded5cc2)
![Screenshot 2024-08-16 230836](https://github.com/user-attachments/assets/7d03fc81-c8b8-440c-a96d-954ae93c60eb)

![Screenshot 2024-08-16 231330](https://github.com/user-attachments/assets/383733c9-2125-43b1-9965-666d77b68b35)


Make sure sentinel and logic app have proper permisions to acton the playbook( like we did in the slides above) and the rule is ready to run
With this this lab is concluded..........
