# slyt-connect
## Slytter connection interface
An idea for a node.js based interface that congregates all previously slytter connection interfaces such as:
- Aviso Messenger (Closed source)
- Aviso SMS (Closed source)
- [SlytterSheets](https://github.com/neheren/url-to-sheets)
- Emailing with pre-configured smtps, and adresses.
- Basic http requests

The module exposes simple tools to easily connect different modules across servers and devices.


## Syntax:

### Messenger:
```
slytConnect.messenger.getFriends()
slytConnect.messenger.sendMessage(100, 'sker der');
```

### Sheets:
```
slytConnect.sheets.easyPush([‘Sag', ‘smag', ‘huh'])
slytConnect.sheets.get(2,3)
slytConnect.sheets.set(2,3, “noget andet")
```
### SMS:
```
slytConnect.sms.sendTo(24402011, 'nye sager’)
slytConnect.sms.recieveController = function(req, res){
	console.log(req.params.text)
}
```

### Managing credentials
All credentials and Auth API keys will be saved in creds.json 
```
{
	messenger: {	
		login: “nikolaj.sn@hotmail.com”, 
		pass: “..”
	},
	sheets: {
		auth: ".."
	}
  ....
}
```
To add / remove authentication use commandline tool:
```
slyt-connect addKey --messenger-email "...."
```
or via inline js:
```
slytConnect.addKey.messenger.email("...");

