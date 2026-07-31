# VoLTE Retrofit Project Spanaway Hardware
## Overview
This device, when finished, will act as the first piece of reference hardware for the VRP project. The device should be easily debuggable and handsolderable.


## Hardware Overview
The device is a two PCB design with "front board" containg the interface, MCU, and audio circuity. The "rear board" will handle power and modem. Both boards will interface via two 8 pin dupont headers. An alphanumeric tranflective display and a matrix of tactile 6mm push buttons will act a the primary user interface. The device will continue to use a mini-pcie form factor modem. All audio will be routed through an I2S codec and a mux will be used to switch sources (between the MCU or Modem). 3 AA sized NiMH batteries mounted on the rear board will power everything.


```

FRONT BOARD
	OVERVIEW
		Userfacing hardware like the display and button matrix along with the primary MCU and audio will be handled by this top board.	
	MAJOR COMPONENTS
		MICRCONTROLLER: ATASAMD21G18
		CODEC: TLV320AIC3104
		KEYPAD: disrcete micro switch buttons
		HEADPHONE JACK:
		MICROPHONE: CUI CMA-4544PF-W
		BUZZER: CUI
		INTEGRATED MICROPHONE:
		SPEAKER AMPLIFIER: TPA6203A1
		SD CARD HOLDER: MOLEX
		I2S MUX:
			
REAR BOARD

	MAJOR COMPONENTS
		MINI PCIE CONNECTOR:
		MODEM:
		SIM TRAY:
		3.3V LDO:
		1.8V LDO:
		3V LDO:	
		NIMH CHARGE CONTROLLER:






```


## Revisions
