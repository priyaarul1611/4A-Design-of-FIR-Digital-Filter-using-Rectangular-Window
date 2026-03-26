# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) = Wc/ %pi ; 
else 
hd(n) = sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) = 1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR LPF using Rectangular Window');
```
**CALCULATION:**
<img width="940" height="1384" alt="image" src="https://github.com/user-attachments/assets/c8c673a6-4088-4448-a652-1868db4607f6" />
<img width="940" height="705" alt="image" src="https://github.com/user-attachments/assets/40bed32d-7e99-4592-a9fd-eb02d9240d2e" />

# OUTPUT: 
<img width="533" height="492" alt="LPF-Rectangular Window cal" src="https://github.com/user-attachments/assets/81e1bdf8-57e0-48c2-9076-b396d6abad6c" />
<img width="762" height="717" alt="LPF-Rectangular window graph" src="https://github.com/user-attachments/assets/6d1bac39-5a9b-48c9-b66d-3299700970e2" />

# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n)=1-Wc/ %pi ; 
else 
hd(n) =-sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Rectangular Window'); 
```
**CALCULATION:**
<img width="940" height="705" alt="image" src="https://github.com/user-attachments/assets/fbf0736c-9d5f-412c-917e-dfbd78caa057" />
<img width="940" height="1126" alt="image" src="https://github.com/user-attachments/assets/f0228950-70df-44a1-bd37-90756621ec4f" />


# OUTPUT: 
<img width="514" height="474" alt="HPF-Rectangular calculation" src="https://github.com/user-attachments/assets/10e8fc48-ef99-4c19-9d24-48b2af34181f" />
<img width="762" height="721" alt="HPF-Rectangular graph" src="https://github.com/user-attachments/assets/6abdb4ab-9970-4b97-937d-0fe7963cad5d" />
# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1;  
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Rectangular Window'); 
```
**CALCULATION:**
<img width="818" height="1454" alt="image" src="https://github.com/user-attachments/assets/5864d823-4ba8-4f1d-9075-e4eefc7b6f47" />
<img width="940" height="1194" alt="image" src="https://github.com/user-attachments/assets/b6113f6d-528e-4f70-a64d-05f1f85353ef" />

# OUTPUT: 
<img width="549" height="455" alt="BPF-Rectangular Calculation" src="https://github.com/user-attachments/assets/1681263b-7b4b-45a3-b0e6-84e13dde0b36" />
<img width="760" height="720" alt="BPF-Rectangular Graph" src="https://github.com/user-attachments/assets/d40091b9-3dae-4e35-a160-908c36f1f217" />

# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi) ; 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR BSF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Rectangular Window'); 
```
**CALCULATION:**
<img width="940" height="1381" alt="image" src="https://github.com/user-attachments/assets/daa81326-b8c4-42c0-a9f4-062cf183056a" />
<img width="940" height="410" alt="image" src="https://github.com/user-attachments/assets/54a44638-41aa-4d58-9c27-a652c0c9166e" />

# OUTPUT: 
<img width="558" height="511" alt="BSF-Rectangle Calculation" src="https://github.com/user-attachments/assets/2941a094-0121-4e58-a98d-5c990bea1d90" />
<img width="756" height="718" alt="BSF-Rectangle Graph" src="https://github.com/user-attachments/assets/7a6349d7-9c9a-40ef-a884-2952abc993f5" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
