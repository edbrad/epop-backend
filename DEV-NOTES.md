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
## Server REST-api development

### Create Model(s)

Create models for the data entities that will be managed:

- MailOwners - USPS Mail Owner information (Name & Address)
- CRIDs - USPS Customer Registration ID's (related to Mail Owner)
- Permits - USPS Postal Permit (related to Mail Owner)
- MailerIds - USPS Mailer Id's (related to Mail Owner)

```
$ slc loopback:model

```
