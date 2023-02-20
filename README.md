# Calculate $\pi$ by hand to 20 decimal places
Here is a simple and optimized method for calculating pi to 20 decimal places.  
20 decimal places of $\pi$ corresponds to 60 nanometers along the orbit of Pluto!   
With focus you should be finished in a few hours.  
You only need to know how to calculate long division.  
To follow the Mathematics you need to understand complex numbers, Calculus and Geometric Series. Only very basic trigonomety is required. Complex numbers let us to avoid trigonometric [Angle Sum formulae](https://en.wikipedia.org/wiki/List_of_trigonometric_identities#Angle_sum_and_difference_identities).

## Machin Formula (1706)

We will use the tangent of an angle function which is defined as
$$tan(angle)={sin(angle) \over cos (angle)}={rise \over run}=slope$$
Inverting gives us
$$angle=arctan(slope)$$

The slope $1 \over 5$, which is $5+i$ in complex numbers, has an angle of about $11.3 \degree$. Rotating by this angle 4 times is close to $45 \degree$. Let's calculate this slope with complex numbers. 
$$(5+i)^4$$
$$=(25+2*5i+i^2)^2=(24+10i)^2(1-i)=2^2(12+5i)^2$$
$$=4(144-25+2*60i)=4(119+120i)$$

We have just found that 4 times a slope of $1 \over 5$ is a slope of $120 \over 119$, which is just bigger by $1\over119$ than ${1\over1} = 45\degree$. Let's rotate by $-45 \degree=(1-i)$ from this angle to find that tiny angle.
$$(119+120i)(1-i)$$
$$=(119-119i+120i-120i^2)$$
$$=239+i$$
This number ${1\over 239}$ is the very small slope we have been looking for. It is an angle about $ 0.24 \degree$.
We have calculated that
$$ 4*arctan({1 \over 5})-arctan({1\over 1})=arctan({1 \over 239})$$
We know that $arctan(1)=45 \degree ={\pi \over 4}$ which gives us
$$ 4*arctan({1 \over 5})-{\pi \over 4}=arctan({1 \over 239})$$
Rearranging gives us the [famous formula](https://en.wikipedia.org/wiki/Machin-like_formula) found by John Machin in 1706.
$$ {\pi \over 4}=4*arctan({1 \over 5})-arctan({1 \over 239})$$
We will use this formula to calculate $\pi$ to 20 decimal places.  

## Approximating the Arctanget function

By definition of inverse functions
$$arctan(tan(x))=x$$
Differentiating and using the [Chain Rule](https://en.wikipedia.org/wiki/Chain_rule) gives
$$arctan'(tan(x)).tan'(x)=1$$
Applying the [Quotient Rule](https://en.wikipedia.org/wiki/Quotient_rule)
$$tan'(x)={d \over dx}({sin(x) \over cos(x)})={sin'(x).cos(x)-sin(x).cos'(x) \over cos^2(x)} $$
$$={cos^2(x)+ sin^2(x)\over cos^2(x)}={cos^2(x) \over cos^2(x)}+ {sin^2(x) \over cos^2(x)} $$
which gives us the nice identity
$$tan'(x)= 1 + tan^2(x) $$
Therefore
$$arctan'(tan(x)).(1+tan^2(x))=1$$
$$arctan'(tan(x))={1 \over 1+tan^2(x) }$$
Letting $y=tan(x)$
$$ arctan'(y)={ 1 \over 1+y^2} = { 1 \over 1-(-y^2)} $$
By inspection, this is the sum of the [Geometric Series](https://en.wikipedia.org/wiki/Geometric_series) of $-y^2$

$$ arctan'(y)=\sum_{n=0}^{\infin} (-y^2)^n=\sum_{n=0}^{\infin} (-1)^ny^{2n}$$
Integrating both sides gives us the infinite expansion for $arctan(y)$
$$ arctan(y)=\sum_{n=0}^{\infin} {(-1)^ny^{2n+1} \over 2n+1}=y-{y^3 \over 3}- {y^5 \over 5} +{y^7 \over 7}- {y^9 \over 9} + \ldots$$
which we can use to calculate the two arctangets to twenty decimal places.
## A precise formula for calculating $\pi$
$$ {\pi \over 4}=4*arctan({1 \over 5})-arctan({1 \over 239})$$
$$ {\pi \over 4}=4\{{1 \over 5}-{1 \over 3.5^3}+{1 \over 5.5^5}-{1 \over 7.5^7}+ \ldots\}-\{{1 \over 239}-{1 \over 3.239^3}+{1 \over 5.239^5}-{1 \over 7.239^7}+ \ldots\}$$

We will need to calculate as far as $1 \over 29*5^{29} $ and $1\over 9*239^9$ to get 20 digits accuracy.

$$ {1\over29.5^{29}}={5\over29}*{1\over5^{30}}={5\over29}*\{{2 \over 10}\}^{30}= {5\over29}*{(2^{10})^3 \over 10^{30} }={5\over29}* {1024^3\over10^{30}}\approx {5\over30}*{1000^3\over10^{30}}={1\over6}*10^{-21}\approx 1.7*10^{-22}$$

$${1\over 9*239^9} \approx{1\over 10* 200^9}={1\over2^9}*10^{-19}={2\over2^{10}}*10^{-19}\approx{2\over1000}*10^{-19}=2*10^{-22}$$
We will calculate everything to 22 decimal places, which will give us certainty that the 20th decimal place is correct.

## Some tricks to efficiently perform long division and validate your work
It is very easy to make calculation errors when performing long division. We need to constantly check our work to ensure we have made no errors.
### Dividing by 5 is very easy!
Note that ${1\over 5}={2 \over 10} $, so dividing by 5 is the same as doubling and shifting the decimal place!
$${1\over5}={2\over10}=0.200,000,000$$
$${1\over5^2}={2^2\over10^2}=4/100=0.040,000,000$$
$${1\over5^8}={2^8\over10^8}=256/10^{-8}=0.000,002,560$$
$${1\over5^{10}}={2^{10}\over10^{10}}=1024/10^{-10}=0.000,000,102,400$$
You can use the sequence 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048, etc to quickly calculate $1\over5^n$.

### A quick way to multiply by $2^{10}$.
Notice that $2^{10}=1024$ only contains the digits 1, 2 and 4. Each is double the previous.
Therefore
$$x*2^{10}=x*1024=x*1000+(x*2)*10+(x*4)$$
Example. $4345*2=8690$ and $8690*2=17,380$
$$ 4345 * 1024= 4345*1000 + 8690*10+17380 $$
$$=4,345,000 + 86,900 + 17,380=4,449,280$$

Once you have calculated $1\over5^{19}$, you can calculate ${1\over5^{19}}*2^{10}={1\over5^{9}}$. In this way you can quickly check that each value from n=11 to n=29 matches the value 10 before it.
### A quick way to multiply by 239
239=240-1, which also only contains 1, 2 and 4. This saves us a lot of calculations when dealing with 22 decimal places! We only have to multiply by 2 twice. We don't have to multiply by 2, 3 and 9.


$$239*x=(240-1)*x = (x*2)*100 +(4*x)*10-x $$
    
for example $185*2=370$ and $185*4=740$.
$$185*239=185*(200+40-1)$$
$$=370*100+740*10-185$$
$$=37,000+7,400-89=44,400-85=44,215$$






 
