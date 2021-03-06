# ZMQ Connection Between Python and Unity

## Unity Respond, Python Request

### Execute

Under `UnityResponder`, start game mode of `demo.unity`, then run `request.py`

Lighting on the sphere will flash with 1 second interval, according to the command "on" or "off" sent from the Python script `request.py`. Unity will send back the current state of the light, which `request.py` will print.

## Unity Request, Python Respond

### Execute

Under `UnityRequester`, run `respond.py`, then start game mode of `demo.unity`

After typing into the input field and hitting enter, the message will be sent to `respond.py` and unity will wait for a response for 3 seconds. If there is a response, it will be printed to console. 

Commands that the responder takes:

- ping: Reply "ping back from server"

- gib [object]: Spawns [object] in scene. Currently supports "sphere" and "cube"

- sendJSON: Sends a random JSON to be parsed by Python responder

- receiveJSON: Request and parse a random JSON from Python responder

The requester is run asynchronously so the UI won't be blocked.

## Note

For  `System.Threading.Tasks` to be accessible, set editor to .NET 4.6

`File -> Build Settings -> Player Settings... -> Other Settings -> Scripting Runtime Version -> Experimental (.NET 4.6 Equivalent)`

