# SID Concerto

SID Concerto is a dual SID board for the Commodore 64. It features bank and page selection headers for SID2, dual built-in preamps identical to those inside the C64 so line-out audio output can be used directly from the board and a built-in SwinSID (SID emulation) for SID2 in case you don't have a second SID chip.

### Warning!
This device has **no** voltage regulation, so you can **only** use the type of SIDs for which the motherboard is intended. Vdd voltage on pin 28 is taken directly from the motherboard to pin 28 on both sockets. Disregarding this may **destroy** your SID chips!

## Addressing

##### For normal $DExx/DFxx/D4xx/D7xx addressing:

- Remove all jumpers from the "Page select" header.
- Set the jumper to "Standard pages" on the CS header.
- Put one jumper on the "Block select" header for the block you wish to use. Most 2SID songs use $D420 for SID2, for this, use the "Dx20" setting.

- For $DExx, connect PAGE IN to expansion port pin 7.
- For $DFxx, connect PAGE IN to expansion port pin 10.
- For $D7xx, put one jumper at D7xx on the "Page select" header.
- For $D4xx, put one jumper to short PAGE IN and D4xx on the "Address lines" header

##### If some other page is needed

- Set the jumper to "Additional pages" on the CS header.
- Connect A8/A9/A10 on the "Address lines" header to the equivalent ones on the CPU.
- Connect VIC IN as folows:
 *C64 Rev. A-D: U15 (74LS239) pin 4*
 *C64C Rev. E: U8 (Super PLA) pin 40*
 *C128/C128-DCR: U11 (8721 PLA) pin 42*

- Connect VIC OUT as follows:
 *C64 Rev. A-D: U19 pin 10*
 *C64C Rev. E: U7 pin 10*
 *C128: U21 pin 13*
 *C128-DCR: U11 (8721 PLA) pin 42*

*The VIC pins need to be connected to the chip but need to be insulated from the motherboard socket. An extra socket is recommended so you don't need to bend the fragile pins on the VIC chip itself.*

- Put one jumper on the desired page on the "Page select" header

##### If an address other than $Dx00 (in the selected page) is needed

- Connect all jumpers and wires as described above first to select the desired page.
- Connect A5/A6/A7 on the "Address lines" header to the equivalent ones on the CPU.
- Move the jumper on the "Block select" header to the desired block.


##### CPU locations
C64 Rev. A-D: 6510 at U7
C64 Rev. E: 8580 at U6
C128/C128-DCR: 8502 at U6

Other jumpers:

- The SID2 Filters jumpers select which filter capacitors will be used for the two SIDs (6581/8580). Set them to the left position for 6581 or to the right position for 8580.
- The SID/SwinSID jumper selects which audio is routed to the line output on the board for SID2. Both the socket and SwinSID are playing simultaneously, but only one can be routed at a time to the output.
- The SwinSID mode jumper selects what characteristics the SwinSID should emulate. Close it for 6581 or open it for 8580.
- The EXT_In to GND jumpers (vertical) simply connect the chip's EXT_In pin (26) to ground. Some prefer this to reduce noise. The left one is for SID1 and the right one is for SID2.
- The Volume limiter jumpers (vertical) limit the volume of each chip. This may be required if the audio is too loud or distorted. The left one is for SID1 and the right one is for SID2.
- The sideways audio header is a line-level audio output. SID1 at the top pin, SID2 at the bottom pin and ground on the middle pin.

Do **NOT** change the jumper settings while the machine is on. Take the necessary precautions as to not expose the delicate SID chips (or the rest of the machine, for that matter) to electrostatic discharge (ESD).

This board is derrived from [Vanessa Dannenberg's "Internal Stereo SID board"](http://daconcepts.com/vanessa/hobbies/projects.html). Thank you, Vanessa!

Lastly, I am not responsible if this device in any way damages your other equipment. Also, I have not tested wether this board fits in all C64/C128 models. You may have to build a relocation device using a ribbon cable. It should however fit in most C64 models.
