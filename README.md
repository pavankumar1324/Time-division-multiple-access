%Time-division-multiple-access
%TDMA matlab code using parameters

clc
clear all
close all
t = (0:0.1:4*pi);
a = sin(t);
figure(1);
plot(a);
title('sine signal');
xlabel('time');
ylabel('amplitude');
%plot(t,a);
x = (0:0.1:4*pi);
y = cos(x);
figure(2);
plot(y);
title('cosine signal');
xlabel('time');
ylabel('amplitude');
%plot(x,y);

%sampling the signals
stem(a);
title('Sampled Sinusoidal Signal');
ylabel('Amplitude');
xlabel('Time');
figure(3);
stem(y);
title('Sampled cosine Signal');
ylabel('Amplitude');
xlabel('Time');
figure(4);
%length of samples
l1=length(a);
l2=length(y);
for i=1:l1
z(1,i)=a(i);
z(2,i)=y(i);
end
tdmasig=reshape(z,1,2*l1);
stem(tdmasig);
figure
pwelch(tdmasig,[],[],[],1000);
title('Power Spectral Density');

