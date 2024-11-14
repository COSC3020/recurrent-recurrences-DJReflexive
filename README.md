# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$


# My Analysis

#### All of these are very similar to eachother, but there are slight differences in each. All three examples have a base case where if $n \le 1$ it returns 1, a constant.


### 1.

$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Taking the equation $T\left(\frac{n}{13}\right) + 5$, let's expand it out a few iterations to begin to find a pattern:

$$T(n) = T(\frac{n}{13}) + 5$$
$$T(n) = (T(\frac{n}{13^2}) + 5) + 5$$
$$T(n) = ((T(\frac{n}{13^3}) + 5) + 5 ) + 5$$

With these iterations, we can assume the following pattern:

$$T(n) = T(\frac{n}{13^k}) + 5k$$

Now plug in $k = \log_{13}n$:

$$T(n) = T(1) + 5\log_{13}n$$

Since $T(1)$ is a constant time operation, then $T(1) = \Theta(1)$.\
Simplify:

$$T(n) \in \Theta(1) + 5\log_{13}n$$
$$T(n) \in \Theta(\log{n})$$



### 2.

$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Taking the equation $13T\left(\frac{n}{13}\right) + 5$, let's expand it out a few iterations to begin to find a pattern:

$$T(n) = 13T(\frac{n}{13}) + 5$$
$$T(n) = 13(13T(\frac{n}{13^2}) + 5) + 5$$
$$T(n) = 13(13(13T(\frac{n}{13^3}) + 5) + 5 ) + 5$$

With these iterations, we can assume the following pattern:

$$T(n) = 13^k * T(\frac{n}{13^k}) + 5k$$

Now plug in $k = \log_{13}n$:

$$T(n) = n * T(1) + 5\log_{13}n$$

Since $T(1)$ is a constant time operation, then $T(1) = \Theta(1)$.\
Simplify:

$$T(n) \in n * \Theta(1) + 5\log_{13}n$$
$$T(n) \in \Theta(n)$$




### 3.

$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

Taking the equation $13T\left(\frac{n}{13}\right) + 2n$, let's expand it out a few iterations to begin to find a pattern:

$$T(n) = 13T(\frac{n}{13}) + 2n$$
$$T(n) = 13(13T(\frac{n}{13^2}) + 2n) + 2n$$
$$T(n) = 13(13(13T(\frac{n}{13^3}) + 2n) + 2n) + 2n$$

With these iterations, we can assume the following pattern:

$$T(n) = 13^k * T(\frac{n}{13^k}) + 2nk$$

Now plug in $k = \log_{13}n$:

$$T(n) = n * T(1) + 2n*\log_{13}n$$

Since $T(1)$ is a constant time operation, then $T(1) = \Theta(1)$.\
Simplify:

$$T(n) \in n * \Theta(1) + 2n * \log_{13}n$$
$$T(n) \in \Theta(n + 2n * \log_{13}n)$$
$$T(n) \in \Theta(n \log{n})$$



# Sources

- My previous assignment "Recurence Analysis" for a refresher

# Plagiarism

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.