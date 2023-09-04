# Smart_Water_Pump_Switch

Promoting global sustainability by conserving power and reducing water wastage is paramount. "Automatic Water Pump Switch with Level Indicator" project aims to empower households to make a meaningful contribution towards minimizing both power and water waste. This solution ensures that the water pump switches off before overflowing, switches on when water reaches a specified low level, and provides a real-time display of the tank's current water level.

## The Product Architecture

The automatic water pump switch consists of three main sub-systems.
  1. **Regulated DC power supply**
  2. **Automatic water pump switch**
  3. **Water level indicator**

### Regulated DC Power Supply

The regulated DC power supply in our project takes a nonregulated AC power supply as input and delivers a filtered, stable DC voltage. It comprises four main blocks: a step-down transformer (230V to 9V), a bridge wave rectifier using four IN4007 rectifier diodes, a filtering stage with a 470uF 50V electrolytic capacitor and three 0.01uF ceramic capacitors, and finally, voltage regulators (7805 and 7806 ICs) to provide constant 5V and 6V DC outputs for powering the subsystems of the project. This power supply unit ensures that each subsystem receives the appropriate voltage levels it requires.

### Automatic Water Pump Switch

The automatic water pump switch subsystem operates based on preset threshold levels, ensuring efficient control of the water pump. It employs several key components, including an op-amp comparator (LM324n) to detect water levels, a 555 timer IC (NE555) as a threshold detector, an NPN transistor (BC547) for switching, and a Single Pole Double Throw (SPDT) relay to control the water pump. The op-amp comparator identifies two threshold levels based on the water level indicator circuit's inputs. The 555 timer IC receives inputs indicating water levels and produces the appropriate output to control the transistor, which, in turn, activates or deactivates the relay switch. This design allows the water pump to operate when the water level falls below the lower threshold and stops once it exceeds the upper threshold, ensuring efficient and automated water management while safeguarding against voltage spikes with the IN4007 flyback diode.

### Water Level Indicator

The water level indicator subsystem provides real-time water level information, displaying it as a numerical value ranging from 0 to 9. This subsystem comprises four main components: a priority encoder (74LS147 IC) to compress multiple inputs into fewer outputs, transistors functioning as NOT gates to handle encoder outputs, a BCD to 7 segment decoder (CD4511 IC) to convert binary input values into 7-segment display outputs, and the 7-segment display itself. The priority encoder collects data from various sources, which is then processed by the transistors and decoded into numerical values by the BCD to 7 segment decoder. The 7-segment display visually represents the current water level, providing users with a clear indication of the water level status.

## Enclosure Design
