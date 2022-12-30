# SonOff_R2_WiFi_12V_Mod
Circuit Modification to operate on 12V DC Supply


The SonOff Basic R2 is diesigned to work off an AC Supply, and switch the AC supply onto the output terminals.

However, I needed to use the switch for controlling a 12V dc supply to a couple of items within the observatory, namely;
1) Turning on an off the fan at the back of the RASA11 telescope
2) Remotely power cycling the shutter controller when it locks up, and stops communicating with the Rotator controller.
and I am sure there will be other items in the future.

I had originally found this video https://www.youtube.com/watch?v=tRd7VgM_nEI on YouTube, but it was for an earlier revision of the PCB design. I needed to dig a bit deeper and see if I could modify the PCB Rev 1.3 design for the modules I had.

I found the circuit diagram for the device on the SonOff website at the following URL;
https://sonoff.tech/wp-content/uploads/2021/07/SONOFF_BAISCR2_ETL_Security_CDR.pdf

Referring to the power circuit diagram on Page 12, I conducted the following modifications;
1) Remove the inductor L1
2) Remove the diode D3

Using a 7805 regulator I connected this as follows;
1) 7805 Input to the upstream side of the removed inductor L1 pad, '2' on illustration 1.
2) 7805 Output to the downstream side of the removed diode D3 pad, labelled 'C' on illustration 1.
3) 7805 Common to the 0V (-ve) side of the input bridge rectifer BR1, pin 2
4) 7805 Common to the 0V (-ve) side of the transformer , labelled 'P2 1',at the joint where it connects to C17 '2'

I attached the regulator to the side of the relay using hot glue, just to keep things in place to make re-assembly easier.

The sktech for the modification can be found in the repository, the image is as follows;
![Modified Sketch](https://github.com/Daves-Astrophotography/SonOff_R2_WiFi_12V_Mod/blob/b2c2fb2e19f35f5d101e750a9779d58ee383753f/SonOff%20Basic%20R2%2012V%20DC%20Modification.png)
