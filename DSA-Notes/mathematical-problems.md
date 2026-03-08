# Mathematical Problems

## 1. Common diviser and common multiple
### Euclidean Algorithm
use to Calculate the greatest common divisor of two integers.
> gcd(a, b) = gcd(b, a mod b)  



```cpp
int gcd(int a, int b) {
  return b == 0? a : gcd (b, a% b);
}
```
### Extended Euclidean Algorithm
The Extended Euclidean Algorithm can not only find the **greatest common divisor (gcd(a, b))** of two integers a and b, but also find **integers x and y** such that...
> ax + by = gcd(a, b)

```cpp
int xGCD(int a, int b, int &x, int &y){
  if(!b){
    x = 1, y = 0;
    return a;
  }
  int x1, y1, gcd = xGCD(b, a % b, x1, y1);
  x = y1, y = x1 - (a / b) * y1;
  return gcd;
}
```

## Prime Number
A prime number can only be divided evenly by 1 and itself.

Practice:
[204. Count Primes](https://leetcode.com/problems/count-primes/)

### Sieve of Eratosthenes
The Sieve of Eratosthenes is an ancient and efficient algorithm for finding all prime numbers up to a given limit. It was invented by Eratosthenes of Cyrene, a Greek mathematician, around 200 BCE.  
Think of it as a "number sifter" – like a kitchen sieve that filters out composite numbers, leaving only primes behind!

#### Core Idea
Simple Analogy 🍜  
Imagine you have a bowl of numbered balls from 2 to 100:  
1. Start with the smallest number (2) – it's prime!  
2. Remove all multiples of 2 (4, 6, 8, 10...)  
3. Move to the next remaining number (3) – it's prime!  
4. Remove all multiples of 3 (6, 9, 12, 15...)  
5. Continue until done  
What's left? All prime numbers!
