---
{"dg-publish":true,"permalink":"/01/linear-algebra-manual/","tags":["gardenEntry"]}
---

# Before Reading

## What

This manual is for linear algebra study, especially for undergraduates.

The main concepts, theorems and methods covered are as follows:

1. Linear system


## Why

To teach is the best way to learn, so I write this manual to further my understanding of linear algebra. Nevertheless, I would be glad if this manual could help those who also struggles in linear algebra.

I also want to explain that why am I using English all through this manual despite my catastrophic English writing ability: GZIC is a campus that dedicates to implement localized globalization from the very day it is established, therefore undergraduates here should embrace this intention.

## When

Whenever you feel resistance learning linear algebra, a few pages of reading might do some help. 

## How

For more references and further study, see:
1. [MIT 18.06 Linear Algebra, Spring 2005 YouTube Playlist](https://www.youtube.com/playlist?list=PLE7DDD91010BC51F8)
2. [Linear Algebra | Mathematics | MIT Open Course Ware](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)
3. [3Blue1Brown ](https://www.3blue1brown.com/topics/linear-algebra)
4. [*Linear Algebra and Its Application (Fifth Edition)* David C. Lay](https://api.pageplace.de/preview/DT0400.9781292092249_A26575335/preview-9781292092249_A26575335.pdf) 
6. [*Linear Algebra Done Right (Fourth Edition)* Sheldon Axler](https://linear.axler.net/LADR4e.pdf)

## Who

<andrew05@foxmail.com>

# 1 Linear System

## 1.0 Vocab

1. first understanding for linearity
2. second understanding for linearity
## 1.1 Linearity

### 1.1.1 First understanding

You might be familiar with the concept *linear*, your first impression of this concept might be equations with variables to the power of 1, which illustrates a line in a rectangular coordinate system. That is the **first understanding for linearity**, which is quite direct, as is shown in fig.1.1.

![Pasted image 20241217203855.png](/img/user/Attachment/Pasted%20image%2020241217203855.png)
$$2x_{1}-x_{2}=3\tag{1-1}$$

The graph for a linear equation is a line, obviously. Wait, is this rigorous? For an equation with three variables, this might still be true. A line in a three dimensional space is still imaginable. But nobody can illustrate a four dimensional space, let alone defining a "line" in it. So for linear equations with more than 3 variables, the **first understanding for linearity** might not hold true. Thus we need to implement another understanding for linearity.

Before that, we need to introduce the following concept: [[01/Linear Algebra Manual#^7c7b7a\|linear system]]. 

>When learning linear algebra, please always bring abstract definition into simple cases. 

As an example, let's give a brief example of one *linear system*:
$$
\begin{cases}
1x_{1}+3x_{2}=5\\ 
2x_{1}+1x_{2}=5 
\end{cases}\tag{1-2}
$$
No doubt that you can still draw two line in a 2D space and find a specific intersection point and claim you have found that unique solution $\begin{cases}x_{1}=2\\x_{2}=1\end{cases}$. But what if we look at the *linear system* vertically? You see, by examining the system vertically, the benefit is that the unknowns are categorized. So now we may express the first column in briefer notation:
$$
x_{1}\begin{bmatrix}
1\\2
\end{bmatrix}\tag{1-3}
$$
Thus, (1-2) can be written as
$$
x_{1}\begin{bmatrix}
1\\2
\end{bmatrix}+x_{2}\begin{bmatrix}
3\\1
\end{bmatrix}=\begin{bmatrix}
5\\5
\end{bmatrix}\tag{1-2*}
$$
Please still keep in mind that this is only for brief notation, don't attach any meaning to it in a hurry. For now, we just want to avoid writing the same unknowns ($x_{1},x_{2},\dots$) repeatedly.

But hey, why not call these $\begin{bmatrix}1\\2\end{bmatrix},\begin{bmatrix}3\\1\end{bmatrix},\begin{bmatrix}5\\5\end{bmatrix}$ stuffs a [[01/Linear Algebra Manual#^293950\|vector]]?

### 1.1.2 Second understanding

>One golden rule for learning linear algebra is try to visualize what is going on.

We might be familiar with the geometric description of vectors in high school (fig.1.2), as $\mathbf{u}=\begin{bmatrix}1\\2\end{bmatrix},\mathbf{v}=\begin{bmatrix}3\\1\end{bmatrix},\mathbf{w}=\begin{bmatrix}5\\5\end{bmatrix}$. We also know the [[01/Linear Algebra Manual#^8e681d\|dot product]] scales a vector by zooming or squishing. So $2\mathbf{u}=\begin{bmatrix}2\\4\end{bmatrix},1\mathbf{v}=\begin{bmatrix}3\\1\end{bmatrix}$ (fig.1.3). I don't bother to explain the [[01/Linear Algebra Manual#^e08cc2\|vector addition]], but when you do add $2\mathbf{u}$ and $1\mathbf{v}$ together. Guess what, you get $\mathbf{w}$! So when you look back at the *linear system* (1-2), **the solution set is the set of scalers**.

fig.1.2![Pasted image 20241217164441.png](/img/user/Attachment/Pasted%20image%2020241217164441.png)

fig.1.3![Pasted image 20241217170134.png](/img/user/Attachment/Pasted%20image%2020241217170134.png)

So if we look at this *linear system* once again
$$
x_{1}\begin{bmatrix}
1\\2
\end{bmatrix}+x_{2}\begin{bmatrix}
3\\1
\end{bmatrix}=\begin{bmatrix}
5\\5
\end{bmatrix}\tag{1-2*}
$$
Solving it amounts to find out how to produce the targeted vector $\begin{bmatrix}5\\5\end{bmatrix}$ by the given vectors $\begin{bmatrix}1\\2\end{bmatrix}$ and $\begin{bmatrix}3\\1\end{bmatrix}$. 

Now reflecting on two kinds of operations: *scaling* and *addition*. These are the make up of [[01/Linear Algebra Manual#^857296\|linear combination]]. Finally, here comes **the second understanding for linearity**, that is, doing [[01/Linear Algebra Manual#^4dbac7\|linear operations]] to vectors.

>Linear combination is the essence of linear algebra.

### 1.1.3 Summarize

We seemed to waste a lot of time chattering about trivial matters

# 0 Rigorous Definition Library

Linear system: a set of equations in the following form
{ #7c7b7a}

$$
\begin{cases}
a_{11}x_{1}+a_{12}x_{2}+\dots+a_{1n}x_{n}=b_{1}\\ 
a_{21}x_{1}+a_{22}x_{2}+\dots+a_{2n}x_{n}=b_{2} \\ 
\dots\\
a_{n1}x_{1}+a_{n2}x_{2}+\dots+a_{nn}x_{n}=b_{n}
\end{cases}
$$

---
Vectors (Column Vectors): a vertical array of numbers in the following form
{ #293950}

$$
\mathbf{v}=\begin{bmatrix}x_{1}\\x_{2}\\\vdots\\x_{n}\end{bmatrix}
$$

---
Dot product: scaling a vector by a constant which is called a *scaler*
{ #8e681d}

$$
c\cdot \mathbf{v}=\begin{bmatrix}cx_{1}\\cx_{2}\\\vdots\\cx_{n}\end{bmatrix}
$$

Scalar: the constant in scaling

---
Vector addition: adding vectors by entries
{ #e08cc2}

$$
\mathbf{v}+\mathbf{u}=\begin{bmatrix}x_{1}\\x_{2}\\\vdots\\x_{n}\end{bmatrix}+\begin{bmatrix}y_{1}\\y_{2}\\\vdots\\y_{n}\end{bmatrix}=\begin{bmatrix}x_{1}+y_{1}\\x_{2}+y_{2}\\\vdots\\x_{n}+y_{n}\end{bmatrix}
$$
---
Linear combination: combine a group of vectors through *linear operations*
{ #857296}

$$
c_{1}\mathbf{v}_{1}+c_{2}\mathbf{v}_{2}+\dots+c_{n}\mathbf{v}_{n}
$$

Weights: scalars in a linear combination

Linear operation: scaling and addition of vectors
{ #4dbac7}


---

