<p align="center">
  <a href="https://example.com/">
    <img src="http://www.epsilones.com/material/artes/027-fibonacci-pisa.jpg" alt="statue" width=72 height=72>
  </a>

  <h3 align="center">10 ways to Fibonacci series</h3>

  <p align="center">
    because I'm bored and softwares are broken. Don't believe me? 
    <br>
  </p>
</p>


## By professionals

- [Functional prodigy](#functional-prodigy)
- [Meta functional expert](#meta-functional-expert)
- [One liner wizard](#one-liner-wizard)
- [Classy theorist](#classy-theorist)
- [Closure fanatic](#closure-fanatic)
- [Lazy idealist](#lazy-idealist)
- [OO based lazy conservative](#OO-based-lazy-conservative)
- [Generator magician](#generator-maniac)
- [Iterator maniac](#iterator-maniac)
- [Abandoned](#abandoned)

## Functional prodigy

```python
def fib(n):
    if n <= 1:
        return n
    return fib(n-1) + fib(n-2)
```

## Meta Functional Expert

```python
def fib(a, b, nth=0, current=0):
    if nth == current:
        return a
    return fib(b, a + b, nth, current+1)

def main():
    series = [fib(0,1,n) for n in range(50)]
    print(series)
```

## One Liner Wizard

```python
f = lambda n: n if n <= 1 else f(n-1) + f(n-2)  # f and not fib because functional laws
```

## Classy Theorist

```python
class Fibonacci:

    def __init__(self, nth):
        self.nth = nth
        self.a = 0
        self.b = 1
        self.current = 0

    def get(self):
        while True:
            if self.current == self.nth:
                    return self.a
              self.a, self.b = self.b, self.a + self.b
              self.current += 1

def main():
    f = Fibonacci(100)
    # God bless getters
    print(f.get())
```

## Closure Fanatic

```python
from functools import wraps

def closo_fibo_stream():
    # precious closures
    a, b = 0, 1
    @wraps
    def wrapper(*args, **kwargs):
        nonlocal a, b
        current = a
        a, b = b, a + b
        return current
    return wrapper

def main():
    streamer = closo_fibo_stream()
    series = [streamer() for i in range(10)]
    print(series)
```

## Lazy Idealist

```python
def lazy_fibo():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

def main():
    from itertools import islice
    for n in islice(lazy_fibo(), 100):
        print(n) # i feel good

```

## OO based Lazy conservative

```python
# refactored into class coz why not??
class LazyFibo:
    def __init__(self):
        self.a = 0
        self.b = 1

    def __iter__(self):
        while True:
            yield self.a
            self.a , self.b = self.b, self.b + self.a

def main():
    from itertools import islice
    for n in islice(LazyFibo(),10):
        print(n)
```

## Generator Magician

```python
def fib_magico(a, b):
    yield a
    yield from fib_magico(b, a + b)

def main():
    from itertools import islice
    for n in islice(fib_magico(0, 1), 10):
            print(n)
```

## Iterator Maniac

```python
class fib_iter:

    def __init__(self, n):
        self.n = n
        self.current = 0
        self.a = 0
        self.b = 1

    def __next__(self):
        if self.current > self.n:
            raise StopIteration("don't care anymore")
        current = self.a
        self.a, self.b = self.b, self.a + self.b
        self.current += 1
        return current

class fib:

    def __init__(self, n):
        self.n = n

    def __iter__(self):
        return fib_iter(self.n)

def main():
    for i in fib(10):
        print(i)
```

## Abandoned

```python
# not for experts
def fib(n):
    res = []
    a, b = 0, 1
    for i in range(n):
        res.append(a)
        a, b = b, a + b
    return res
```

### you be the judge!!

## Thanks

Enjoy :metal:
