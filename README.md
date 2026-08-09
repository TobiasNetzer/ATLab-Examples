# ATLab Demo

This project demonstrates some of the features and capabilities of the [ATLab](https://github.com/TobiasNetzer/ATLab) testing framework.

The hardware used for this demonstration is the [TIA-Demo Board](https://github.com/TobiasNetzer/TIA-Demo_HW).

# Test Procedure

The test sequence begins with an initial supply voltage check and configuration of the onboard I²C GPIO expander.  
Next, each segment of the 7-segment display is activated individually and validated using voltage measurements.  
The state of the DIP switches is then read and evaluated.

To demonstrate ATLab's dynamic test execution capabilities, the DIP switches are used to select which test cases are executed.

![image](ATLab_TIA-Demo/Test%20Configuration.png)

## 1 LED Test
The onboard RGB LED is activated via the STIM channels.  
The forward voltage and current are then measured using the connected DMM.

## 2. Button Test
The user is prompted to press both buttons in succession.  
The test verifies that the expected button states are detected.

## 3. Voltage Divider Test
Different resistance values are switched via the STIM channels to generate a range of voltages.  
The resulting voltages are measured and validated.

## 4. Potentiometer Adjustment
The user is prompted to adjust the onboard potentiometer to 1.5 V.  
The wiper voltage is continuously measured until the target voltage is reached and the user confirms the adjustment by pressing Enter.

## 5. Temperature Sensor Test
The output voltage of the onboard temperature sensor is measured.  
The corresponding temperature is then calculated using a custom math expression.

## 6. I2C DAC Test
The onboard I²C interface of the Test Interface Adapter is used to configure various output voltages on the DAC.  
The resulting voltages are measured and validated using the external DMM.

## 7. Program MCU
A J-Link programming script is executed to program the ATSAMD10C13A using a J-Link EDU Mini.  
The firmware version is then read back and verified to confirm that programming was successful.

## 8. MCU UART Test
UART is used to communicate with the MCU.  
The test reads back voltage measurements from the MCU's ADC and configures various DAC output voltages via UART.

# Test Results
After the test sequence has completed, the results can be exported in two formats:
- [CSV Export](Prototype-001_2026-08-09_18-12-38.csv) - Raw measurement and test data for further analysis or processing.
- [Test Report](Prototype-001_2026-08-09_16-03-28.pdf) - A formatted PDF report containing the test results and DUT information.