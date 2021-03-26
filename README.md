# skribbl.io-reverse-engineering

# WebSocket
Skribbl.io has a main game websocket running on Socket.io

# Commands

## KeepAlive
Client sends a packet of type 2 and receives a packet of type 3.

## Type 4
Type 4 is used for all of the actual game messages consisting of data in the format
[commandName, ...args]

### drawCommands (in+out)
cmd: "drawCommands"
args: [DrawCommand]

#### Type: DrawCommand
pen: `[0,colour,size,x1,y1,x2,y2]`
  
erasor: `[1,size,x1,y1,x2,y2]`
  
fill: `[2, colour, x, y]`

Where colours
`{'0': '#ffffff', '1': '#000000', '2': '#c1c1c1', '3': '#4c4c4c', '4': '#ef130b', '5': '#740b07', '6': '#ff7100', '7': '#c23800', '8': '#ffe400', '9': '#e8a200', '10': '#00cc00', '11': '#005510', '12': '#00b2ff', '13': '#00569e', '14': '#231fd3', '15': '#0e0865', '16': '#a300ba', '17': '#550069', '18': '#d37caa', '19': '#a75574', '20': '#a0522d', '21': '#63300d'}`

coordinates (left to right, top to bottom)

x = 0..800

y = 0..600

(can draw at negative or above, but isnt seen)

size: pixels

