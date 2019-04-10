**linear convolution**

a=3*3

b=3*2

conv2(a,b)



**circular conolution**

a=2*2, 

h=2*2



X=fft2(a)

H=fft2(h)

Y=X.*H (Dot Product)

y=ifft(Y)  (inverse fourier)



**Circular Conolution expressed as linear convolution plus alias**

a and b are two matrices 2*2

y=conv2(a,b)

y1=[y(:,1)+y(:,$),y(:,2)]

cc=[y1(1,:)+y1($,:),y1(2,:)]



**Linear Cross Correlation**

a=2*2

b=2*2

h1=b( : , $​: - 1 : ​1)

h2=h1($ : -1 : 1 , :)

y=conv2(a , h2)

**Circular Correlation**

a=2*2

b=2*2

h1=b( : , $​: - 1 : ​1)

h2=h1($ : -1 : 1 , :)

X=fft2(a)

H=fft2(h2)

Y=X.*H

y=ifft(Y)

**Linear auto Correlation**

a=2*2

b=a( : , $​ :  - 1 :​ 1)

b=b($ : -1 : 1 , :)

cor=conv2(a,b)



**DFT of 4x4 gray scale image**



a=4*4

t=fft2(a)



**Perform threshold operation**

[m n ] = size(a)

for i = 1 : m

for j = 1 : n

if(a(i,j)<t)

b(i,j)=0

else

b(i,j)=255

end

end

end

**Gray level slicing**

y = double(x)

[m n ] = size(a)

L = max(a)

average = round(L/2)

for i = 1 : m

for j = 1 : n

if ( y ( i , j ) >= a & y( i , j )<=b)

b( i , j ) = L

else

b( i , j ) = 0

end

end

end