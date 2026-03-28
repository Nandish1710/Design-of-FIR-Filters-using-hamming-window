
# RESULT:
# 4 B Design of FIR Filters using Hamming Window

# AIM: 
          
To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

PC Installed with SCILAB 

# PROGRAM 
a. Design of Low Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = Wc/%pi;
    else
        hd(n) = sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Hamming Window
for n = 1:M
    W(n) = 0.54 - 0.46*cos((2*%pi*(n-1))/(M-1));
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hamming Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hamming Window');
```
b. Design of High Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = 1 - (Wc/%pi);
    else
        hd(n) = -sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Hamming Window
for n = 1:M
    W(n) = 0.54 - 0.46*cos((2*%pi*(n-1))/(M-1));
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hamming Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hamming Window');
```
c. Design of Band Pass FIR Digital filter
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = ');

alpha= (M -1)/2  

for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =(Wc2-Wc1)/%pi ; 
    else 
        hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);
    end 
end 
// Hamming Window 
for n = 1:M 
    W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp('Filter Coefficients are') 
disp(h) 
[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hamming Window ') 

hzm_dB = 20* log10 (hzm);
 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hamming Window');
```
d. Design of Band Stop FIR Digital filter
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = ');

alpha= (M -1)/2 // Center Value 

for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =1-((Wc2-Wc1)/%pi) ; 
    else 
        hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); `  k,
    end 
end 
// Hamming Window 

for n = 1:M 
    W(n) = 0.54-(0.46*cos((2*%pi*(n-1))/(M-1)));  
end 
//Windowing filter coefficients 

h = hd.*W; 
disp('Filter Coefficients are') 
disp(h) 


[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hamming Window ') 

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hamming Window');
```
# OUTPUT
a. Design of Low Pass FIR Digital filter

<img width="2878" height="1794" alt="image" src="https://github.com/user-attachments/assets/ff331aa4-70f1-4c21-8621-161ccebeb0c5" />

b. Design of High Pass FIR Digital filter

<img width="2879" height="1794" alt="image" src="https://github.com/user-attachments/assets/9ed3922e-8e80-4bad-b06b-1710e9a57709" />

c. Design of Band Pass FIR Digital filter

<img width="2874" height="1796" alt="image" src="https://github.com/user-attachments/assets/0e105d55-a083-4bb0-9212-bb4faea967df" />

d. Design of Band Stop FIR Digital filter

<img width="2875" height="1794" alt="image" src="https://github.com/user-attachments/assets/62dbc942-a412-4649-9f9f-ecb4c0ae8aa1" />

# RESULT
The FIR Filters were successfully designed using Hamming window Technique.
