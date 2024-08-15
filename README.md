
Weclome to this Sentinal lab
List of tasks to be accomplised in this lab are as follows:
1. creating a sentinel workspace which is free for first 30 days of use of upto 10gb perday of data ingestion so there is no problem setting up a trial account and working towards it
2. setting up onprem and multicloud servers. in this tutorial i used my windows 11 pc and a linux machine and as AWS as the other cloud using EC-2 linux instance  
3. setting up data connectors to various os and setting up configuration to azure activity logs as well as Entra id logs. I also went ahead and installed the data connector for AWS cloudtrail which is equivalent to azure activity logs and bring that to Azure sentinel
4. To bring the logs from AWS to sentinel i had to create a stack in cloudformation using a template automatically created in sentinel while setting up the connector
5. installing Azure ARC and then azure monitor to ingest logs in Azure sentinel. Windows logs will be SecurityEvents table and the linux logs will be syslog table in the sentinel. 
6. WORK IN PROGRESS>>>>


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

>>>>>>Activity logs started showing up in logs in sentinel
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
CloudTrial events started showing up in sentinel logs
![9](https://github.com/user-attachments/assets/46727e3d-f75c-4cfe-89f4-a59f971d0a5a)
ENTRA ID connector confogration from content hub
![10](https://github.com/user-attachments/assets/c7f664c2-5222-4db3-a38e-50f58f292585)
VirusTotal connector for threat intelligence based alerts
![11](https://github.com/user-attachments/assets/6f3ff261-904b-4c5f-b42b-f8dca463ab1c)
AWS connector for Azure Arc
![12](https://github.com/user-attachments/assets/33965b7e-a50d-4e52-8b8f-8eae729f8c6d)

![13](https://github.com/user-attachments/assets/0932687d-0a3e-495b-b96b-6ad6eb3e3017)
![14](https://github.com/user-attachments/assets/7c43fc43-e449-4da1-86af-307e9907a012)
For this connector you need to create Cloudformation stack using template provided in Azure

![15](https://github.com/user-attachments/assets/9a312bfe-f790-4b78-84af-cfe86090ef12)
![16](https://github.com/user-attachments/assets/cd81df54-0f17-470d-b994-6ad3f3b0a8b8)
![17](https://github.com/user-attachments/assets/b79ce393-15ee-4f3a-8a00-0bbe72766c2a)
![18](https://github.com/user-attachments/assets/bd769f4b-732a-42b8-a05a-8e02c3cd8a5c)
![19](https://github.com/user-attachments/assets/520b4b14-5327-4ab8-89d2-f45fb8378176)
![20](https://github.com/user-attachments/assets/ab4d781d-bd64-4c37-8844-d9734e829b1e)
![21](https://github.com/user-attachments/assets/420b75e8-33c1-4628-9b8d-84e5fb72eee9)
![22](https://github.com/user-attachments/assets/714607cd-3f9b-4727-88a8-8351c0cf2c24)
![23](https://github.com/user-attachments/assets/a957b8ec-52ab-4b33-b4c6-0fa7835b3a7f)
![24](https://github.com/user-attachments/assets/07f8943b-35f7-4e43-9c09-9833ff0ebaab)
![25](https://github.com/user-attachments/assets/5cc70d2c-9849-4473-9e2a-c9e53dede0fa)
![26](https://github.com/user-attachments/assets/1d7242a7-1d1f-4a78-9bb0-956aa4d3138e)
![27](https://github.com/user-attachments/assets/9056e765-7885-4a91-a337-6179489d4368)
![28](https://github.com/user-attachments/assets/858bac7d-8afb-41aa-8cb5-5fb4964bba6f)
![29](https://github.com/user-attachments/assets/09916999-0c9a-4670-be9f-47c011883c73)
![37](https://github.com/user-attachments/assets/4e41f38b-bc91-46b0-ae20-3ac7ad15ef06)
![38](https://github.com/user-attachments/assets/b419afa6-9a2b-454e-a4ec-b94ea3f735d1)
![39](https://github.com/user-attachments/assets/d59a1e09-57ed-4634-88b0-66e79d335f46)
![40](https://github.com/user-attachments/assets/34683837-fa41-468b-b851-1a1940b89aa7)
![41](https://github.com/user-attachments/assets/5aee1e3a-f96f-4205-8d40-c5b7294aaacb)
![42](https://github.com/user-attachments/assets/5a338952-0c49-4d00-af45-012100f7dd98)
![43](https://github.com/user-attachments/assets/9786dfc8-8dab-41eb-9e2f-5ac78cb9f2f6)
![44](https://github.com/user-attachments/assets/dc8bd5e9-9e44-4503-b8f8-4a1ff2d1a316)
![45](https://github.com/user-attachments/assets/ff88fadb-27e2-42a3-a7e8-925d7544645e)
![46](https://github.com/user-attachments/assets/587ec078-bf43-4fd5-87ca-d6445690dee4)
![47](https://github.com/user-attachments/assets/00dc2e4c-e236-45ba-841b-7187945380d0)
![48](https://github.com/user-attachments/assets/958be2b3-6cee-45a9-b799-ee24c56f7756)
![49](https://github.com/user-attachments/assets/b6a6767e-6306-4abe-957a-f587d316bf55)
![50](https://github.com/user-attachments/assets/51121af6-7e4f-4ce3-bd34-b74aee213f41)
