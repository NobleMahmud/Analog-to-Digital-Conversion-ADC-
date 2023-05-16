# Analog-to-Digital-Conversion-ADC-

Analog to Digital Conversion (ADC) as a three-step process.This process is

1. Sampling
This is the conversion of a continuous-time signal into a discretetime signal obtained
by taking &quot;samples&quot; of the continuous time signal at discrete-time instants. Thus, if
xa(t)is the input to the sampler, the output is xa(nT )=x(n),where T is called the
sampling interval.
2. Quantization
This is the conversion of a discrete-time continuous-valued signal into a discrete-time,
discrete-valued (digital) signal. The value of each signal sample is represented by a
value selected from a finite set of possible values. The difference between the
unquantized sample x( n )and the quantized output xq( n ) is called the quantization
error.
3. Coding
In the coding process, each discrete value xq(n) is represented by a b-bit binary
sequence.
Sample the sinusoid x(t) = sin(2*pi*F*t), where F = 2 kHz, and plot the sampled(DT)
signals over the continuous-time signal.
 Let x1 be the signal sampled at 10 kHz.
 Let x2 be the signal sampled at 3 kHz.


F = 2000;
T = 1/F;
tmin = 0;
tmax = 3*T;
dt = T/100;
dt1 = 1/10000;
dt2 = 1/3000;
x = tmin:dt:tmax;
x1 = tmin:dt1:tmax;
x2 = tmin:dt2:tmax;
y = sin(2*pi*F*x);
y1 = sin(2*pi*F*x1);
y2 = sin(2*pi*F*x2);
subplot(3,1,1);
plot(x,y,&#39;r&#39;);
subplot(3,1,2);
plot(x,y,&#39;r&#39;);
hold on
stem(x1,y1,&#39;b&#39;);
subplot(3,1,3);
plot(x,y,&#39;r&#39;);
hold on
stem(x2,y2,&#39;b&#39;);
hold off

% Quantization and Coding
U=8;
n=3;
q=U/(2^n-1);
t=0:0.1:8;
y=abs(8*sin(t));
a=fix(y/q);
yd=dec2bin(a,n)
yq=a*q;
plot(t,y,&#39;r&#39;);
hold on
plot(t,yq,&#39;g&#39;);
hold off
