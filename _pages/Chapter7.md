---
layout: page
title: Chapter 7
permalink: /chapter-7/
---



# Chapter 7 Problems (Baltagi)

### 7.1.

​	*Invariance of the Fitted Values and Residuals to Nonsingular Transformations of the Independent variables* Post-Multiply the independent variables in (7.1) by a nonsingular transformation $$C$$, so that $$X* = XC$$.



**(7.1) provided below:**


$$
y = X\beta + u
$$


-----

**(a) Show that $$P_x^* = P_x$$ and $$\bar{P_x^*} = \bar{P_x}$$. Conclude that the regression of y on $$X$$ has the same fitted values and the same residuals as the regression of $$y$$ on $$X^*$$**



First, note the structure of the projection matrix:
$$
P_X = X(X'X)^{-1}X'
$$
Now, plugging $$X*$$ for $$X$$ yields the following result: 


$$
\begin{align*}

P_{X^*} &= XC((XC)'(XC))^{-1}(XC)'\\
&= XC[C'X'XC]^{-1}(XC)' \\
&= XC[C'X'XC]^{-1}(XC)'\\
&= XC[C^{-1}X^{-1}X'^{-1}C'^{-1}]C'X' \\
&= XCC^{-1}X^{-1}X'^{-1}C'^{-1}C'X'\\
&= XCC^{-1}(X^{-1}X'^{-1})C'^{-1}C'X' \\
&= XCC^{-1}(X'X)^{-1}C'^{-1}C'X' \\
&= X(X'X)^{-1}X'

\\
\blacksquare
\end{align*}
$$


Note that $$\bar{P}_X = (I-P_X)$$, Thus, we have already shown that $$\bar{P}_X = \bar{P}_{X*}$$



Finally, consider the fitted values of the regression $$y$$ on $$X$$, i.e. $$\hat{y}$$. 

----

> **Note**

$$
y = X\hat{\beta} + e \\
$$

$$
e = y - X\hat{\beta}_{OLS}
$$



> *It's helpful to consider here that  we can denote the error $$e$$ as:*

$$
e = y - \hat{y}
$$



> Thus, the fitted value is 

$$
\hat{y} = X\hat{\beta}_{OLS}
$$

-----



From normal equation (7.3): 

$$
\begin{align*}

X'X\hat{\beta} &= X' Y \\
\hat{\beta} &= (X'X)^{-1}X'Y 

\end{align*}
$$


By plugging in  $$\hat{\beta}$$
$$
\begin{align*}
\hat{y} &= X\hat{\beta}_{OLS} \\
\hat{y} &= X(X'X)^{-1}XY  \\
\hat{y} &= P_XY
\end{align*}
$$
From above, $$P_{X^*} = P_X$$.



From the above note, we can see also that the residuals $$e$$ do not change as y on X* and y on X maintain the same dependent variable, such that.


These results imply the invariance of fitted values and residuals to nonsingular transformations of the independent variables.



----





**(b) As an application of these results, suppose that every X was multiplied by a constant, say, a change in the units of measurement. Would the fitted values or residuals change when we rerun the regression?**



Multiplying the independent variable by a constant (diagonal matrix) indicates a nonsingular transformation of the independent variables. We have shown in (a) that these transformations have no effect on the fitted values/residuals.



**(c) Suppose that X contains two regressors $$X_1$$ and $$X_2$$ each of dimension $$n \times 1$$. If we run the regression of $$y$$ on $$(X_1 -X_2)$$ and $$(X_1 + X_2)$$, will these yield the same fitted values and the same residuals as the original regression of y on $$X_1$$ and $$X_2$$?**



By intuition, we might assume that $$(X_1 -X_2)$$ and $$(X_1 + X_2)$$ are nonsingular transformations of X. Let's show this with matrices:



First, note that originally,  $$X = [X_1, X_2]$$. Now, we can consider the transformation provided above by  $$X^* = [X_1-X_2,X_1+X_2]$$. 



Rewrite this using matrix algebra:


$$
\underset{n \times 2}X^* =[X_1,X_2] 

\begin{bmatrix} 
1 & 1 \\
-1 & 1
\end{bmatrix}
$$


Define $\begin{vmatrix} 
1 & 1 \\
-1 & 1
\end{vmatrix}$ as C. Such that $X^* = XC$. From (a) we know that nonsingular transformations of independent variables have the same fitted values and residuals.

$\blacksquare$



### 7.2 

*The FWL Theorem*



**(a) Using partitioned inverse results from the Appendix, show that the solution to (7.9) yield $$\hat{\beta_2}_{OLS}$$ given in (7.10)** 



> I will develop this answer in depth below, feel free to skip



The inverse of a partitioned matrix 


$$
A = \begin{bmatrix}
A_{11} & A_{12}\\
A_{21} & A_{22}
\end{bmatrix}
$$


is:
$$
A^{-1} = \begin{bmatrix}
A_{11}^{-1}+A_{11}^{-1}A_{12}FA_{21}A_{11}^{-1} & -A_{11}^{-1}A_{12}F\\
-FA_{21}A_{11}^{-1} & F
\end{bmatrix}
$$
Where $F = (A_{22}-A_{21}A_{11}^{-1}A_{12})^{-1}$

Here we will consider the partitioned matrix provided in (7.9)


$$
\begin{bmatrix}
X_{1}'X_{1} & X_{1}'X_{2}\\
X_{2}'X_{1} & X_{2}'X_{2}
\end{bmatrix}


\begin{bmatrix}
\hat{\beta_{1,OLS}}\\
\hat{\beta_{2,OLS}}
\end{bmatrix} = 

\begin{bmatrix}
X_{1}'y\\
X_{2}'y
\end{bmatrix}
$$


----

> **Digression on Matrix Properties:**
>
> To solve a system of equations using the inverse of a matrix A, note the following property:

$$
AX = B\\
A^{-1}A{X}=A^{-1}B\\
X = A^{-1}B
$$

> Also note that if $$X = \begin{bmatrix} x_1 \\x_2  \end{bmatrix}$$, we can solve for only $$X_2$$:
> 
>$$
> \begin{align*}A^{-1} &= \begin{bmatrix}
> A_{11} & A_{12}\\
> A_{21} & A_{22}
> \end{bmatrix}
> 
> 
> 
> 
> 
> \end{align*}
> $$
> Then

$$
\\ \begin{bmatrix} b_1 \\b_2  \end{bmatrix} =  \begin{bmatrix}
A_{11} & A_{12}\\
A_{21} & A_{22}
\end{bmatrix}\begin{bmatrix} x_1 \\x_2  \end{bmatrix} \\
$$

> Such that $$b_1 = A_{11}x_1+A_{12}{x_2}$$ and $$b_2 = A_{21}x_1+A_{22}{x_2}$$



**End Digression**

----

Using the partitioned matrix 
$$
A = \begin{bmatrix}
X_{1}'X_{1} & X_{1}'X_{2}\\
X_{2}'X_{1} & X_{2}'X_{2}
\end{bmatrix}
$$
We can find the inverse using the inverse results provided above: However we can note that from the properties discussed in the digression above, we can solve for $\hat{\beta_{2,OLS}}$ considering only the bottom row of $A^{-1}$

i.e.
$$
A^{-1} = \begin{bmatrix}
A_{11}^{-1}+A_{11}^{-1}A_{12}FA_{21}A_{11}^{-1} & -A_{11}^{-1}A_{12}F\\
-FA_{21}A_{11}^{-1} & F
\end{bmatrix}
$$


Where $$F = (A_{22}-A_{21}A_{11}^{-1}A_{12})^{-1}$$



Solving for $$F = (A_{22}-A_{21}A_{11}^{-1}A_{12})^{-1}$ using $A$$ above:


$$
\begin{align*}
F &= (X_2'X_2-X_2'X_1(X_1'X_1)^{-1}X_1'X_2)^{-1} \\
 &= (X_2'X_2-X_2'P_XX_2)^{-1} \\
 &= (X_2'(X_2-P_XX_2))^{-1}\\
 &= (X_2'(I-P_X)X_2)^{-1} \\
 &= (X_2'\bar{P_X}X_2)^{-1}
\end{align*}
$$
Similiarly, solving for $-FA_{21}A_{11}^{-1}$ yields 
$$
-(X_2'\bar{P_X}X_2)X_2'X_2(X_1'X_1)^{-1}
$$
Thus:
$$
\begin{bmatrix}
\hat{\beta}{_{1,OLS}}\\
\hat{\beta}{_{2,OLS}}
\end{bmatrix} =

\begin{bmatrix}
blah & blah \\
-(X_2'\bar{P_X}X_2)X_2'X_2(X_1'X_1)^{-1} & (X_2'\bar{P_X}X_2)^{-1} 
\end{bmatrix}

\begin{bmatrix}
X_{1}'y\\
X_{2}'y
\end{bmatrix}\\
$$

$$
\begin{align*}

\hat{\beta}_{2,OLS} &= (X_2'\bar{P_X}X_2)^{-1}X_{2}'y-(X_2'\bar{P_X}X_2)X_2'X_2(X_1'X_1)^{-1}X_{1}'y \\

&= (X_2'\bar{P}_XX_2)^{-1} +X_2'\bar{P}_Xy
\end{align*}
$$

*By factoring*



**(b) Alternatively, write (7.9) as a system of two equations in two unknowns $$\hat{\beta}_{1,OLS}$$ and $$\hat{\beta}_{2,OLS}$$. Solve, by eliminating $$\hat{\beta}_{1,OLS}$$ and show that the resulting solution is given by (7.10)**


$$
\begin{align*} \begin{bmatrix}
X_{1}'X_{1} & X_{1}'X_{2}\\
X_{2}'X_{1} & X_{2}'X_{2}
\end{bmatrix}

\begin{bmatrix}
\hat{\beta}{_{1,OLS}}\\
\hat{\beta}{_{2,OLS}}
\end{bmatrix} 
&= 

\begin{bmatrix}
X_{1}'y\\
X_{2}'y
\end{bmatrix}
\\
\end{align*}
$$

Written as
$$
X_{1}'X_{1}\hat{\beta}{_{1,OLS}}+X_{1}'X_{2}\hat{\beta}{_{2,OLS}} = X_1'y \\
X_{2}'X_{1}\hat{\beta}{_{1,OLS}}+X_{2}'X_{2}\hat{\beta}{_{2,OLS}} = X_2'y \\
$$

To isolate $ \hat{\beta}{_{1,OLS}} $, premultiply. by $(X_1'X')^{-1}$, then rearrange
$$
\begin{align*}
(X_1'X')^{-1}(X_{1}'X_{1}\hat{\beta}{_{1,OLS}}+X_{1}'X_{2}\hat{\beta}{_{2,OLS}} &= X_1'y )\\
\hat{\beta}{_{1,OLS}}+(X_1'X')^{-1}X_{1}'X_{2}\hat{\beta}{_{2,OLS}} &= (X_1'X')^{-1}X_1'y \\
\hat{\beta}{_{1,OLS}} &= (X_1'X')^{-1}X_1'y -(X_1'X')^{-1}X_{1}'X_{2}\hat{\beta}{_{2,OLS}}\\
&=(X_1'X')^{-1}X_1'(y-X_{2}\hat{\beta}{_{2,OLS}})
\end{align*}
$$

Now, plug into second equation

$$
\begin{align*}
X_{2}'X_{1}((X_1'X')^{-1}X_1'y -(X_1'X')^{-1}X_{1}'X_{2}\hat{\beta}{_{2,OLS}}) +X_{2}'X_{2}\hat{\beta}{_{2,OLS}} &= X_2'y \\


X_{2}'X_{1}(X_1'X')^{-1}X_1'y-X_{2}'X_{1}(X_1'X')^{-1}X_{1}'X_{2}\hat{\beta}{_{2,OLS}}+ X_{2}'X_{2}\hat{\beta}{_{2,OLS}} &= X_2'y \\


X_{2}'X_{1}(X_1'X')^{-1}X_1'y -X_2'{P}_{X_1}X_2\hat{\beta}{_{2,OLS}}+X_{2}'X_{2}\hat{\beta}{_{2,OLS}} &= X_2'y \\

X_{2}'X_{2}\hat{\beta}{_{2,OLS}}- X_2'{P}_{X_1}X_2\hat{\beta}{_{2,OLS}} &= X_2'y -X_{2}'X_{1}(X_1'X')^{-1}X_1'y\\


(X_{2}'X_{2}-X_2'{P}_{X_1}X_2)\hat{\beta}{_{2,OLS}}&=X_2'y -X_{2}'X_{1}(X_1'X')^{-1}X_1'y\\


(X_2'(X_{2}-{P}_{X_1}X_2))\hat{\beta}{_{2,OLS}}&=X_2'y -X_{2}'X_{1}(X_1'X')^{-1}X_1'y\\


\hat{\beta}{_{2,OLS}} &= (X_2'\bar{P}_{X_1}X_2)^{-1}X_2'\bar{P}_{X_1}y
\end{align*}
$$

**(c) Using FWL, show that if $X_1=\iota_n$ a vector of ones indicating the presence of a constant. Then (i)  $$\hat\beta_{2,OLS}$$ can be obtained by running $$y_i - \bar{y}$$ on the set of variables in $$X_2$$ expressed as deviations from their respective sampole means (ii) The least squares estimate of the constant $$\hat\beta_{1,OLS}$$ can be retrieved as $$\bar{y} -\bar{X_2}'\hat{\beta}_{2,OLS} $$ where $$\bar{X}_2'=\iota_n'X_2/n$$ is in the vector of sample means of the independent variables in $$X_2$$.**



For (i) Note that FWL indicates that the estimates of $\beta$ and $u$ are the same for both the regression above 
$$
y = X_1\beta_1 + X_2\beta_2+u
$$
 

and
$$
\bar{P}_{X_1}y = \bar{P}_{X_1}X_2\beta_2+\bar{P}_{X_1}u
$$

We know that from the problem above:

$$
X_1 = \iota_n = 

\begin{bmatrix}
1 & 1 & ... &1
\end{bmatrix}'
$$

Then 
$$
\begin{align*}
{P}_{X_1} &= \iota(\iota'\iota)^{-1}\iota'




\end{align*}
$$


Note the dimensions of $$\underset{n \times 1}\iota$$, such that $$\underset{1 \times n}\iota'\underset{n \times 1}\iota$$ is a scalar of size $$n$$. The inverse of this scalr is $$n^{-1}$$ or $$\frac{1}{n}$$.  Now, note that $$\underset {n \times 1} \iota  \ \underset {1 \times n} \iota' $$ is an $$n \times n$$ matrix of 1's. such that $$(\iota \iota')y$$ is $$\sum_{i=1}^n y_i$$  Putting it all together 


$$
(\iota'\iota)^{-1}\iota'y
$$

> Is equal to (FIX THIS)

$$
\begin{align*}

&= \frac{\sum_{i=1}^n y_i}{n}
\\
&=\bar{y}

\end{align*}
$$



> And by distributing y:

$$
\begin{align*}

\bar{P}_{X_1}y
\\

&=(I-\iota(\iota'\iota)^{-1}\iota')y
\\
&= y_i-\bar{y}

\end{align*}
$$



> Similiarly, $$\bar{P}_{X_1}X_2\beta_2 = (\bar{X_2}-X_2)\beta_2$$





> and we have shown 

$$
y_i-\bar{y} = ({X_2}-\bar{X_2})\beta_2 +(u-\bar{u})
$$

We have found that the estimate of $\hat\beta_{2,OLS}$ can be optained by running $y_i - \bar{y}$ on the set of variables in $X_2$ expressed as deviations from their respective sampole means.



---

For (ii)



We derived 
$$
\hat{\beta}{_{1,OLS}} =(X_1'X_1)^{-1}X_1'(y-X_{2}\hat{\beta}{_{2,OLS}})
$$
In 7.2.b. 



For $X_1 = \iota$:

$\frac{\iota'}{n}(y-X_2' \hat{\beta}_{2,OLS})= \bar{y}-\bar{X_2}'\hat{\beta}_{2,OLS}$ 



---



CRUCIAL NOTE FOR 7.5


$$
\begin{align*}

s^2 = MSE &= \frac{RSS}{df} = \frac{RSS}{(n-k)}

\\
s^2(n-k)&=RSS
\\
\hat{\sigma}^2_{mle} &= \frac{RSS}{n} 

\\

\hat{\sigma}^2_{mle} &= \frac{s^2(n-k)}{n}

\\
\end{align*}

$$


