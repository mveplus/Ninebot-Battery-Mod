# Ninebot-Battery-Mod
Ninebot ES2 External Battery mod as a Main Battery

I was gifted an ES2 scooter by a friend, which was not working and on the verge of being discarded. The scooter's history was unknown, but upon inspection, all major components seemed fine. However, it was not charging and was displaying [error codes 19 and 21](https://github.com/etransport/ninebot-docs/wiki/ES2ESC).

Initially, I disassembled and tested key components like the battery, motor controller, display, motor, and sensors. It appeared that the external battery was functional but the scooter couldn't operate solely on it. The internal battery was completely dead with no signs of life - the diagnostic LED was off. I attempted to revive it using a bypass method, but this proved unsuccessful as the battery couldn't hold any charge. Further investigation revealed that four cells in the internal battery were damaged. Lacking spare cells and a spot welder, I couldn't repair the main battery pack at that time.

Desiring to repair the scooter, I pondered the idea of utilizing the "external battery" as the "main battery" if feasible. Upon examining the main controller board, I discovered a configuration of 2+4 wires - two power wires and four control wires for supply and communication purposes. While both the external and internal batteries had dedicated components, I noticed that certain connections were shared on the Motor Control board.

To make the external battery the primary one, I needed to reroute its communication and power wires to the internal battery, while deactivating the external battery presence detection. With the assistance of detailed MCU pin-out references and some trial and error, I successfully reconfigured the scooter to operate solely on the external battery.
![Bypass links](https://github/mveplus/Ninebot-Battery-Mod/blob/master/01_External_battery_mod_bypass_connections_bottom_IMG_9827.jpeg)
![External battery RX&TX resistors](https://github/mveplus/Ninebot-Battery-Mod/blob/master/02_External_Battery_RX_TX_Resistors_IMG_9831.jpeg)
![Exteranl battery sense resistor](https://github/mveplus/Ninebot-Battery-Mod/blob/master/03_External_battery_sense_resistor_IMG_9840.jpeg)

After a successful test run in my neighborhood, I encountered error code 21 upon returning home. Suspecting a poor connection with the external battery, I modified the internal connector slightly to address the issue. Ultimately, it was discovered that the female connector of the external battery had also been damaged due to impact. After reengineering the connections, the scooter was back to normal operation.

"Disclaimer: I absolve myself of any liability or responsibility if someone lacks the necessary caution and ends up getting hurt while using the information provided. However, if you find this information helpful, feel free to express your gratitude in a more practical manner by buying me [a beer or a coffee](https://buymeacoffee.com/mveplus). Cheers to safety and fun!"
