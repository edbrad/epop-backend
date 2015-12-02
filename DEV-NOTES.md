# Development Notes

## Development Environment & Tools

- OS - Linux (Linux Mint)
- Code Editor - Visual Studio Code

## Components & Libraries

- Loopback (http://loopback.io) - Open Source Part of Stongloop
- Yeoman (http://yeoman.io) - Loopback code generator (slc)
- GIT - source control
- Gulp - Javascript Task Runner
- TypeScript Definition Manager - TSD (VSCode Node/Express Intellisense)

## Preparation

## Node Package Manger (NPM) - Global Libraries

- StrongLoop (Loopback)
```
$ npm install -g strongloop
```

- Yeoman
```
$ npm install -g yo
```

- Gulp
```
$ npm install -g gulp
```

- Typescript Definition Manager
```
$ npm install -g tsd
```

### LoopBack Web API

```
$ slc loopback

```
### GIT initialization

```

$ git init

```

### Visual Studio Code Node/Express (loopback) Intellisense support (via typscript)

```
$ tsd query node express --action install

```
## Server REST-API development

### Create Model(s)

Create models for the data entities that will be managed:

- MailOwners - USPS Mail Owner information (Name & Address)
- CRIDs - USPS Customer Registration ID's (related to Mail Owner)
- Permits - USPS Postal Permit (related to Mail Owner)
- MailerIDs - USPS Mailer Id's (related to Mail Owner)

```
$ slc loopback:model

```
### Define the Model Schemas:

Add the properties to each of the models to define the data elements:

```
$ slc loopback:property

```

`MailOwners`

Field Name 		| Type 		| Description
--- 			| --- 		| ---
`Name` 			| string 	| Mail Owner Name/Company `[required]`
`ContactName` 	| string 	| Mail Owner Contact C/O Name
`Address1`		| string	| Primary Address Line
`Address2`		| string	| Secondary Address Line
`City`			| string	| City
`State`			| string	| State Code
`Zip5`			| string	| 5-digit ZipCode
`ZipPLus4`		| string	| Zip Plus4 Code
`Phone`			| string	| Phone Number
`CREATED`		| date		| AUDIT - Date/Time created
`CREATED_BY`	| string	| AUDIT - User that created the record
`LAST_UPDATED`	| date		| AUDIT - Date/Time of last update
`UPDATED_BY`	| string	| AUDIT - User that updated the record

`CRID's`

Field Name 		| Type 		| Description
--- 			| --- 		| ---
`CRID` 			| string 	| USPS Customer Registration ID `[required]`
`MailOwnerId` 	| string 	| Related Mail Owner `(FK)`
`CREATED`		| date		| AUDIT - Date/Time created
`CREATED_BY`	| string	| AUDIT - User that created the record
`LAST_UPDATED`	| date		| AUDIT - Date/Time of last update
`UPDATED_BY`	| string	| AUDIT - User that updated the record

`Permits`

Field Name 		| Type 		| Description
--- 			| --- 		| ---
`PermitNumber` 	| string 	| USPS Permit Number `[required]`
`MailOwnerId` 	| string 	| Related Mail Owner `(FK)`
`PermitCity`	| string	| Permit City `[required]`
`PermitState`	| string	| Permit State Code `[required]`
`PermitZip5`	| string	| Permit 5-digit ZipCode `[required]`
`PermitZipPLus4`| string	| Permit Zip Plus4 Code
`CREATED`		| date		| AUDIT - Date/Time created
`CREATED_BY`	| string	| AUDIT - User that created the record
`LAST_UPDATED`	| date		| AUDIT - Date/Time of last update
`UPDATED_BY`	| string	| AUDIT - User that updated the record

`MailerID's`

Field Name 		| Type 		| Description
--- 			| --- 		| ---
`MailerID` 		| string 	| USPS Mailer ID (6 or 9 Digits) `[required]`
`MailOwnerId` 	| string 	| Related Mail Owner `(FK)`
`MailerName` 			| string 	| Mailer Name/Company `[required]`
`MailerContactName` 	| string 	| Mailer Contact C/O Name
`MailerAddress1`		| string	| Mailer Primary Address Line
`MailerAddress2`		| string	| Mailer Secondary Address Line
`MailerCity`			| string	| Mailer City
`MailerState`			| string	| Mailer State Code
`MailerZip5`			| string	| Mailer 5-digit ZipCode
`MailerZipPLus4`		| string	| Mailer Zip Plus4 Code
`MailerPhone`			| string	| Mailer Phone Number
`CREATED`		| date		| AUDIT - Date/Time created
`CREATED_BY`	| string	| AUDIT - User that created the record
`LAST_UPDATED`	| date		| AUDIT - Date/Time of last update
`UPDATED_BY`	| string	| AUDIT - User that updated the record