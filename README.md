# Wiegand 26 and Wiegand 34 module for Node.js and using on Raspberry Pi
The Wiegand interface is a de facto standard commonly used to connect a card reader or keypad to an electronic entry system. 
Wiegand interface has the ability to transmit signal over long distance with a simple 3 wires connection. 
This module uses interrupt pins from Raspberry Pi to read the pulses from Wiegand interface and return the code and type of the Wiegand.

## Installation 

	npm install wiegand-node
    
### Example
<pre><code>
"use strict";

const Wiegand = require('wiegand-node');

var pinD0 = 4,  //DATA0 of Wiegand connects to RPi GPIO04 (Pin 7)
    pinD1 = 17; //DATA1 of Wiegand connects to RPi GPIO17 (Pin 11)

const w = new Wiegand({ d0: pinD0, d1: pinD1 });
w.begin();
w.on('reader', (idDec, idRFID, idHex) => {
  console.log(idDec); // RAW data
  
  console.log(idRFID); // EM format
  
  console.log(idHex); // Mifare format
});

</code></pre>

## Credits

