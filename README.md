# Inspiravit for flute, trumpet, violin and live electronics - live electronics MaxMSP patch 

## Overview

This Max/MSP patch is designed for live electronics performance. It processes three incoming audio signals and distributes them across a quadraphonic sound system (4 outputs). The system includes a chain of effects such as Delay, Reverb, Pitch Shifting (via Faust), and Saturation/Detune, all controllable via a MIDI interface.

## Requirements

* **Software:** Max 8 (or newer).
* **Dependencies:** `faustgen~` external (Must be installed via the Max Package Manager to run the pitch shifter).
* **Hardware:**
* Audio Interface with at least **3 inputs** and **4 outputs**.
* MIDI Controller: for example **Korg nanoKONTROL2** (configured for standard slider/knob CCs).



## Audio I/O Configuration

* **Inputs (ADC):**
* **In 1-3:** Live Audio Sources (Microphones or Instruments).


* **Outputs (DAC):**
* 
**Out 1 & 2:** Front Left / Front Right.

* 
**Out 3 & 4:** Rear Left / Rear Right.

## Features & Modules

### 1. Input Stage

* 
**Gain Control:** Individual input gain faders for channels 1, 2, and 3.

* 
**Panning:** Dedicated panning logic for positioning input sources within the sound field.


### 2. Effects Processing

The patch features several parallel processing modules controllable via the UI or MIDI:

* **Pitch Shifter:** Utilizes `faustgen~` (stdfaust.lib) for high-quality real-time pitch shifting.
* 
*Controls:* Shift (+/- 12 semitones), Window size, and Crossfade.




* 
**Delay:** Adjustable feedback/balance and buffer size.


* 
**Reverb:** Controls for reverb time and wet/dry balance.


* 
**Saturation / Detune:** Adds harmonic content and detuning effects (power in cents).



### 3. Mixing & Routing

* 
**Matrix Routing:** A routing matrix allowing flexible distribution of signals between the Front and Rear speakers.


* 
**Visual Feedback:** Level meters (`meter~`, `levelmeter~`) provided for all inputs and outputs.



## MIDI Control

The patch is pre-configured for the **Korg nanoKONTROL2**.

* 
**CC Mapping:** Control Change messages (CC 16-31) are routed to faders and knobs to control gains, effect parameters, and sends.



## Usage

1. **Install Dependencies:** Ensure the `faustgen~` package is installed in Max.
2. **Audio Setup:** Configure your Audio Status to use a 4-channel output device.
3. **Start:** Turn on the DSP (Audio) using the `ADC ON` toggle.
4. **Performance:** Use the MIDI controller or on-screen `live.sliders` to manipulate effects in real-time (you can change CC in `p midi` subpatch.
