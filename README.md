# Temperature Regulation with LABVIEW

## Objective
The goal of this project is to create a temperature regulation loop using a DC fan. This fan is controlled by an interface board and programmed in the LABVIEW environment based on temperature values measured by an LM35 sensor.

## Equipment Used
1. **K8055 Acquisition and Control Board** (Velleman)
2. **Innovative SP401212M Fan**
    - Voltage: 12 V DC
    - Current: 0.06 A
3. **LM35 Temperature Sensor** (Texas Instruments)
    - Operating Voltage: 4V to 30V
    - Linear Output: 10 mV/°C
    - Temperature Range: -55°C to 150°C
4. **External Power Supply for the Fan** (12 V DC)

## Specifications
1. **Design of the Interface Board**: An interface board must be designed to enable closed-loop regulation of the fan according to its specifications.
2. **LABVIEW Programming**: The control of the fan will be implemented via programming in LABVIEW, utilizing the values measured by the LM35 temperature sensor connected to the K8055 board.
3. **Electronic Assembly**:
    - **LM35 Temperature Sensor**:
        - The output **Vout** is connected to the analog input **A2** of the K8055 board.
        - The power supply **+Vs** is connected to the analog output **Dac2** of the board.
        - The ground **GND** is connected to the GND of the board.
    - **SP401212M Fan**:
        - The fan is powered by an external 12 V source.
        - The fan is controlled via the digital output **DO2** of the K8055 board.

## Operation
1. The **LM35 sensor** measures the ambient temperature and sends a voltage proportional to the temperature to the **A2** input of the K8055 board.
2. The **K8055 board** converts this voltage into a digital value that can be used by LABVIEW.
3. LABVIEW controls the speed of the **fan** by adjusting the **DO2** output based on the measured temperature values.
4. The fan is activated when the digital output **DO2** of the board is turned on, closing the circuit and allowing current to flow.

## Wiring Diagram
### LM35 Sensor:
- **Vout** → **A2** (analog input K8055)
- **+Vs** → **Dac2** (analog output K8055)
- **GND** → **GND** (K8055)

### SP401212M Fan:
- **+Vs** (12 V) → External power supply
- **GND** → **DO2** (digital output K8055)

## K8055 Board Configuration
The switches **SK5** and **SK6** are left open, configuring the board's address to **0**.

## Important Remarks
- When connecting the LM35 temperature sensor, it is crucial to carefully follow the datasheet to avoid any connection errors.
- The fan must be powered by an external 12 V source, as the K8055 board only provides 5 V, which is insufficient to operate it.

## Conclusion
This project allows for the understanding and implementation of closed-loop temperature regulation using a sensor, a fan, a K8055 acquisition board, and the LABVIEW environment.
