# VoLTE Retrofit Project Spanaway Hardware
## Overview
This device, when finished, will act as the first piece of reference hardware for the VRP project. The device should be easily debuggable and handsolderable.


## Hardware Overview
The device is a two PCB design with "front board" containg the interface, MCU, and audio circuity. The "rear board" will handle power and modem. Both boards will interface via two 8 pin dupont headers. An alphanumeric tranflective display and a matrix of tactile 6mm push buttons will act a the primary user interface. The device will continue to use a mini-pcie form factor modem. All audio will be routed through an I2S codec and a mux will be used to switch sources (between the MCU or Modem). A single cell Li-Ion battery will power everything.

## Detailed Hardware Documentation
### Audio
The Spanaway phone uses a TI TLV320AIC3104 audio codec. This codec supports I2S, has integrated pre-amps and a headphone power amplifier making it well suited for this application. A TI SN74CB3Q3257 is used to select which I2S device the codec communicates with, the choices being the MCU or the Modem. When not in a call, `VOICE/MEDIA` is pulled low selecting the MCU, durin a call this pin is pulled high selecting the codec. The MCU controls the coded via I2C selecting which inputs and outputs to use, this behaviour is defined on a per state basis.

#### `DEVICE_STATE_IDLE`
The handset is at "rest" during `DEVICE_STATE_IDLE`, all audio inputs and outputs are unsused/muted.
- MCU is selected (VOICE/MEDIA is low)

#### `DEVICE_STATE_MEDIA`
- MCU is selected (VOICE/MEDIA is low)
- audio inputs are unused (could change if audio recording is implemented)
- audio output may be earpiece or headpones

#### `DEVICE_STATE_INCALL`
- modem is selected (VOICE/MEDIA is high)
- audio inputs may be headset or integrated mic
- audio output may be earpiece or headpones







```

FRONT BOARD
	OVERVIEW
		Userfacing hardware like the display and button matrix along with the primary MCU and audio will be handled by this top board.	
	MAJOR COMPONENTS
		MICRCONTROLLER: ATASAMD21G18
		CODEC: TLV320AIC3104
		KEYPAD: disrcete micro switch buttons
		HEADPHONE JACK: SJ3-35094BG
		MICROPHONE: CMB-6544PF
		EAR PIECE SPEAKER: AST-01508MR-R
		BUZZER: CUI
		SPEAKER AMPLIFIER: TPA6203A1
		SD CARD HOLDER: MOLEX
		I2S MUX: SN74CB3Q3257
			
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
