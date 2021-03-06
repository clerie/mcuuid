# MCUUID
Getting Minecraft Player Information from Mojang API.

## Usage
1. `pip install mcuuid`
2. Use the module like this:

### API
```
from mcuuid.api import GetPlayerData

player = GetPlayerData(identifier)

if player.valid is True:
    uuid = player.uuid
    name = player.username
```

Identifier can be a username or a UUID.

When `identifier = "gronkh"`:
`uuid` will be `"a2080281c2784181b961d99ed2f3347c"`
and `name` will be `"Gronkh"`


```
player = GetPlayerData(identifier, timestamp)
```

Some names are time-sensitive. (When they are changed)
So you can choose a special time.

It even works with UUIDs. They respond the username at the given time.

### Tools
Syntax check of username
```
from mcuuid.tools import is_valid_minecraft_username

if is_valid_minecraft_username('gronkh'):
  print('Valid')
```

Syntaxcheck of UUID
```
from mcuuid.tools import is_valid_mojang_uuid

if is_valid_mojang_uuid('a2080281c2784181b961d99ed2f3347c'):
  print('Valid')
```

## Documentation
### Module `mcuuid.api`
#### Class `GetPlayerData(indentifier, timestamp=None)`
##### Parameters
- `identifier`: string - a Minecraft username or Mojang UUID
- `timestamp`: int - a unix timestamp

##### Returns
`player` object

#### Object `player`
##### Value `player.uuid`
Mojang UUID

##### Value `player.username`
Minecraft username

### Module `mcuuid.tools`
#### Function `is_valid_minecraft_username(username)`
##### Parameters
- `username`: string - a Minecraft username

##### Returns
`True` or `False`

#### Function `is_valid_mojang_uuid(uuid)`
##### Parameters
- `uuid`: string - a Mojang UUID

##### Returns
`True` or `False`

#### Function `cleanup_uuid(uuid)`
##### Parameters
- `uuid`: string - a Mojang UUID

##### Returns
`uuid` as string, lowered. Without dashes

## Test file
Usage
```
$ python test.py gronkh
```
or
```
$ python test.py a2080281c2784181b961d99ed2f3347c
```
or
```
$ python test.py
Please enter a username or UUID:
gronkh
```
or
```
$ python test.py
Please enter a username or UUID:
a2080281c2784181b961d99ed2f3347c
```

Response:
```
UUID: a2080281c2784181b961d99ed2f3347c
correct name: Gronkh
```

## License
This software is licensed under the MIT license. Feel free to use it however you like.
