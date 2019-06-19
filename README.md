# QLS-Server

## CREW 

| Name | Role |
|------|------|
| Adrien Masson | **Front** |
| Ibrahima Dansoko | **Front** |
| Maxime Gouénard | **Back** |
| Yassine Fahiti | **Back** |

## LOCAL SETUP

- `npm install`
- Create **.env** file for :
```conf
  NODE_ENV=dev
  PORT=SERVER_PORT
  SUPERSECRET=secretphrase
```
- Create **MYSQL** database called `lotos`
```sql
CREATE DATABASE IF NOT EXISTS `lotos` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `lotos`;
```
- Create **database/config.json** to configure local DB connection, like this one :
```java
{
  "dev": {
    "dialect": "mysql",
    "database": "lotos",
    "port": 3306,
    "user": "YOUR_USERNAME",
    "password": "YOUR_PASSWORD"
  }
}
```
  **_Note : Heroku is handling DB connection on itself, you simply have nothing to do for deployed connection_**
- `npm start`

---
- **AUTH ENDPOINT**

| method       | endpoint              | body                                                        |  auth |
|--------------|-----------------------|-------------------------------------------------------------|-------|
| **POST**     | `/api/auth/register ` | body : { firstname, email, password, password_confirmation } | none  |
| **POST**     | `/api/auth/login`     | body : { email, password }                                  | token |

---

## DEPLOYED SERVER APP

https://qls-project.herokuapp.com/