title: Utveckling & teknik
output: docs/index.html
controls: false
style: styles.css
--
<!-- theme: sudodoki/reveal-cleaver-theme -->
# Utveckling & teknik
## Snillen spekulerar om Låntagar-APIer och annat utvecklarrelaterat
Lari Kovanen  
Martin Ericsson 
--
### Vilka steg behövs.
1. Patrongroup
1. Skapa en user
1. Skapa Permissions
1. Skapa RequestPreference
1. ID-block?
1. Sätt pinkod/lösenord

--
### Skapa användaren
Posta till  `/users`
```json
{
    "username": "string",
    "externalSystemId": "string",
    "active": true,
    "personal": {
        "firstName": "string",
        "lastName": "string",
        "email": "string",
        "preferedContactTypeId": "002"
    },
    "barcode":"string",
    "patronGroup":"GUID"
}
```
--
### Skapa rättighegter för användaren
/perms/users  
```json
{
    "userId": "GUID",
    "permissions": []
}
```
--
### Skapa beställarpreferens
/request-preference-storage/request-preference  
```json
{
    "userId": "GUID",
    "holdShelf": true,
    "delivery": false
}
```
--
### Skapa ID-block
/manualblocks  
```json
{
    "userId": "GUID",
    "type": "Manual",
    "desc": "Nyskapat konto. ID-koll!!",
    "staffInformation": "Info som personal behöver.",
    "patronMessage": "Eventuell info till användaren. Visa ID.",
    "borrowing": true,
    "renewals": false,
    "requests": false
}
```
--
### Skapa pin/lösenord
/patron-pin  
```json
{
    "id": "GUID",
    "pin": "pin/lösenord"
}
```