# Personal Notes

Nothing contained here is recommended.  It's just a collection of personal notes about some temporary lash-up situations.



## MUX 2x Super Hybrid DPT+SLT to/from single Cat5e

This is a quick fix for situations where there is not enough existing Cat5 structured cabling infrastructure, e.g. in my house, I have to squeeze (mux) 3 DPTs and 5 SLTs through just two Cat5 wall ports.  The patch panel under the stairs is unpowered.  I de-mux them there to wall ports around the rest of building.

|    Cat5e     | RJ45 Pin | Hybrid Port 1 | Hybrid Port 2 |
| :----------: | :------: | :-----------: | :-----------: |
| Orange/White |    1     |               |   Green - 5   |
|    Orange    |    2     |               |   Red  - 4    |
| Green/White  |    3     |   Black - 3   |               |
|     Blue     |    4     |   Red  - 4    |               |
|  Blue/White  |    5     |   Green - 5   |               |
|    Green     |    6     |  Yellow - 6   |               |
| Brown/White  |    7     |               |   Black - 3   |
|    Brown     |    8     |               |  Yellow - 6   |

## MUX 1x Super Hybrid DPT+SLT, plus 2x SLT to/from single Cat5e

| Cat5e TIA568B | RJ45 Pin |   Hybrid Port   |   SLT Port1   |  SLT Port 2   |
| :-----------: | :------: | :-------------: | :-----------: | :-----------: |
| Orange/White  |    1     |                 | Green - 5 - A |               |
|    Orange     |    2     |                 |  Red - 4 - B  |               |
|  Green/White  |    3     | Black - 3 - D2  |               |               |
|     Blue      |    4     |  Red  - 4 - B   |               |               |
|  Blue/White   |    5     |  Green - 5 - A  |               |               |
|     Green     |    6     | Yellow - 6 - D1 |               |               |
|  Brown/White  |    7     |                 |               | Green - 5 - A |
|     Brown     |    8     |                 |               |  Red - 4 - B  |

## TDA30 - Music on Hold 

Module GPD2846A is perfect for this.  It auto-starts upon the application of power, and plays ad infinitum.  It is  very loud.  You will have to limit the output.  I used a 10K potentiometer to do this.  It requires a micro SD card and a soldered 5v power supply.

## Asterisk - Speaking Clock (TIM) - 123

This is an absolute must: https://github.com/paulseward/asterisk-tim 