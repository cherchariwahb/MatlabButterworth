# TP 1 :
## Q 1 :
### f(x)
```console
>> f = @(x)sin(x);
>> x=[0:0.1:2*pi];
>> plot (x,f(x)); 
```
![GitHub Logo](/tp1/6.PNG)
> Tilte
```console
>> plot (x,f(x))
>> title('sinus (x)')
>> xlabel('x')
>> ylabel('f(x)')
```
![GitHub Logo](/tp1/7.PNG)
## Q 2 :
### vector
```console
>> v1 = [1,2,3,4]
>> v2 = [5,6,7,8]
>> v1+v2
>> v1.^2
>> v1.*3
```
![GitHub Logo](/tp1/8.PNG)
## Q 3 :
### Laplace
```console
>> syms t s
>> laplace (dirac(t))
>> laplace (heaviside(t))
>> laplace(exp(3*t))
>> laplace(sin(t))
>> laplace(cos(t))
>> laplace(t)
>> laplace(t^2)
```
![GitHub Logo](/tp1/9.PNG)
# MatlabButterworth
## Step 1 :
### determine the value of `N` and `Wc`.
###   Step 1.1 :
#### determine the value of `Rp`,`Rs`,`Wp`and `Ws`.
```console
>> Rp = -20*log10(0.8);
>> Rs = -20*log10(0.2);
>> wp = 5 ;
>> ws = 20 ;  
```
![GitHub Logo](/tp1/1.PNG)
###   Step 1.2 :
#### determine the value of `N` and `Wc`.
```console
>> [N,wc] = buttord (wp,ws,Rp,Rs,'s'); 
 
```
![GitHub Logo](/tp1/2.PNG)
## Step 2 :
### Transfer function .
###   Step 2.1 :
#### determine the  `num`and `den`.
```console
>> [num,den] = butter ( N,wc,'s');
```
![GitHub Logo](/tp1/3.PNG)
###   Step 2.2 :
#### determine `H(S)`.
```console
 >> Ht = tf(num , den);
```
![GitHub Logo](/tp1/4.PNG)

## Step 3 :
### Trace `H(S)`.
```console
 >> [H,w] = freqs(num,den);
 >> Plot (w,abs(H));
```
 - x = wc = 9.03 
 - 0.2 < = y = 0.707 <= 0.8 
![GitHub Logo](/tp1/5.PNG)

