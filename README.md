# Godot Better HTTP

A simple HTTP client for Godot 4.x.

## Usage

```gdscript
@onready var client: BetterHTTPClient = BetterHTTPClient.new(self, "https://api.mygame.com")

func do_login():
  # send POST to https://api.mygame.com/login with some JSON payload
  var resp = await (client
    .http_post("/login")
    .json({
      "username": "AzureDiamond",
      "password": "hunter2"
    })
    .send())

  if resp.status() != 200:
    return print("invalid credentials!")

  # parse response as json
  var me = await resp.json()
```
