**********************************************
LED_Light_Stimulation.vi: Execution of light stimulation protocols to evoke neural activity in ChR2 expressing neurons according to a preconceived stimulation file (csv format).

By Vani Rajendran and Aljoscha Schulze
Center for Genomic Regulation (CRG), Barcelona Spain
AljoschaTobias@yahoo.com

For bug reports/comments/feedback, e-mail: mlouis_at_crg.eu or matthieu.louis_at_icloud.com
**********************************************

This package contains a Labview routine to drive an LED stimulation according to to a preconceived light stimulation time course (in the form of voltage values defining the light intensity). This stimulation protocol was used in conjunction with one 'NI USB-6008 12-Bit, 10 kS/s Low-Cost Multifunction DAQ' board connected to a PC. The analog output of this DAQ board was connected to the LED driver driving changes of the LED intensity according to the light stimulation protocol.In order to learn the relationship between the output voltage and the light intensity present at the experimental setup, a calibration of the LED as it is connected to the LED controller has to be performed prior to running this routine.

The light stimulation protocol should come in the form of a csv file containing only one column of voltage values. Every line in this csv file corresponds to a voltage and thus a light intensity value of the stimulation time course (values should not exceed 5V). The frame-size (Set frame size) of the execution protocol has to be defined before the stimulation is executed at the Labview VI front panel by the user (units are in milliseconds).

For bug reports/comments/feedback, e-mail: mlouis_at_crg.eu or matthieu.louis_at_icloud.com

**********************************************
Main routines:
**********************************************

* LED_Light_Stimulation.vi: LED stimulation interface

Execution of this program leads to the execution of custom LED stimuli via the analog output port of a Multifunction DAQ device. The stimulus time course (voltage values) of the odor channel has to be computed prior to the execution and saved as a csv file. The user should adapt the stimulation protocol to the frame-size that he intends to use. 

**********************************************
Front panel:
**********************************************

Stimulation START: Pressing this button leads to a prompt asking the user to load the stimulation csv file. As soon as the file is selected the stimulation starts.

Set frame size (min=2ms): Define the frame size of the stimulation protocol in units of milliseconds.

Duration of the Stimulation (s): Shows the duration of the stimulation protocol for the defined frame-size.

Length of csv file: Shows the number of values (each values corresponding to a single frame of the stimulation) contained in the loaded stimulation csv file.

Format of the csv file: The csv file should contain only one column of numbers (voltage values) that correspond to the LED stimulation.

**********************************************
Block diagram:
**********************************************

The user has to open the DAQ Assistant and edit both the coordinates and the analog output port of the DAQ device that is being used to drive the light stimulation via the LED controller.

