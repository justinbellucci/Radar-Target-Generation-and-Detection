# Radar Target Generation and Detection

This is the final project for the Radar class in the Sensor Fusion Engineer Nanodegree from Udacity. The goal of this project is to generate a radar signal in Matlab and then use the radar signal to detect a target using 2D Fast Fourier Transform and CA-CFAR.

## Radar Specifications
Frequency of operation = 77GHz  
Max Range = 200m  
Range Resolution = 1 m  
Max Velocity = 100 m/s  

Initial position and velocity of the target is given by the following:  
`x0 = 160`  
`v0 = 60`  

## 1D-FFT for Range Detection

A transmit and received signal is generated using the following parameters:  
* Sweep Bandwidth    
* Chirp Time   
* Chirp Slope  

`Nd=128` is the number of chirps in a Doppler FFT.  `
`Nr=1024` is the number of range bins in the output.

The Tx and Rx signals are mixed together with noise to form the radar signal. By performing a 1D FFT on the mixed signal, we can detect the target at 160 meters as noted by image below.

<img src="images/1dfft.png" width="600" align="center"/>  
  
## 2D-FFT for Range and Doppler Velocity Detection
In order to resolve the range and velocity of the target, a 2D-FFT is performed on the noisy radar signal. The Range-Doppler Map is shown below with a considerable amount of clutter alough the target is clearly visible with a velocity of 60 m/s and a range of 160 m.

<table border=0 width="600px" align="center">
	<tbody> 
    <tr>		
            <td width="20%" align="center"> </td>
			<td width="20%" align="center"> </td>
		</tr>
		<tr>
			<td width="20%" align="center"> <img src="images/2dfft.png"> </td>
			<td width="20%" align="center"> <img src="images/cfar.png"> </td>
		</tr>
	</tbody>
</table>
