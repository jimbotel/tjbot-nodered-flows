# tjbot-nodered-flows
Contains node-red flows created to show Watson services to students using TJBot


## Bienvenida (welcome)
 
This flow is automatically executed once when node-red starts. It checks the hostname of the raspberry and it synthesizes an audio message giving this information. It also checks the main IP address and plays it back. For this second task, another flow (Dime IP) is invoked. This way we show the concept of "wiring flows" ("link" node). 

For example, if the student TJBot's hostname is "equipotj01" and the IP address is 192.168.1.105, the audio played will be:

&nbsp;&nbsp;&nbsp;"soy el equipo 1. Mi dirección IP de wifi es 192.168.1.105"

The idea is that TJBot can be setup in a "headless" way, with no attached display to the raspberry. With this setup, TJBot will connect to a pre-defined wireless network and the student will connect to it from a PC or laptop using VNC Viewer. In order to do that, they need to know the IP address assigned to TJBot, and that's where these two flows help.

The flow also shows an example of how to invoke shell commands and gather the standard output, standard error and the return code.

Flow dependencies:
* [espeak](http://espeak.sourceforge.net/): It can be installed from the command line doing a "sudo apt-get install espeak". It is a completely synthetic voice, it doesn't sound natural but it provides "local" text-to-speech services (not dependent on internet connection and/or IBM cloud service).
* A variant using aplay (see [aplay(1) - Linux man page](https://linux.die.net/man/1/aplay) ) to reproduce a pre-recorded audio file is also shown at the bottom.

<img src="images/01.bienvenida.jpg" width="100%">

## Dime IP (give my IP)

The purpose of this flow is explained above. The flow is designed so that the audio message reporting the IP address can be repeated several times (by default it is only played once) to help the student taking note of the IP address. This introduces the use of variables and the "for loop" in JavaScript. 

<img src="images/02.dime.ip.jpg" width="100%">

Flow dependencies:
* [espeak](http://espeak.sourceforge.net/)(see above)

## Mover brazo (move arm)

This flow shows how to move TJBot's arm (servomotor). In this and other flows we use Jean Carl TJBot's nodes (see "dependencies" section). They are very robust and easy to use. 
The flow can be activated manually using the "inject" node, or it can also be accessed via web (ex: http://127.0.0.1:1880/mueve ). This introduces the "http in", "template" and "http response" nodes with a very simple example.

<img src="images/03.mover.brazo.jpg" width="100%">

Flow dependencies:
* [Jean Carl's node-red-contrib-tjbot](https://github.com/jeancarl/node-red-contrib-tjbot): node "tjbot-wave"


## S. Hawking

This flow is a test bench to play with command invocation using espeak to synthesize speech and aplay to reproduce audio files.

It also shows options to reproduce audio to a USB speaker or a bluetooth one.

<img src="images/05.s.hawking.jpg" width="100%">

Flow dependencies:
* [espeak](http://espeak.sourceforge.net/)(see above)

## Loro (parrot)

This flow uses Speech to Text to convert audio input captured from the microphone into text, and then it plays this text back through the speaker using Text to Speech. The flow introduces a feedback mechanism to stop "listening" once some text has been recognized. 

Flow dependencies:
* [Jean Carl's node-red-contrib-tjbot](https://github.com/jeancarl/node-red-contrib-tjbot): nodes "tjbot-listen" and "tjbot-speak"

<img src="images/06.loro.jpg" width="100%">

## LED test 

This flow 

Flow dependencies:
* [Jean Carl's node-red-contrib-tjbot](https://github.com/jeancarl/node-red-contrib-tjbot): nodes "tjbot-listen" and "tjbot-speak"

<img src="images/07.led.test.jpg" width="100%">

## LED voz (LED controlled via voice) 

This flow 

<img src="images/08.led.voz.jpg" width="100%">

## Reconocimiento de imagen (image recognition) 

This flow 

<img src="images/09.reco.imagen.jpg" width="100%">

## Hacer una foto (take a photo)

This flow 

<img src="images/10.hacer.foto.jpg" width="100%">

## Conversación (conversation)

This flow 

<img src="images/12.conversa.jpg" width="100%">



**Item 1** This is item 1

**Item 2:** 

* [Link to my ibm web page](https://www.ibm.com)


