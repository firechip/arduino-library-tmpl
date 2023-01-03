
**Firechip - Analog Devices MAX14521E Arduino Library**

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
[![PlatformIO Registry](https://badges.registry.platformio.org/packages/firechip/library/FC0001614614.svg)](https://registry.platformio.org/libraries/firechip/FC0001614614)
[![Check Arduino](https://github.com/firechip/Firechip_Analog_Devices_MAX14521E_Arduino_Library/actions/workflows/check-arduino.yml/badge.svg)](https://github.com/firechip/Firechip_Analog_Devices_MAX14521E_Arduino_Library/actions/workflows/check-arduino.yml)

The MAX14521E is a quad-output high-voltage DC-AC converter that drives four electroluminescent (EL) lamps. The device features a 2.7V to 5.5V input range that allows the device to accept a variety of voltage sources such as single-cell lithium-ion (Li+) batteries. The lamp outputs of the device generate up to 300VP-P for maximum lamp brightness. The high-voltage outputs are ESD protected up to ±15kV Human Body Model (HBM), ±6kV Contact Discharge, and ±8kV Air Gap Discharge, as specified in IEC 61000-4-2.

The  MAX14521E  uses  a  high-voltage  full-bridge  output stage  to  convert  the  high  voltage  generated  by  the boost  converter  to  a  sinusoidal  output  waveform.  The MAX14521E  utilizes  a high-frequency  spread-spectrum oscillator to reduce the amount of EMI/EFI generated by the boost-converter circuit.

The  MAX14521E  provides  an  I2C  interface  to  set  the boost  converter  and  EL  output  switching  frequencies through an 8-bit register and the peak output voltages with 5 bits of resolution. The MAX14521E also provides an  adjustable  automatic  ramping  feature  that  slowly increases or decreases the peak output voltage when a change is made to the output amplitude. The slew rate of the automatic ramp is set with 3 bits of resolution through 

the I2C interface and it is independent for each channel. The MAX14521E features an audio auxiliary input AUX that modulates the EL output voltage and frequency for dynamic lighting effects.

The MAX14521E is available in a small, 4mm x 4mm, 24-pin TQFN package, and specified over the extended -40°C to +85°C operating temperature range

**Applications**

- Keypad Backlighting
- LCD Backlighting
- PDAs
- Smartphones

**Benefits and Features**

- Integration Reduces Required Board Space
  - Integrated ±15kV ESD Protection
  - Low Number of Needed Discrete Components
  - 4mm x 4mm, 24-Pin TQFN Package
- Enhances Lamp Performance
- 300VP-P Maximum Output for Highest Brightness
- ±3% EL Output Frequency Accuracy for Truest EL Panel Color
- Individually Adjustable Output Brightness Ramping Rate and Individual Dimming Control
- Audio Input for Dynamic Lighting Effects
- I2C Interface for Control of Brightness, EL Fre- quency, Boost Frequency, Shape
- Eases System Integration
  - Sinusoidal Output for Low Audible Noise
  - High-Frequency Spread-Spectrum Oscillator Reduces EMI/EFI Generation
- Ideal for Battery-Powered Devices
- 100nA Shutdown Current
- 2.7V to 5.5V Input Voltage Range


The MAX14521E is a quad-output high-voltage DC-AC converter that drives four EL lamps. The device features a 2.7V to 5.5V input range that allows the device to accept a variety of sources such as single-cell Li+ batteries. The lamp outputs of the device generate up to 300VP-P for maximum lamp brightness.

The MAX14521E utilizes a high-frequency spread-spec- trum boost converter that reduces the amount of EMI/EFI generated by the circuit. The boost-converter switching frequency is set with an 8-bit register through the I2C interface. The MAX14521E uses a high-voltage full-bridge output stage to convert the high voltage generated by the boost converter to an AC waveform suitable for driving an EL lamp. An internal register controlled through the I2C interface sets the shape of the EL output waveshape.

The  EL  output  switching  frequency  for  all  outputs  is set with an 8-bit register through the I2C interface. The MAX14521E provides a serial digital interface that allows the user to set the peak voltage of each output independently with 5 bits of resolution. The MAX14521E also pro- vides an adjustable automatic ramping feature that slowly increases or decreases the peak output voltage when the set value is changed. The slew rate of the ramp is set with 3 bits of resolution through the I2C interface and it is independent for each channel. The MAX14521E features an audio auxiliary input AUX that modulates the EL output voltage and frequency for dynamic lighting effects.

The high-voltage outputs are ESD protected up to ±15kV Human Body Model, ±8kV Air Gap Discharge, and ±6kV Contact Discharge, as specified in IEC 61000-4-2.

**EL Output Voltage**

The  shape,  slope,  frequency,  ramp-on/-off  times,  and peak-to-peak voltage of the MAX14521E lamp outputs are programmed using internal registers.

The MAX14521E is capable of producing output waveforms with varying shapes and slew rates. The user sets the shape and slew rate of the output using bits in the EL shape registers.

The  MAX14521E  EL  lamp  output  frequency  uses  an internal EL oscillator to set the desired frequency. The 

output frequency is adjusted by the FEL[7:0] bits of the EL output frequency register. The EL frequency increases and decreases linearly with FEL[7:0].

The peak-to-peak voltage of the EL lamp output is varied from 0 to 300VP-P by programming the EL\_ \_[4:0] bits of the EL ramping time and EL peak voltage registers. The peak-to-peak voltage increases and decreases linearly with EL\_ \_[4:0].

The MAX14521E also features a slow fade-on and slow fade-off time feature programmed by the RT\_ \_ [2:0] bits of the EL ramping time and EL peak voltage registers. This slow fade-on/-off feature causes the peak-to peak voltage of the EL outputs to slowly rise from the previously set value to the maximum set value. This feature also causes the peak-to-peak voltage of the EL outputs to fall from the maximum set value to zero when the device is placed into shutdown. The slow rise and fall of the peak- to-peak  EL  output  voltage  creates  a  soft  fade-on  and fade-off of the EL lamp.

**Boost Converter**

The MAX14521E boost converter consists of an external- tapped inductor from VDD to the LX input, an internal DMOS switch, an external diode from the secondary of the tapped inductor to the CS output, an external capacitor from the CS output to GND, and an EL lamp connected to the EL lamp outputs. When the DMOS switch is turned on, LX is connected to GND, and the inductor is charged. When the DMOS switch is turned off, the energy stored in the inductor is transferred to the capacitor CCS and the EL lamp.

**Note:** The MAX14521E exhibits high-voltage spikes on the LX node. The addition of a snubber circuit to the LX node protects the device by suppressing the high-voltage spikes. The values of RSN and CSN should be optimized for the specific tapped inductor used. Typical values are RSN = 20Ω and CSN = 330pF.

The MAX14521E boost-converter frequency uses an inter- nal oscillator to set the frequency of the boost converter. The oscillator frequency is adjusted by the FSW[4:0] bits of the boost-converter frequency register. The boost con- verter increases and decreases linearly with FSW[3:0].

To further reduce the amount of EMI/EFI generated by the circuit,  the  boost-converter  frequency  can  be  modulated (see the SS[1:0] bits of the boost-converter frequency reg- ister). Enabling modulation spreads the switching energy of the oscillator in the frequency domain, thus decreasing EMI.

**Independent Dimming Control**

The brightness of an EL lamp is proportional to the peak- to-peak voltage applied across the lamp. The MAX14521E provides four registers to control the EL peak-to-peak volt- age of each EL output using the EL\_ \_[4:0] bits of the EL ramping time and EL peak voltage registers.

**EL Output Waveshape**

The MAX14521E can produce sine-wave to square-wave waveshapes on the EL output by varying the slope of the EL output. This is achieved by using bits SL[1:0] of the EL shape register. If the EL shape configuration is set to sine and if all EL outputs have the same amplitude settings, then each EL output has a sinusoidal waveshape. If the EL outputs have different amplitude settings, then the EL output with the highest setting has a sine waveshape while the remaining EL outputs have a clamped sine waveshape.

**Auxiliary Audio Input (AUX)**

The MAX14521E uses an auxiliary input AUX that accepts an audio signal to produce visual effects on the EL out- puts. The frequency and amplitude modulation (FR\_AM) bit is set to modulate the EL output voltage or frequency. The AUX audio signal modulates the EL output voltage when FR\_AM is set to 0 and modulates the EL output frequency when FR\_AM is set to 1.

When  the  NO\_SAMPLE  bit  is  enabled,  the  voltage  of the EL outputs is proportional to the voltage at AUX. For example, when FR\_AM = 0, NO\_SAMPLE = 1, and any of the AU1, AU2, AU3, AU4 bits are set to 1, the peak value of those particular channels follow AUX directly.

If AUX is a DC value, the EL output voltage is VEL = 250 x AUX (VP-P) with a maximum of 300VP-P.

AUX can also accept a PWM signal with a frequency rang- ing from 100kHz to 10MHz, where the EL output voltage is VEL = 300 x DutyCycle% (VP-P). The NO\_SAMPLE bit has no effect when FR\_AM = 1. 

When FR\_AM = 1, frequency modulation is enabled and the AUXDIV1 and AUXDIV0 bits are used to divide the audio frequency and apply this to the EL outputs. AU1, AU2, AU3, and AU4 must be set to 1 to enable this feature.

**Shutdown**

The MAX14521E features two methods to place the device in shutdown: 1) a reset input, RB, to clear all registers to zero and put the device into low-power shutdown mode, and 2) the EN bit of the system register. Using method 1, the device does not respond to I2C communications when RB is held low. Using method 2, the EL outputs are shut down; however, the register contents remain unchanged.

**Undervoltage Lockout (UVLO)**

The MAX14521E has a UVLO threshold of +2.0V (typ). When VDD falls below +2.0V (typ), the device enters a nonoperative mode. The contents of the I2C registers are not guaranteed below UVLO.

**Thermal Protection**

The MAX14521E enters a nonoperative mode if the internal die temperature of the device reaches or exceeds +160°C (typ). The MAX14521E is latched, and only placing RB to 0 resets the thermal protection bit as well as all registers.

**I2C Registers and Bit Descriptions**

Ten  internal  registers  program  the  MAX14521E. [Table 1](#_page11_x53.00_y231.00) lists all the registers, their addresses, and power- on reset states. All registers are read/write. Register 0x0A is reserved as a command to update all EL peak voltage output registers. Register 0x0B is reserved and should not be written to.

Maxim Integrated  │ 21

**Table 1. Register Map**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|**REGISTER ADDRESS**|**POWER-ON RESET STATE**|
| - | - | - | - | - | - | - | - | - | - | :-: |
|**SYSTEM**|
|Device ID|DEVID3|DEVID2|DEVID1|DEVID0|REV3|REV2|REV1|REV0|0x00|0xB2|
|Power Mode|OVR TEMP\*|X|X|X|X|X|X|EN|0x01|0x00|
|**EL FREQUENCY**|
|EL Output Frequency|FEL7|FEL6|FEL5|FEL4|FEL3|FEL2|FEL1|FEL0|0x02|0x00|
|**EL SHAPE**|
|Slope/Shape|X|ENDAMP|X|X|SHAPE1|SHAPE0|SL1|SL0|0x03|0x00|
|**BOOST-CONVERTER FREQUENCY**|
|Boost-Converter Frequency|SS1|SS0|X|FSW4|FSW3|FSW2|FSW1|FSW0|0x04|0x00|
|**AUDIO**|
|Audio Effects|FR\_AM|NO\_ SAMPLE|AUXDIV1|AUXDIV0|AU4|AU3|AU2|AU1|0x05|0x00|
|**EL RAMPING TIME AND EL PEAK VOLTAGE**|
|EL1 Ramping Time and EL Peak Voltage\*\*|RT1\_2|RT1\_1|RT1\_0|EL1\_4|EL1\_3|EL1\_2|EL1\_1|EL1\_0|0x06|0x00|
|EL2 Ramping Time and EL Peak Voltage\*\*|RT2\_2|RT2\_1|RT2\_0|EL2\_4|EL2\_3|EL2\_2|EL2\_1|EL2\_0|0x07|0x00|
|EL3 Ramping Time and EL Peak Voltage\*\*|RT3\_2|RT3\_1|RT3\_0|EL3\_4|EL3\_3|EL3\_2|EL3\_1|EL3\_0|0x08|0x00|
|EL4 Ramping Time and EL Peak Voltage\*\*|RT4\_2|RT4\_1|RT4\_0|EL4\_4|EL4\_3|EL4\_2|EL4\_1|EL4\_0|0x09|0x00|
*X = Don’t Care \*Read back only.*

*\*\*Send command 0Ah (update all EL ramping time and EL peak voltage registers) to have the programmed voltage effectively applied to the EL lamp.*

Maxim Integrated  │ 

**Slave Address**

The MAX14521E device address is set through external inputs. The slave address consists of five fixed bits (B7– B3, set to 11110) followed by two input programmable bits (A1 and A0).

For example: If A1 and A0 are hardwired to ground, then the  complete  address  is  1111000.  The  full  address  is defined as the seven most significant bits followed by the read/write bit. Set the read/write bit to 1 to configure the MAX14521E to read mode. Set the read/write bit to 0 to configure the MAX14521E to write mode. The address is the first byte of information sent to the MAX14521E after the START condition.

**System Registers (0x00, 0x01)**

**Device ID (DEVID3/DEVID2/DEVID1/DEVID0)**

DEVID[3:0]  is  preprogrammed  to  1011  to  identify  the MAX14521E; see [Table 2](#_page12_x53.00_y446.00).

**Revision (REV3/REV2/REV1/REV0)**

REV[3:0] is preprogrammed to the current revision of the MAX14521E and is REV[3:0] = 0010.

0 = Analog circuitry operating properly.

OVRTEMP = 1 turns the EL outputs off. To set OVRTEMP to 0 and restart in default condition (all register reset), the user must place RB = 0.

**System Enable (EN)** 1 = EL outputs enabled. 0 = EL outputs disabled.

EN = 1 places the MAX14521E in a normal operating mode. Register contents are restored to values prior to shutdown. EN = 0 disables the EL outputs and places the device in a low-power shutdown state.

**EL Frequency Register (0x02) EL Frequency (FEL[7:0])**

FEL[7:6] sets the EL frequency range of all EL outputs and FEL[5:0] sets the EL frequency within the frequency range; see [Table 4](#_page12_x54.00_y604.00). FEL[5:0] = 000000 sets the frequency to the minimum value of the frequency range. FEL[5:0] = 111111 sets the frequency to the maximum value of the frequency  range.  EL  frequency  increases  linearly  with FEL[5:0]; see [Table 3](#_page12_x53.00_y541.00).

Maxim Integrated  │ 22

**System Overtemperature (OVRTEMP)**

1 = Thermal shutdown temperature exceeded.

**Table 2. Device Identification, Status, and Enable**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x00|DEVID3|DEVID2|DEVID1|DEVID0|REV3|REV2|REV1|REV0|
|0x01|OVRTEMP\*|X|X|X|X|X|X|EN|
*X = Don’t Care*

**Table 3. EL Output Frequency**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x02|FEL7|FEL6|FEL5|FEL4|FEL3|FEL2|FEL1|FEL0|
**Table 4. EL Frequency Range**

|**FEL[7:6]**|**EL FREQUENCY RANGE (Hz)**|
| - | - |
|00|50–100|
|01|100–200|
|10|200–400|
|11|400–800|

Maxim Integrated  │ 

**EL Shape Register (0x03)**

**Damping Enable (ENDAMP)**

1 = Active damping on LX node enabled. 0 = Active damping on LX node disabled.

ENDAMP = 1 actively damps the oscillation on the LX pin and could reduce EMI.

**EL Shape (SHAPE1/SHAPE0)**

SHAPE[1:0] sets the desired EL output waveform; see [Table 5](#_page13_x53.00_y358.00) and [Table 6](#_page13_x53.00_y431.00).

**EL Slew Rate (SL1/SL0)**

SL[1:0] sets the slope of the EL output; see [Table 7](#_page13_x316.00_y431.00).

**Boost-Converter Frequency Register (0x04)**

**Spread Spectrum (SS1/SS0)**

SS[1:0] sets the spread-spectrum modulation frequency to  a  fraction  of  the  boost-converter  frequency;  see [Table 8](#_page13_x53.00_y545.00) and [Table 9](#_page13_x53.00_y624.00).

**Boost-Converter Switching Frequency (FSW[4:0])**

FSW4 sets the switching frequency range of the boost converter  and  FSW[3:0]  sets  the  switching  frequency within the frequency range; see [Table 10](#_page14_x53.00_y260.00). The frequency range for FSW4 = 0 is 800kHz–1600kHz. The frequency range  for  FSW4  =  1  is  400kHz–800kHz.  FSW[3:0]  = 0000 sets the frequency to the minimum value of the fre- quency range. FSW[3:0] = 1111 sets the frequency to the maximum value of the frequency range. Boost-converter switching frequency increases linearly with FSW[3:0].

Maxim Integrated  │ 23

**Table 5. EL Shape Configuration**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x03|X|ENDAMP|X|X|SHAPE1|SHAPE0|SL1|SL0|
*X = Don’t Care*

Maxim Integrated  │ 

**Table 6. EL Output Shape Configuration**

|**SHAPE[1:0]**|**EL OUTPUT SHAPE**|
| - | - |
|0X|Sine|
|10|Do Not Use|
|11|Do Not Use|
*X = Don’t Care*

**Table 7. EL Slope Configuration**

|**SL[1:0]**|**EL OUTPUT SLOPE**|
| - | - |
|00|Sine|
|01|Fast Slope|
|10|Faster Slope|
|11|Fastest Slope (Square Wave)|


Maxim Integrated  │ 

**Table 8. Boost-Converter Configurations**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x04|SS1|SS0|X|FSW4|FSW3|FSW2|FSW1|FSW0|
*X = Don’t Care*

**Table 9. Spread-Spectrum Configuration**

|**SS[1:0]**|**SPREAD SPECTRUM**|
| - | - |
|00|Disabled|
|01|1/8|
|10|1/32|
|11|1/128|

Maxim Integrated  │ 

**Audio Input Register (0x05)**

**Frequency and Amplitude Modulation (FR\_AM)**

0 = AUX input signal modulates EL output voltage.

1 = AUX input frequency modulates EL output frequency.

**AUX Envelope on EL Output (NO\_SAMPLE)**

1  =  The  EL  output  envelope  follows  that  of  the AUX envelope.

0 = AUX is sampled every fEL cycle and the correspond- ing EL output cycle has zero DC average.

Set FR\_AM = 0 when NO\_SAMPLE = 1 and enable the corresponding EL outputs by bits AU[4:1]. If FR\_AM = 1, the NO\_SAMPLE bit has no effect. If AUX is a DC value, the EL output peak-to-peak voltage is EL\_ (VP-P) = 250 x AUX (V) with a maximum of 300VP-P. If AUX is a PWM signal with a frequency from 100kHz to 10MHz, the EL output voltage is VEL = 300 x DutyCycle% (VP-P).

Maxim Integrated  │ 24

**Table 10. Boost-Converter Frequency Range**

|**FSW3**|**FSW2**|**FSW1**|**FSW0**|**BOOST-CONVERTER SWITCHING FREQUENCY (kHz)**|
| - | - | - | - | - |
|||||**FSW4 = 0**|**FSW4 = 1**|
|0|0|0|0|800|400|
|0|0|0|1|853|427|
|0|0|1|0|907|453|
|0|0|1|1|960|480|
|0|1|0|0|1013|507|
|0|1|0|1|1067|533|
|0|1|1|0|1120|560|
|0|1|1|1|1173|587|
|1|0|0|0|1227|613|
|1|0|0|1|1280|640|
|1|0|1|0|1333|667|
|1|0|1|1|1387|693|
|1|1|0|0|1440|720|
|1|1|0|1|1493|747|
|1|1|1|0|1547|773|
|1|1|1|1|1600|800|
**Table 11. Audio Input Configurations**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x05|FR\_AM|NO\_ SAMPLE|AUXDIV1|AUXDIV0|AU4|AU3|AU2|AU1|

Maxim Integrated  │ 

**Frequency Divider (AUXDIV1/AUXDIV0)**

AUXDIV[1:0] sets the divisor to divide down the AUX input frequency; see [Table 12](#_page15_x53.00_y403.00).

**Audio Enable (AU4/AU3/AU2/AU1)** 1 = Enable audio effect to EL output. 0 = Disable audio effect to EL output.

When FR\_AM = 0 the EL outputs can be enabled and dis- abled independently according to AU[4:1]. When FR\_AM = 1 then all AU[4:1] bits must be set to 1 (i.e. AU[4:1] = 1111) to enable the audio effect on the EL outputs.

**EL Peak Ramping Time and EL Peak Voltage Register (0x06, 0x07, 0x08, 0x09)**

**EL Ramping Time** 

**(RT4\_ \_/RT3\_ \_/RT2\_ \_/RT1\_ \_)**

RT\_ \_[2:0] sets the ramp time of each EL output; see [Table 14](#_page15_x53.00_y624.00).

**EL Peak-to-Peak Voltage (EL1\_ \_/EL2\_ \_/EL3\_ \_/EL4\_ \_)**

EL \_ \_[4:0] controls the peak-to-peak voltage of each EL output. When EL \_ \_[4:0] = 00000, the EL output follows 

**Table 12. AUX Frequency Divider Configuration**



|**AUXDIV[1:0]**|**AUX FREQUENCY DIVIDER**|
| - | - |
|00|16|
|01|8|
|10|4|
|11|2|
COM. When EL\_ \_[4:0] = 11111, the EL output has a 150V peak with respect to COM. The EL output voltage rises linearly with EL\_ \_[4:0].

**I2C Interface**

The MAX14521E features an I2C-compatible as a slave device, 2-wire serial interface consisting of a serial data line (SDA) and a serial-clock line (SCL). SDA and SCL facilitate communication to the device at clock rates up to 400kHz. [Figure 1](#_page5_x68.00_y140.00) shows the 2-wire interface timing diagram. The master generates SCL and initiates data transfer on the bus. A master device writes data to the MAX14521E  by  transmitting  the  proper  slave  address followed by the register address and then the data word. Each transmit sequence is framed by a START (S) or REPEATED START (Sr) condition and a STOP (P) condi- tion. Each word transmitted to the MAX14521E is 8 bits long  and  is  followed  by  an  acknowledge  clock  pulse. A master reading data from the MAX14521E transmits data  on  SDA  in  sync  with  the  master-generated  SCL pulses. The master acknowledges receipt of each byte of data. Each read sequence is framed by a START or REPEATED START condition, a not acknowledge, and a STOP condition. SDA operates as both an input and an open-drain output. A pullup resistor, typically greater than 500Ω, is required on SCL if there are multiple masters on the bus, or if the master in a single master system has an open-drain SCL output. Series resistors in line with SDA and SCL are optional. Series resistors protect the digital inputs of the MAX14521E from high-voltage spikes on the bus lines, and minimize crosstalk and undershoot of the bus signals.

Maxim Integrated  │ 25

**Table 13. EL Output Configuration**

|**REGISTER**|**B7**|**B6**|**B5**|**B4**|**B3**|**B2**|**B1**|**B0**|
| - | - | - | - | - | - | - | - | - |
|0x06|RT1\_2|RT1\_1|RT1\_0|EL1\_4|EL1\_3|EL1\_2|EL1\_1|EL1\_0|
|0x07|RT2\_2|RT2\_1|RT2\_0|EL2\_4|EL2\_3|EL2\_2|EL2\_1|EL2\_0|
|0x08|RT3\_2|RT3\_1|RT3\_0|EL3\_4|EL3\_3|EL3\_2|EL3\_1|EL3\_0|
|0x09|RT4\_2|RT4\_1|RT4\_0|EL4\_4|EL4\_3|EL4\_2|EL4\_1|EL4\_0|
**Table 14. Ramping Time Configuration**

|**RT\_ \_[2:0]**|**RAMPING TIME (ms)**|
| - | - |
|000|< 0.1|
|001|62.5|
|010|125|
|011|250|

|**RT\_ \_[2:0]**|**RAMPING TIME (ms)**|
| - | - |
|100|500|
|101|750|
|110|1000|
|111|2000|

Maxim Integrated  │ 26

**Bit Transfer**

One data bit is transferred during each SCL cycle. The data on SDA must remain stable during the high period of the SCL pulse. Changes in SDA while SCL is high are control  signals  (see  the  *[START  and  STOP  Conditions](#_page16_x53.00_y220.00)* section). SDA and SCL idle high when the I2C bus is not busy.

**START and STOP Conditions**

SDA and SCL idle high when the bus is not in use. A mas- ter initiates communication by issuing a START condition. A START condition is a high-to-low transition on SDA with SCL high. A STOP condition is a low-to-high transition on SDA while SCL is high ([Figure 2](#_page16_x67.00_y364.00)). A START condition from the master signals the beginning of a transmission to the MAX14521E. The master terminates transmission and frees the bus by issuing a STOP condition. The bus remains active if a REPEATED START condition is gener- ated instead of a STOP condition.

S Sr P![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.016.png)

SCLSDA

*Figure 2. START, STOP, and REPEATED START Conditions*

**Early STOP Conditions**

The MAX14521E recognizes a STOP condition at any point during data transmission except if the STOP condi- tion occurs in the same high pulse as a START condition. For proper operation, do not send a STOP condition dur- ing the same SCL high pulse as the START condition.

**Slave Address**

The  MAX14521E  has  selectable  device  addresses through external inputs. The slave address consists of five fixed bits (B7–B3, set to 11110) followed by two pin programmable bits (A1 and A0).

For example: If A1 and A0 are hardwired to ground, the complete address is 1111000. The full address is defined as the seven most significant bits followed by the read/ write  bit.  Set  the  read/write  bit  to  1  to  configure  the 

MAX14521E to read mode. Set the read/write bit to 0 to configure the MAX14521E to write mode. The address is the first byte of information sent to the MAX14521E after the START condition.

**Acknowledge**

The acknowledge bit (ACK) is a clocked 9th bit that the MAX14521E  uses  to  handshake  receipt  each  byte  of data when in write mode (see [Figure 3](#_page16_x324.00_y401.00)). The MAX14521E pull down SDA during the entire master-generated 9th clock pulse if the previous byte is successfully received. Monitoring ACK allows for detection of unsuccessful data transfers. An unsuccessful data transfer occurs if a receiv- ing device is busy or if a system fault had occurred. In the event of an unsuccessful data transfer, the bus master may retry communication.

The master pulls down SDA during the 9th clock cycle to acknowledge receipt of data when the MAX14521E are in read mode. An acknowledge is sent by the master after each read byte to allow data transfer to continue. A not acknowledge is sent when the master reads the final byte of data from the MAX14521E followed by a STOP condition.

CLOCK PULSE FOR![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.017.png)

ACKNOWLEDGMENT START

CONDITION

SCL 1 2 8 9

NOT ACKNOWLEDGE SDA

ACKNOWLEDGE

*Figure 3. Acknowledge*

**Write Data Format**

A  write  to  the  MAX14521E  includes  transmission  of  a START condition, the slave address with the R/W bit set to 0, one byte of data to configure the internal register address pointer, one or more bytes of data, and a STOP condition.  [Figure  4](#_page17_x67.00_y270.00)  illustrates  the  proper  frame  format for writing one byte of data to the MAX14521E. [Figure 5](#_page17_x62.00_y434.00) illustrates the frame format for writing n-bytes of data to the MAX14521E.

The slave address with the R/W bit set to 0 indicates that the master intends to write data to the MAX14521E. The MAX14521E  acknowledge  receipt  of  the  address  byte during the master-generated 9th SCL pulse.

The second byte transmitted from the master configures the  MAX14521E  internal  register  address  pointer.  The pointer tells the MAX14521E where to write the next byte of data. An acknowledge pulse is sent by the MAX14521E upon receipt of the address pointer data.

The third byte sent to the MAX14521E contains the data that will be written to the chosen register. An acknowledge pulse from the MAX14521E signals receipt of the data 

byte.  The  address  pointer  autoincrements  to  the  next register address after each received data byte. This auto- increment feature allows a master to write to sequential registers within one continuous frame. Attempting to write to register addresses higher than 0x0B results in repeated writes of 0x0B. [Figure 5](#_page17_x62.00_y434.00) illustrates how to write to multiple registers with one frame. The master signals the end of transmission by issuing a STOP condition.

Maxim Integrated  │ 28

ACKNOWLEDGE FROM MAX14521E![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.018.png)

|B7|B6|B5|B4|B3|B2|B1|B0|
| - | - | - | - | - | - | - | - |
ACKNOWLEDGE FROM MAX14521E ACKNOWLEDGE FROM MAX14521E



|S|SLAVE ADDRESS 0|A|REGISTER ADDRESS|A|DATA BYTE|A|P|
| - | - | - | - | - | - | - | - |
R/W 1 BYTE

AUTOINCREMENT INTERNAL REGISTER ADDRESS POINTER

*Figure 4. Writing One Byte of Data to the MAX14521E*

ACKNOWLEDGE FROM MAX14521E ACKNOWLEDGE FROM MAX14521E![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.019.png)



|B7|B6|B5|B4|B3|B2|B1|B0|
| - | - | - | - | - | - | - | - |

|B7|B6|B5|B4|B3|B2|B1|B0|
| - | - | - | - | - | - | - | - |
ACKNOWLEDGE FROM ACKNOWLEDGE FROM MAX14521E MAX14521E



|S|SLAVE ADDRESS 0|A|REGISTER ADDRESS|A||DATA BYTE 1|A|
| - | - | - | - | - | :- | - | - |

|` `DATA BYTE n||A|P|
| - | :- | - | - |
R/W 1 BYTE 1 BYTE

AUTOINCREMENT INTERNAL REGISTER ADDRESS POINTER

*Figure 5. Writing n-Bytes of Data to the MAX14521E*

Maxim Integrated  │ 

**Read Data Format**

Send the slave address with the R/W set to 1 to initiate a read operation. The MAX14521E acknowledges receipt of its slave address by pulling SDA low during the 9th SCL clock pulse. A START command followed by a read command  resets  the  address  pointer  to  register  0x00. The first byte transmitted from the MAX14521E will be the contents of register 0x00. Transmitted data is valid on the rising edge of the master-generated serial clock (SCL). The  address  pointer  autoincrements  after  each  read data byte. This autoincrement feature allows all registers to be read sequentially within one continuous frame. A STOP condition can be issued after any number of read data  bytes.  If  a  STOP  condition  is  issued  followed  by another read operation, the first data byte to be read will be from register 0x00 and subsequent reads will autoin- crement the address pointer until the next STOP condition. 

The address pointer can be preset to a specific register before a read command is issued. The master presets the address pointer by first sending the MAX14521E’s slave address with the R/W bit set to 0 followed by the register address. A  REPEATED  START  condition  is  then  sent, followed by the slave address with the R/W set to 1. The MAX14521E transmits the contents of the specified regis- ter. The address pointer autoincrements after transmitting the first byte. Attempting to read from register addresses higher than 0x0B results in repeated reads of 0x0B. The master acknowledges receipt of each read byte during the acknowledge clock pulse. The master must acknowledge all correctly received bytes except the last byte. The final byte must be followed by a not acknowledge from the master and then a STOP condition. [Figure 6](#_page18_x62.00_y369.00) illustrates the frame format for reading one byte from the MAX14521E. [Figure 7](#_page18_x64.00_y537.00) illustrates the frame format for reading multiple bytes from the MAX14521E.

Maxim Integrated  │ 29

ACKNOWLEDGE FROM MAX14521E NOT ACKNOWLEDGE FROM MASTER![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.020.png)

ACKNOWLEDGE FROM MAX14521E ACKNOWLEDGE FROM MAX14521E

|S|SLAVE ADDRESS 0|A|REGISTER ADDRESS|A|Sr|SLAVE ADDRESS 1|A|` `DATA BYTE|A|P|
| - | - | - | - | - | - | - | - | - | - | - |
R/W REPEATED START R/W 1 BYTE

AUTOINCREMENT INTERNAL REGISTER ADDRESS POINTER

*Figure 6. Reading One Indexed Byte of Data from the MAX14521E*

ACKNOWLEDGE ACKNOWLEDGE ACKNOWLEDGE FROM MAX14521E![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.021.png) FROM MAX14521E FROM MAX14521E



|S|SLAVE ADDRESS 0|A|REGISTER ADDRESS|A|Sr|SLAVE ADDRESS 1|A|
| - | - | - | - | - | - | - | - |

|` `DATA BYTE|A|P|
| - | - | - |
R/W REPEATED START R/W 1 BYTE

AUTOINCREMENT INTERNAL REGISTER ADDRESS POINTER

*Figure 7. Reading n-Bytes of Indexed Data from the MAX14521E*

Maxim Integrated  │ 

**ESD Test Conditions**

ESD performance depends on a number of conditions. The MAX14521E are specified for ±15kV (HBM) typical ESD resistance on the EL lamp outputs.

**HBM ESD Protection**

[Figure  8a](#_page19_x66.00_y295.00)  shows  the  Human  Body  Model,  and [Figure 8b](#_page19_x323.00_y295.00) shows the current waveform it generates when discharged into a low impedance. This model consists of a 100pF capacitor charged to the ESD voltage of interest, which is then discharged into the device through a 1.5kΩ resistor.

RC RD![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.022.png)1MΩ 1.5kΩ

CHARGE-CURRENT- DISCHARGE LIMIT RESISTOR RESISTANCE

HIGH-  DEVICE VOLTAGE Cs STORAGE UNDER

DC 100pF CAPACITOR TEST

SOURCE

*Figure 8a. Human Body ESD Test Model*

**Design Procedure**

**LX Inductor Selection**

The  recommended  tapped-inductor  ratio  is  1:7  with  a 2.3μH primary inductance and 115μH secondary induc- tance.  For  most  applications,  the  primary  series  resis- tance  (DCR)  should  be  below  1Ω  for  reasonable  effi- ciency. Do not exceed the inductor’s saturation current. See [Table 15](#_page19_x53.00_y464.00) for a list of recommended tapped-inductors.

IP 100% Ir PEAK-TO-PEAK RINGING 90%![](Aspose.Words.3cf04602-34d7-4b9a-8220-1bd18df404b1.023.png) (NOT DRAWN TO SCALE)

AMPERES

36.8%

10% 0

0 t TIME

RL tDL

CURRENT WAVEFORM

*Figure 8b. Human Body Current Waveform*

Maxim Integrated  │ 30

**Table 15. Inductor Vendors**

|**INDUCTOR VALUE (μH)**|**VENDOR**|**URL**|**PART NUMBER**|
| - | - | - | - |
|2.3/115|Coilcraft|www.coilcraft.com|GA3250-BL|
|2.3/115|Cooper|www.cooper.com|CTX03-18210-R|

Maxim Integrated  │ 

**CCS Capacitor Selection**

CCS is the output of the boost converter and provides the high-voltage source for the EL lamp. Connect a 3.3nF capacitor from CS to GND and place as close to the CS input as possible.

**Diode Selection**

Connect a diode, D1, from the LX node to CS to rectify the boost voltage on CS. The diode should be a fast recovery diode that is tolerant to +200V.

**EL Lamp Selection**

EL lamps have a capacitance of approximately 2.5nF to 3.5nF per square inch. See the Total Input Current vs. Load graph in the Typical Operating Characteristics sec-tion for compatible lamp sizes. 

**Snubber Selection**

An RSN value of 20Ω and CSN value of 330pF is suf- ficient for VDD < 5V and CLAMP\_TOTAL < 40nF. For higher capacitive loads on the EL output or for VDD > 5V, CSN must be increased to keep LX spikes less than 30V.

**fSW Selection**

Choose a boost-converter frequency such that the satu- ration current of the tapped-inductor primary coil is not 

exceeded. Special attention must be given to program the FSW bits properly when VBAT > 5.5V to avoid destruction of the device. In general, it is good practice to start from the highest fSW setting (1.6MHz) and decrease accord- ingly to obtain the acquired waveshape on the EL outputs and to prevent exceeding the saturation current of the tapped-inductor.

**Applications Information**

**PCB Layout**

Keep  PCB  traces  as  short  as  possible.  Ensure  that bypass capacitors are as close to the device as possible. Use large ground planes where possible.

**Ordering Information**

|**PART TEMP RANGE PIN-PACKAGE**|
| - |
|MAX14521EETG+ -40°C to +85°C 24 TQFN-EP\*|
*+Denotes lead(Pb)-free/RoHS-compliant package. \*EP = Exposed pad.*

**Chip Information**

PROCESS: BiCMOS-DMOS


© 2023 Firechip SL.

