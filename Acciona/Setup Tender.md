

## Before set up 
visit https://dev.gpt-project.acciona.com.au/
enter account to get idToken
with sample acount:  phong.buiduy@enouvo.com | Password@123
## Step 1 
run
```
docker compose up api
docker compose up init-db
```
## Step 2 
use DataGrip(Or any DataSource Management)
Connect to Docker Sql Server with specs:
```
datasource: Sql Server
host: localhost
port: 1433
user: sa
password: Acciona@1234
database name: ai-project-automation-api
```
## Step 3
Using Query to modify Context Data
```sql
update dbo.Context set KendraIndexID = '50b79eda-c968-474d-a41a-1e430ffb5d1d'
  update dbo.Context set LinkedSiteProjectName = 'AIProjectWHT'
```
Double-check with 
```sql
Select * from Context
```

## Step 4
Back to IDE's Terminal run
```zsh
make install
make dev
```
## Step 5
Using Postman to test API `/chat`
```
http://localhost:8000/chat
Method: Post```
```Authorization: Bearer Token - <Your idToken>
	Header: context-uid - <UID in Context Table from Database>
	--data '{ "question" : "What are the Witness Points the contractor must observe for Shotcrete activity." }'
```
Expected Response:
![[Pasted image 20241210153906.png]]
