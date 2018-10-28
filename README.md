# MCUUID
Getting Minecraft Player Information from Mojang API.

## Usage
1. `pip install mcuuid` OR add the mcuuid.py file to your Python path.
2. Use the module like this:

```
from mcuuid import GetPlayerData

player = GetPlayerData(username)

if player.valid is True:
    uuid = player.uuid
    name = player.username
```

Read `test.py` for some explaination.

When `username = "gronkh"`:
`uuid` will be `"a2080281c2784181b961d99ed2f3347c"`
and `name` will be `"Gronkh"`

## Test file
Usage
```
$ python test.py gronkh
```
or
```
$ python test.py
Please enter a username:
gronkh
```

Response:
```
UUID: a2080281c2784181b961d99ed2f3347c
correct name: Gronkh
```

## License
This software is licensed under the MIT license. Feel free to use it however you like.
