---
title: Distributions
description: 'Chapter description goes here.'
---

## Distributions

```yaml
type: PureMultipleChoiceExercise
key: 840128d72b
xp: 50
```

The values of a quantitative variable are usually distributed in one of several ways, depending on the process that generates those values. [Click here to see different distributions](http://simple-tech.com/public_html/statistics/distributions.html).

Which of these distributions has mostly low values with a few high ones?

`@hint`


`@possible_answers`
- Normal
- [Geometric]
- Uniform
- Bernoulli

`@feedback`


---

## Uniform distribution

```yaml
type: PureMultipleChoiceExercise
key: b0025d5748
xp: 50
```

In a [uniform distribution](http://mathworld.wolfram.com/UniformDistribution.html) each value has an equal probability. For example, when you throw dice you have an equal chance of getting each value.

What is the chance of getting either one or six?

`@hint`
There are six possibilities uniformly distributed, so the chance of each is $\frac{1}{6}$. The two events, one and six, are mutually exclusive so the chance of either happening is the chance of one plus the chance of the other.

`@possible_answers`
- $0$, it cannot happen
- $\frac{1}{6}$
- [$\frac{1}{3}$]
- $\frac{1}{2}$
- $\frac{2}{3}$
- $\frac{5}{6}$
- $1$, it always happens

`@feedback`


---

## Adding uniformly distributed random variables

```yaml
type: MultipleChoiceExercise
key: 9ecf1e85b7
xp: 50
```

When you add multiple uniformly distributed variables, you get a distribution that has more entries in the middle than in the edges. For example, if you add the results of two dice throws, you get a graph like this one:

![Adding two dice](https://assets.datacamp.com/production/repositories/5515/datasets/7ea5ff962c69dcf1c150edeefb18b0be9b66ca75/two_dice.png)

Out of 36 possible results, there is only one that gives a sum of two (1+1) and only one that gives a sum of twelve (6+6). However, there are six possibilities for seven (1+6 all through 6+1). 

If we add three dice, the effect is even more pronounced. We get this graph:

![Adding three dice](https://assets.datacamp.com/production/repositories/5515/datasets/91de587281abb23156c84c55fc4c34449c56c927/three_dice.png)

Use Python to figure out the chance the chance that when you throw four dice you'll get a value of ten or less.

`@possible_answers`
- 0.2
- [0.3]
- 0.4
- 0.5

`@hint`
* You can simulate throwing a single die with `random.choice(range(1,6))`

`@pre_exercise_code`
```{python}
"""
import random

def die_throw():
	return random.choice(range(1,6))
  
  
def run_test():
	return die_throw()+die_throw()+die_throw()+die_throw() < 11
    
    
successes = 0
total_tests = 1000

for i in range(total_tests):
    if run_test():
        successes = successes+1
        
print (successes/total_tests)
"""
```

`@sct`
```{python}

```

---

## Towards the normal distribution

```yaml
type: PureMultipleChoiceExercise
key: 1cb9ff71b2
xp: 50
```

The [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem) states that as the number of random variables added increases the overall distribution gets closer and closer to the [normal distribution](https://en.wikipedia.org/wiki/Normal_distribution). 

Use the [distributions web page](http://simple-tech.com/public_html/statistics/distributions.html) to see what happens to the mean value when you use one random value in the (-1,1) range as opposed to adding two, ten, or a hundred.

`@hint`
To get the mean you add all the values together and divide by the number of values. If the variable is just one random number, and the distribution is a hundred values, then the mean value is the sum of a hundred random numbers divided by a hundred. If the variable is the sum of ten random numbers, and the distribution is a hundred values, then the mean value is the sum of a thousand random numbers divided by a thousand.

`@possible_answers`
- It gets smaller
- [It stays roughly the same]
- It gets bigger

`@feedback`


---

## The actual normal distribution

```yaml
type: PureMultipleChoiceExercise
key: 86a76077b7
xp: 50
```

The ideal normal distribution is the limit in case we add an infinite number of random values. When it is a [probability distribution](https://en.wikipedia.org/wiki/Probability_distribution) (meaning the total area is one unit) shape is controlled by two parameters: [the mean](https://en.wikipedia.org/wiki/Mean) and [the standard deviation](https://en.wikipedia.org/wiki/Standard_deviation). When the mean is zero and the standard deviation one, it is called the **standard normal distribution**.

[Click here for a calculator that shows what the normal distribution looks like](https://www.desmos.com/calculator/2kmx0enkkz). The parameter `b` is used for the mean, and `a` is used for the standard deviation. How do these values affects [the skew](https://en.wikipedia.org/wiki/Skewness)?

`@hint`


`@possible_answers`
- Increasing the mean increases the skew, but increasing the standard deviation decreases it
- Increasing the mean decreases the skew, but increasing the standard deviation increases it
- Increasing the mean or the standard deviation increases the skew
- Increasing the mean or the standard deviation decreases the skew
- Increasing the mean increases the skew, but changing the standard deviation has no effect on it
- Increasing the mean decreases the skew, but changing the standard deviation has no effect on it
- Increasing the standard deviation increases the skew, but changing the mean has no effect on it
- Increasing the standard deviation decreases the skew, but changing the mean has no effect on it
- [Neither the mean nor the standard deviation have any effect on the skew]

`@feedback`


---

## Bernoulli distribution

```yaml
type: PureMultipleChoiceExercise
key: e0fc54c120
xp: 50
```

The [Bernoulli distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution) gives the number of successful experiments out of $n$ when the probability of a single experiment being successful is $p$. Using either logic or experimentation with [the distributions page](http://simple-tech.com/public_html/statistics/distributions.html), figure out under what conditions, if any, the Bernoulli distribution approximates a normal distribution.

`@hint`


`@possible_answers`
- $p=0.5, n=1$
- [$p=0.5, n$ is high]
- $p=0.25, n=1$
- $p=0.25, n$ is high
- $p=0.75, n=1$
- $p=0.75, n$ is high
- It is impossible to approximate a normal distribution with a Bernoulli distribution.

`@feedback`


---

## Calculate the Bernoulli distribution

```yaml
type: NormalExercise
key: fd33c03b64
xp: 100
```



`@instructions`
Calculate the [Bernoulli distribution](https://en.wikipedia.org/wiki/Bernoulli_distribution) with $p=0.25, n=10$, and return it as a list of probabilities in the variable `bernoulliDist`.

`@hint`
- If we have $n$ experiments, the number of ways for $k$ of them to succeed is $\frac{n!}{k!(n-k)!}$.
- If an experiment has a $p$ likelihood of success, it has a $1-p$ likelihood of failure.

`@pre_exercise_code`
```{python}

```

`@sample_code`
```{python}

```

`@solution`
```{python}
import math

bernoulliDist = []
n = 10
nBang = math.factorial(n)
p = 0.25

for k in range(0,n+1):
  bernoulliDist.append (p**k * (1-p)**(n-k) * nBang/(math.factorial(k)*math.factorial(n-k)) )


```

`@sct`
```{python}
Ex().check_object("bernoulliDist").has_equal_value()
```

---

## Bernoulli distribution

```yaml
type: PureMultipleChoiceExercise
key: ec2e36cec4
xp: 50
```

If you increase $n$, how would that affect the mean of the Bernoulli distribution? What if you increase $p$?

`@hint`
If you don't want to think about it, experiment with [the distributions page](http://simple-tech.com/public_html/statistics/distributions.html).

`@possible_answers`
- [If you increase either $n$ or $p$, the mean number of successful experiments increases]
- If you increase either $n$ or $p$, the mean number of successful experiments decreases
- If you increase either $n$ or $p$, the mean does not change. But if you increase both $n$ and $p$ the mean increases
- If you increase either $n$ or $p$, the mean does not change. But if you increase both $n$ and $p$ the mean decreases

`@feedback`


---

## Geometric and exponential distributions

```yaml
type: MultipleChoiceExercise
key: fd60d9b6c9
xp: 50
```

The [geometric distribution](https://en.wikipedia.org/wiki/Geometric_distribution) is the number of experiments needed until one is successful when the probability of a successful experiment is $p$. The [exponential distribution](https://en.wikipedia.org/wiki/Exponential_distribution) is similar, but extended to be continuous.

Exponential distributions can also be defined by their [half life](https://en.wikipedia.org/wiki/Half-life). For example, if a certain medicine leaves the blood stream so that its half life in the blood is an hour, then $\int_{0}^{1} \lambda e^{-t\lambda} dt = 0.5 $. We don't need to actually do the integral, because somebody already did it for us. This is a frequency distribution, so we can use its [cumulative distribution function](https://en.wikipedia.org/wiki/Cumulative_distribution_function) to see that the amount that leaves the body until time $t$ is $1-e^{-\lambda t}$. In other words, $1-e^{-\lambda} = 0.5 \implies e^{-\lambda} = 0.5 \implies \lambda = ln(2) $.

Use either mathematics or a Python program to calculate how many times we'd expect to throw a pair of fair dice until we get snake eyes (both dice land on one, which happens $\frac{1}{36}$ of the time). Select the correct range.

`@possible_answers`
- 0-10
- 10-20
- 20-30
- [30-40]
- 40-50
- 50-60

`@hint`


`@pre_exercise_code`
```{python}
"""
import random

def throw():
  return random.random() < 1/36


def untilSnakeEyes():
  throws = 1
  while(not throw()):
    throws += 1
  return throws


numTests = 100

sum = 0
for i in range(numTests):
  sum += untilSnakeEyes()

print(sum/numTests)
"""
```

`@sct`
```{python}
# Check https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises on how to write feedback messages for this exercise.
```

---

## Poisson distribution

```yaml
type: PureMultipleChoiceExercise
key: c79f6d9d8f
xp: 50
```

The [Poisson distribution](https://en.wikipedia.org/wiki/Poisson_distribution) is the number of events the actually happen in a period of time when the events are randomly timed and the expected number of events in a period is $\lambda$. The probability of having k events happen is $Pois(k) = \frac{\lambda ^{k}e^{-\lambda}}{k!}$. 

A fisherman typically catches $3$   fish a day. Use the Poisson distribution to identify the chance that his family won't have any dinner tonight because he hasn't caught any fishes.

`@hint`
- $\lambda^{0} = 1$
- $0! = 1$

`@possible_answers`
- [< 5%]
- 5%-10%
- 10%-25%
- 25%-50%
- >50%

`@feedback`


---

## Classify distributions

```yaml
type: DragAndDropExercise
key: 8080a51946
xp: 100
```



`@instructions`
Identify which distributions are continuous (the results can be any number) and which discrete (the results are always an integer)

`@hint`


`@solution`
```{python}
- id: distributions
  title: "Distributions"

- id: cont
  title: "Continuous distributions"
  items: # Each drop zone has a list of items it contains. These will be shown in a random fashion.
    - content: "Normal"
      id: normal # ID of the item. This can be used in the SCTs.
    - content: "Exponential"
      id: exp

- id: disc
  title: "Discrete distributions"
  items:
    - content: "Geometric"
      id: geom
    - content: "Bernoulli"
      id: bernoulli
    - content: "Poisson"
      id: poisson
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(normal) == cont 
    incorrectMessage: "The normal distibution comes from summing up random variables, so it is continuous"
  - condition: check_target(exp) == cont 
    incorrectMessage: "Exponential distributions are continuous"
  - condition: check_target(geom) == disc 
    incorrectMessage: "The geometric distribution is the number of experiments until one is successful. The number of experiments is always an integer"    
  - condition: check_target(bernoulli) == disc 
    incorrectMessage: "The Bernoulli distribution is the number of successful experiments. The number of experiments is always an integer"
  - condition: check_target(poisson) == disc 
    incorrectMessage: "The Poisson distribution is the number of events during a period. The number of events is always an integer"
    
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```

---

## Distribution from graph

```yaml
type: DragAndDropExercise
key: 1036f6a342
xp: 100
```

In data science we typically have a large amount of data, and we need to understand what is happening.

`@instructions`
Identify the distribution type from the graph.

`@hint`


`@solution`
```{python}
- id: distributions
  title: "Distributions"

- id: normal
  title: "Normal Distribution"
  items: 
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/36b1e0fe08988dcedbcd2d2912f35efe2515cd6c/dist1.png)"
      id: dist1 # ID of the item. This can be used in the SCTs.
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/e2aee7123011c04b4dee766fa89d1e7c09b0a3ad/dist2.png)"
      id: dist2 # ID of the item. This can be used in the SCTs.  
      
- id: geom
  title: "Geometric Distribution"
  items: 
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/f9f641f19fd2b0a14f35ea1890d510486f8543c6/dist3.png)"
      id: dist3 # ID of the item. This can be used in the SCTs.
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/c49d51082b2ccf525a3fbd93096ed99931c44112/dist4.png)"
      id: dist4 # ID of the item. This can be used in the SCTs.        
      
- id: uniform
  title: "Uniform Distribution"
  items: 
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/276b97aabc4734e725b19c0aa44d36130415111d/dist5.png)"
      id: dist5 # ID of the item. This can be used in the SCTs.

- id: bernoulli
  title: "Bernoulli Distribution"
  items: 
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/5227f737b869bfd5bf15bfdf6444abc09f2690ef/dist6.png)"
      id: dist6 # ID of the item. This can be used in the SCTs.
    - content: "![](https://assets.datacamp.com/production/repositories/5515/datasets/065251afba3daba96980c65d4a9b6c89ce17f801/dist7.png)"
      id: dist7 # ID of the item. This can be used in the SCTs.      
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(dist1) == normal 
  - condition: check_target(dist2) == normal   
  - condition: check_target(dist3) == geom 
  - condition: check_target(dist4) == geom
  - condition: check_target(dist5) == uniform  
  - condition: check_target(dist6) == bernoulli 
  - condition: check_target(dist7) == bernoulli
    
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```
