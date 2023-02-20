# Calculate $\pi$ by hand to 20 decimal places
Here is a simple and efficient method for calculating pi to 20 decimal places, using just paper and pencil - NO CALCULATOR ALLOWED!  You do not have to calculate square roots like Newton did!  
20 decimal places of $\pi$ corresponds to 60 nanometers along the orbit of Pluto!   
With focus you should be finished in a few hours. 
You only need to know how to calculate long division.  
To follow the Mathematics you need to understand Complex Numbers, Calculus and Geometric Series. Only very basic Trigonomety is required. Complex Numbers let us to avoid trigonometric [Angle Sum formulae](https://en.wikipedia.org/wiki/List_of_trigonometric_identities#Angle_sum_and_difference_identities).

## Machin Formula (1706)

We will use the tangent of an angle function, which is defined as
$$tan(angle)={sin(angle) \over cos (angle)}={rise \over run}=slope, \space angle \ne \pm 90 \degree, \space run \ne 0$$
Inverting gives us the arctan function which we will need.
$$angle=arctan(slope)$$

The slope $1 \over 5$, which is $5+i$ in complex numbers, has an angle of about $11.3 \degree$. Rotating by this angle 4 times is just over $45 \degree$. Let's calculate this slope with complex numbers. 
$$(5+i)^4$$
$$=(25+2*5i+i^2)^2=(24+10i)^2(1-i)=2^2(12+5i)^2$$
$$=4(144-25+2*60i)=4(119+120i)$$

We have just found that 4 times a slope of $1 \over 5$ is a slope of $120 \over 119$, which is just slightly steeper than ${1\over1} = 45\degree$. Let's rotate by $-45 \degree=(1-i)$ from this slope to find that tiny angle.
$$(119+120i)(1-i)$$
$$=(119-119i+120i-120i^2)$$
$$=239+i$$
This number ${1\over 239}$ is the very small slope we have been looking for. It is an angle about $ 0.24 \degree$.
We have calculated that
$$ tiny\space angle= 4 \space arctan({1 \over 5})-arctan({1\over 1})=arctan({1 \over 239})$$
We know that $arctan(1)=45 \degree ={\pi \over 4}$ which gives us
$$ 4\space arctan({1 \over 5})-{\pi \over 4}=arctan({1 \over 239})$$
Rearranging gives us the [famous formula](https://en.wikipedia.org/wiki/Machin-like_formula) found by John Machin in 1706.
$$ {\pi \over 4}=4 \space arctan({1 \over 5})-arctan({1 \over 239})$$
We will use this formula to calculate $\pi$ to 20 decimal places.  

## Approximating the Arctanget function

By definition of inverse functions
$$arctan(tan(x))=x, \space x \in (-{\pi \over 2},{\pi \over 2})$$
Differentiating and using the [Chain Rule](https://en.wikipedia.org/wiki/Chain_rule) gives
$$arctan'(tan(x)).tan'(x)=1 $$
Applying the [Quotient Rule](https://en.wikipedia.org/wiki/Quotient_rule)
$$tan'(x)={d \over dx}({sin(x) \over cos(x)})={sin'(x).cos(x)-sin(x).cos'(x) \over cos^2(x)} $$
$$={cos^2(x)+ sin^2(x)\over cos^2(x)}={cos^2(x) \over cos^2(x)}+ {sin^2(x) \over cos^2(x)} $$
which gives us the nice identity
$$tan'(x)= 1 + tan^2(x) $$
Therefore
$$arctan'(tan(x)).(1+tan^2(x))=1$$
$$arctan'(tan(x))={1 \over 1+tan^2(x) }$$
Letting $y=tan(x)$ gives us the pretty identity
$$ arctan'(y)={ 1 \over 1+y^2} $$
By inspection, this is the sum of the [Geometric Series](https://en.wikipedia.org/wiki/Geometric_series) of $-y^2$
 $$arctan'(y)= { 1 \over 1-(-y^2)}$$
$$ arctan'(y)=\sum_{n=0}^{\infin} (-y^2)^n=\sum_{n=0}^{\infin} (-1)^ny^{2n}, \space |y| < 1$$
Integrating both sides gives us the infinite expansion for $arctan(y)$
$$ arctan(y)=\sum_{n=0}^{\infin} {(-1)^ny^{2n+1} \over 2n+1}=y-{y^3 \over 3}- {y^5 \over 5} +{y^7 \over 7}- {y^9 \over 9} + \ldots, \space |y| < 1$$
which we can use to calculate the two arctangets to twenty decimal places.
## A precise formula for calculating $\pi$
$$ {\pi \over 4}=4 \space arctan({1 \over 5})-arctan({1 \over 239})$$
$$ {\pi \over 4}=4\{{1 \over 5}-{1 \over 3.5^3}+{1 \over 5.5^5}-{1 \over 7.5^7}+ \ldots\}-\{{1 \over 239}-{1 \over 3.239^3}+{1 \over 5.239^5}-{1 \over 7.239^7}+ \ldots\}$$

We will need to calculate as far as $1 \over 29*5^{29} $ and $1\over 9*239^9$ to get 20 digits accuracy.

$$ {1\over29.5^{29}}={5\over29}*{1\over5^{30}}={5\over29}*\{{2 \over 10}\}^{30}= {5\over29}*{(2^{10})^3 \over 10^{30} }={5\over29}* {1024^3\over10^{30}}\approx {5\over30}*{1000^3\over10^{30}}={1\over6}*10^{-21}\approx 1.7*10^{-22}$$

$${1\over 9*239^9} \approx{1\over 10* 200^9}={1\over2^9}*10^{-19}={2\over2^{10}}*10^{-19}\approx{2\over1000}*10^{-19}=2*10^{-22}$$
We will calculate everything to 22 decimal places, which will give us certainty that the 20th decimal place is correct.

## Some tricks to efficiently perform long division and validate your work
It is very easy to make calculation errors when performing long division. We need to constantly check our work to ensure we have made no errors.  
Below are two tricks that will enable you to quickly double-check that all 22 digits of $1\over5^n$ and $1\over239^n$ are correct.
### Dividing 1 by 5 repeatedly is very easy!
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

Once you have calculated $1\over5^{19}$, you can calculate
$${1\over5^{29}}={1\over5^{19}}*{2^{10}\over10^{10}}={1\over5^{19}}*1024 * 10^{-10}$$
In this way you can quickly calculate a number 10 further down the list by multiply by 1024 and shifting the decimal place 10 positions. If you also calculate them by successively dividing by 5, you have two independent methods of calculating each term, thus verifying all 22  digits for each number.
### A quick way to multiply by 239
After you have divided by 239, you should multiply by 239 to check you made no mistake.

239=240-1, which contains only 1, 2 and 4. This saves us a lot of calculations when dealing with 22 decimal places! We only have to multiply by 2 twice. We don't have to multiply by 200, 30 and 9 and then add.


$$239*x=(240-1)*x = (x*2)*100 +(4*x)*10-x $$
    
for example $185*2=370$ and $185*4=740$.
$$185*239=185*(2*100+4*10-1)$$
$$=370*100+740*10-185$$
$$=37,000+7,400-89=44,400-185=44,215$$
### Write out the 239 times table. You will need it!!
239 is a prime number, so we cannot simplify the division by using factors. Check it for yourself. Note that $15^2=225$, so if 239 were prime it would need to be divisible by one of 3, 5, 7, 11 or 13. It is easy to check they all fail.


Note that $239*5=239*3+239*2$. Calculate each term two different ways.  
Make sure that $239*9+239=2390$.  
If there are any mistakes in your 239 times table, all of your long divisions will be wrong and multiplying again by 239 will not get the starting number back.