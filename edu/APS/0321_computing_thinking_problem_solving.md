# 컴퓨팅 사고력 문제 풀이

## 1. 논리와 증명

#### 문제 1

다음 명제들이 항진명제임을 진리표를 이용하여 보이시오.
$$
1.\quad \sim{({\sim p} \and q)} \or q\\
2.\quad ({\sim p} \or q) \or (p  \and {\sim q})
$$

##### 풀이

1. 

   | p    | q    | ~p   | ~p∧q | ~(~p∧q) | ~(~p∧q)∨q |
   | ---- | ---- | ---- | ---- | ------- | --------- |
   | T    | T    | F    | F    | T       | T         |
   | T    | F    | F    | F    | T       | T         |
   | F    | T    | T    | T    | F       | T         |
   | F    | F    | T    | F    | T       | T         |

2. 

   | p    | q    | ~p   | ~q   | ~p∨q | p∧~q | (\~p∨q)∨(p∧\~q) |
   | ---- | ---- | ---- | ---- | ---- | ---- | --------------- |
   | T    | T    | F    | F    | T    | F    | T               |
   | T    | F    | F    | T    | F    | T    | T               |
   | F    | T    | T    | F    | T    | F    | T               |
   | F    | F    | T    | T    | T    | F    | T               |



#### 문제 2

다음 명제들이 모순명제임을 진리표를 이용하여 보이시오.

##### 풀이

1. 

   | p    | q    | ~p   | ~q   | ~p∨q | p∧~q | (\~p∨q)∧(p∧\~q) |
   | ---- | ---- | ---- | ---- | ---- | ---- | --------------- |
   | T    | T    | F    | F    | T    | F    | F               |
   | T    | F    | F    | T    | F    | T    | F               |
   | F    | T    | T    | F    | T    | F    | F               |
   | F    | F    | T    | T    | T    | F    | F               |

2. 

   | p    | q    | ~q   | p∧q  | p∧~q | (p∧q)∧(p∧~q) |
   | ---- | ---- | ---- | ---- | ---- | ------------ |
   | T    | T    | F    | T    | F    | F            |
   | T    | F    | T    | F    | T    | F            |
   | F    | T    | F    | F    | F    | F            |
   | F    | F    | T    | F    | F    | F            |



#### 문제 6

n이 짝수이면 3n+5는 홀수임을 증명하시오.

##### 풀이

$$
n=2k\\
3n+5=3 \times 2k+5\\
=6k+5\\
=2(3k+2)+1
$$



#### 문제 7

n이 홀수이면 n^2+n은 짝수임을 증명하시오.

##### 풀이

$$
n=2k+1\\
n^2+n=(2k+1)^2+2k+1\\
=4k^2+4k+1+2k+1\\
=4k^2+6k+2\\
=2(2k^2+3k+1)
$$



#### 문제 8

m이 짝수이고 n이 홀수이면 2m+3n은 홀수임을 증명하시오.

##### 풀이

$$
m=2k,\quad n=2l+1\\
2m+3n=2 \times 2k+3(2l+1)\\
=4k+6l+3\\
=2(2k+3l+1)+1
$$



#### 문제 9

자연수 n에 대해 n^2+5가 홀수이면 n은 짝수임을 증명하시오.

##### 풀이

- 명제의 대우인 n이 홀수이면 n^2+5가 짝수임을 증명

$$
n=2k+1\\
n^2+5=(2k+1)^2+5\\
=4k^2+4k+1+5\\
=2(k^2+2k+3)
$$



#### 문제 10

n^2이 짝수이면 n은 짝수임을 증명하시오.

##### 풀이

- 명제의 대우인 n이 홀수이면 n^2이 홀수임을 증명

$$
n=2k+1\\
n^2=(2k+1)^2\\
=4k^2+4k+1\\
=2(2k^2+2k)+1
$$



#### 문제 11

자연수 n에 대해 n^2+5n+3은 항상 홀수임을 증명하시오.

##### 풀이

- n이 홀수인 경우와 짝수인 경우를 나누어 증명

$$
n=2k+1\\
n^2+5n+3=(2k+1)^2+5(2k+1)+3\\
=4k^2+4k+1+10k+5+3\\
=4k^2+14k+9\\
=2(2k^2+7k+4)+1\\\\
n=2k\\
n^2+5n+3=(2k)^2+5 \times 2k+3\\
=4k^2+10k+3\\
=2(2k^2+5k+1)+1
$$



#### 문제 12

n^2이 3의 배수이면 n은 3의 배수임을 증명하시오.

##### 풀이

- 명제의 대우인 n이 3의 배수가 아니면 n^2은 3의 배수가 아님을 증명

$$
n=3k+1\\
n^2=(3k+1)^2\\
=9k^2+6k+1\\
=3(3k^2+2k)+1\\\\
n=3k+2\\
n^2=(3k+2)^2\\
=9k^2+12k+4\\
=3(3k^2+4k+1)+1
$$



## 2. 수와 표현

#### 문제 1

2진수 표현에서 log n 비트로 표현할 수 있는 숫자 범위

##### 풀이

$$
2^{\log n}\\
=n^{\log 2}\\
=n\\\\
\therefore 0 \le x \le n-1
$$

#### 문제 2

스무고개가 이상적으로 진행될 시, 맞출 수 있는 답의 수

##### 풀이

$$
2^{20}\\
=1,048,576
$$



#### 문제 3

n이 충분히 클 때 대소 비교
$$
1.\quad 2n,\quad n^2\\
2.\quad 2^{\frac {n}{2}},\quad \sqrt {3^n}\\
3.\quad 2^{n\log n},\quad n!\\
4.\quad \log 2^{2n},\quad n \sqrt n\\
$$

##### 풀이

$$
1.\\
2n,\quad n^2\\
2,\quad n\\
2n < n^2\\\\
2.\\
2^{\frac {n}{2}},\quad \sqrt {3^n}\\
\sqrt {3^n}=3^{\frac {n}{2}}\\
2^{\frac {n}{2}} < \sqrt {3^n}\\\\
3.\\
2^{n\log n},\quad n!\\
2^{n\log n}=n^{n\log 2}=n^n\\
2^{n\log n} > n!\\\\
4.\\
2n,\quad n \sqrt n\\
2,\quad \sqrt n\\
\log 2^{2n} < n \sqrt n\\
$$



#### 문제 4

$$
x=\log_{a} yz
$$

위 식에서 x를 2를 밑으로 하는 로그들로 표현

##### 풀이

$$
x=\log_{a} yz\\
a^x=yz\\
\log a^x=\log yz\\
x\log a=\log y+\log z\\
\therefore x=\frac {\log y+\log z}{\log a}\\
$$



#### 문제 5

역함수
$$
1.\quad f(x)=\log (x-3)-5\\
2.\quad f(x)=3\log (x+3)+1\\
3.\quad f(x)=2 \times 3^x-1\\
$$

##### 풀이

$$
1.\\
f(x)=\log (x-3)-5\\
f(x)+5=\log (x-3)\\
2^{f(x)+5}=x-3\\
x=2^{f(x)+5}+3\\
\therefore f^{-1}(x)=2^{x+5}+3\\\\
2.\\
f(x)=3\log (x+3)+1\\
f(x)-1=3\log (x+3)\\
\frac {f(x)-1}{3}=\log (x+3)\\
2^{\frac {f(x)-1}{3}}=x+3\\
x=2^{\frac {f(x)-1}{3}}-3\\
\therefore f^{-1}(x)=2^{\frac {x-1}{3}}-3\\\\
3.\\
f(x)=2 \times 3^x-1\\
f(x)+1=2 \times 3^x\\
\frac {f(x)+1}{2}=3^x\\
x=\log_{3} \frac {f(x)+1}{2}\\
f^{-1}(x)=\log_{3} \frac {x+1}{2}\\
$$



## 3. 집합과 조합론

#### 문제 1

$$
{n \choose k} + {n \choose k-1}={n+1 \choose k}
$$

##### 풀이

$$
{n \choose k} + {n \choose k-1}={n+1 \choose k}\\
=\frac {n!}{(n-k)!k!}+\frac {n!}{(n-k+1)!(k-1)!}=\frac {(n+1)!}{(n-k+1)!k!}\\
=\frac {(n-k+1)n!}{(n-k+1)!k!}+\frac {kn!}{(n-k+1)!k!}=\frac {(n+1)!}{(n-k+1)!k!}\\
=\frac {(n-k+k+1)n!}{(n-k+1)!k!}=\frac {(n+1)!}{(n-k+1)!k!}\\
=\frac {(n+1)n!}{(n-k+1)!k!}=\frac {(n+1)!}{(n-k+1)!k!}\\\\
\therefore {n \choose k} + {n \choose k-1}={n+1 \choose k}
$$



#### 문제 4

$$
(A-B)\cap(B-A)=\varnothing
$$

##### 풀이

- 귀류법을 이용하여 원소가 있음을 가정하고 이의 모순을 찾아 원명제를 증명

$$
P \in (A-B),\quad P \in (B-A)\\\\
1.\; P \in A\; and\; P \notin B\\
\because P \in (B-A)\; and\; (B-A) \subset B\\\\
2.\; P \notin A\; and\; P \in B\\
\because P \in (A-B)\; and\; (A-B) \subset A\\\\
3.\; P \notin A\; and\; P \notin B\\
\because (A-B) \subset A\; and\; (B-A) \subset B\\\\
4.\; P \in A\; and\; P \in B\\
\Rightarrow P \in (A \cap B) \\
\because P \in (A-B) \Rightarrow P \in (A \cap B^c),\quad P \in (B-A) \Rightarrow P \in (A^c \cap B)
$$



#### 문제 6

$$
(A \cup B)\cap(A \cap B)^c=(A-B) \cup (B-A)
$$

##### 풀이

$$
(A-B) \cup (B-A) = (A \cap B^c) \cup (A^c \cap B)\\
=((A \cap B^c) \cup A^c) \cap ((A \cap B^c) \cup B)\\
=((A \cup A^c) \cap (B^c \cup A^c)) \cap ((A \cup B) \cap (B^c \cup B))\\
=(U \cap (A \cap B)^c) \cap ((A \cup B) \cap U)\\
=(A \cap B)^c \cap (A \cup B)\\\\
\therefore (A \cup B)\cap(A \cap B)^c=(A-B) \cup (B-A)
$$



#### 문제 8

8 × 8 체스판에 말 두 개를 놓는 조합의 수

##### 풀이

$$
{64 \choose 2}\\
=\frac {64!}{(64-2)!2!}\\
=\frac {64 \times 63}{2}\\
=32 \times 63\\
=2,016
$$



#### 문제 10

0~9의 숫자로 가능한 4자리 이상 6자리 이하 비밀번호 수

##### 풀이

$$
_{10}\mathrm{P}_{4}+_{10}\mathrm{P}_{5}+_{10}\mathrm{P}_{6}\\
=\frac {10!}{(10-4)!}+\frac {10!}{(10-5)!}+\frac {10!}{(10-6)!}\\
=10 \times 9 \times 8 \times 7(1+6+6 \times 5)\\
=186,480
$$



#### 문제 12

트럼프 카드에서 5장 조합의 수

##### 풀이

$$
{52 \choose 5}\\
=\frac {52!}{(52-5)!5!}\\
=\frac {52!}{47!5!}\\
=\frac {52 \times 51 \times 50 \times 49 \times 48}{5 \times 4 \times 3 \times 2}\\
=2,598,960
$$



#### 문제 13

트럼프 카드 5장 조합에서 무늬가 같은 카드가 3장인 경우

##### 풀이

$$
{13 \choose 3} \times 4 \times {3 \choose 2} \times {13 \choose 1} \times {13 \choose 1}\\
=\frac {13!}{(13-3)!3!} \times 4 \times \frac {3!}{2!} \times \frac {13!}{12!} \times \frac {13!}{12!}\\
=\frac {13 \times 12 \times 11}{3!} \times 4 \times 3 \times 13 \times 13\\
=13 \times 2 \times 11 \times 4 \times 3 \times 13 \times 13\\
=580,008
$$



#### 문제 16

트럼프 카드 5장 조합에서 숫자가 같은 카드가 한 쌍도 없는 경우

##### 풀이 1

$$
{13 \choose 5} \times 4^5\\
=\frac {13!}{(13-5)!5!} \times 4^5\\
=\frac {13 \times 12 \times 11 \times 10 \times 9}{5 \times 4 \times 3 \times 2} \times 4^5\\
=13 \times 11 \times 9 \times 4^5\\
=1,317,888
$$

##### 풀이 2

$$
{52 \choose 1} \times {48 \choose 1} \times {44 \choose 1} \times {40 \choose 1} \times {36 \choose 1} \times \frac {1}{5!}\\
=\frac {52 \times 48 \times 44 \times 40 \times 36}{5 \times 4 \times 3 \times 2}\\
=52 \times 48 \times 44 \times 2 \times 6\\
=1,317,888
$$



## 4. 기초 수식

### 다음 재귀식들을 O() notation 수준으로 풀어라.

#### 문제 1

$$
T(n)=T(n-1)+1,\quad T(0)=1
$$

##### 풀이

$$
T(n)=T(n-1)+1\\
=T(n-2)+1+1\\
=T(n-3)+1+1+1\\
\cdots\\
=T(n-k)+k\\\\
if\; k=n,\\
T(n)=T(0)+n\\
=n+1\\\\
\therefore O(n)
$$



#### 문제 2

$$
T(n)=T(n-1)+n,\quad T(0)=1
$$

##### 풀이

$$
T(n)=T(n-1)+n\\
=T(n-2)+(n-1)+n\\
=T(n-3)+(n-2)+(n-1)+n\\
\cdots\\
=T(n-k)+(n-k+1)+(n-k+2)+\ \cdots\ +(n-k+k)\\\\
if\; k=n,\\
T(n)=T(0)+1+2+\ \cdots\ +n\\
=1+\frac{n(n+1)}{2}\\
=\frac{1}{2}n^2+\frac{1}{2}n+1\\\\
\therefore O(n^2)
$$



#### 문제 3

$$
T(n)=T(n-1)+\log n,\quad T(0)=1
$$



##### 풀이

$$
T(n)=T(n-1)+\log n\\
=T(n-2)+\log (n-1)+\log n\\
=T(n-3)+\log (n-2)+\log (n-1)+\log n\\
\cdots\\
=T(n-k)+\log (n-k+1)+\log (n-k+2)+\ \cdots\ +\log (n-k+k)\\\\
if\; k=n,\\
T(n)=T(0)+\log 1+\log 2+\ \cdots \ +\log n\\
\le T(0)+\log n+\log n+\ \cdots \ +\log n\\
=T(0)+n\log n\\
=n\log n+1\\\\
\therefore O(n\log n)
$$



#### 문제 4

$$
T(n)=T\left (\frac{n}{2} \right)+1,\quad T(1)=1
$$

##### 풀이

$$
T(n)=T\left (\frac{n}{2} \right)+1\\
=T\left (\frac{n}{2^2} \right)+1+1\\
=T\left (\frac{n}{2^3} \right)+1+1+1\\
\cdots\\
=T\left (\frac{n}{2^k} \right)+k\\\\
if\; 2^k=n,\\
k=\log n,\\
T(n)=T(1)+\log n\\
=\log n+1\\\\
\therefore O(\log n)
$$



#### 문제 5

$$
T(n)=T\left (\frac{n}{2} \right)+n,\quad T(1)=1
$$



##### 풀이

$$
T(n)=T\left (\frac{n}{2} \right)+n\\
=T\left (\frac{n}{2^2} \right)+\frac{n}{2}+n\\
=T\left (\frac{n}{2^3} \right)+\frac{n}{2^2}+\frac{n}{2}+n\\
\cdots\\
=T\left (\frac{n}{2^k} \right)+\frac{n}{2^{k-1}}+\frac{n}{2^{k-2}}+\ \cdots \ +\frac{n}{2^{k-k}}\\
=T\left (\frac{n}{2^k} \right)+n\left (1+\frac{1}{2}+\frac{1}{2^2}+\ \cdots \ +\frac{1}{2^{k-1}} \right)\\\\

if\; 2^k=n,\\
k=\log n,\\
T(n)=T(1)+n\left (1+\frac{1}{2}+\frac{1}{2^2}+\ \cdots \ +\frac{1}{2^{\log n-1}} \right)\\
=T(1)+n\left (\frac{1-\frac {1}{2^{\log n}}}{1-\frac{1}{2}} \right)\\
=T(1)+2n\left (1-\frac {1}{n} \right)\\
=T(1)+2n-2\\
=2n-1\\\\
\therefore O(n)
$$



#### 문제 6

$$
T(n)=2T\left (\frac{n}{2} \right)+n,\quad T(1)=1
$$

##### 풀이

$$
T(n)=2T\left (\frac{n}{2} \right)+n\\
=2^2T\left (\frac {n}{2^2} \right)+n+n\\
=2^3T\left (\frac {n}{2^3} \right)+n+n+n\\
\cdots\\
=2^kT\left (\frac {n}{2^k} \right)+kn\\\\
if\; 2^k=n,\\
k=\log n,\\
T(n)=nT(1)+n\log n\\
=n\log n+n\\\\
\therefore O(n\log n)
$$



#### 문제 7

$$
T(n)=3T\left (\frac {n}{2} \right)+n,\quad T(1)=1
$$

##### 풀이

$$
T(n)=3T\left (\frac {n}{2} \right)+n\\
=3^2T\left (\frac{n}{2^2} \right)+\frac {3n}{2}+n\\
=3^3T\left (\frac{n}{2^3} \right)+\frac {3^2n}{2^2}+\frac {3n}{2}+n\\
\cdots\\
=3^kT\left (\frac {n}{2^k} \right)+\frac {3^{k-1}n}{2^{k-1}}+\frac {3^{k-2}n}{2^{k-2}}+\ \cdots \ +\frac {3^{k-k}n}{2^{k-k}}\\\\
=3^kT\left (\frac {n}{2^k} \right)+\left (\frac {3}{2} \right)^{k-1}n+\left (\frac {3}{2} \right)^{k-2}n+\ \cdots \ +\left (\frac {3}{2} \right)^{k-k}n\\
=3^{k}T(1)+n\left (\frac{\left (\frac {3}{2} \right)^{k}-1}{\frac {3}{2}-1} \right)\\
=3^{k}T(1)+2n\left (\left (\frac {3}{2} \right)^{k}-1 \right)\\\\
if\; 2^k=n,\\
k=\log n,\\
T(n)=3^{\log n}T(1)+2n\left (\left (\frac {3}{2} \right)^{\log n}-1 \right)\\
=n^{\log 3}+2n\left (n^{\log \frac {3}{2}}-1 \right)\\
=n^{\log 3}+2n\left (\frac {n^{\log 3}}{n^{\log 2}}-1 \right)\\
=n^{\log 3}+2n\left (\frac {n^{\log 3}}{n}-1 \right)\\
=3n^{\log 3}-2n\\\\
\therefore O(n^{\log 3})
$$



#### 문제 8

$$
T(n)=T(n-1)+\frac {1}{n},\quad T(1)=1
$$

##### 풀이

$$
T(n)=T(n-1)+\frac {1}{n}\\
=T(n-2)+\frac {1}{n-1}+\frac {1}{n}\\
=T(n-3)+\frac {1}{n-2}+\frac {1}{n-1}+\frac {1}{n}\\
\cdots\\
=T(n-k)+\frac {1}{n-k+1}+\frac {1}{n-k+2}+\ \cdots\ +\frac {1}{n-k+k}\\\\
if\; k=n,\\
T(n)=T(0)+\frac {1}{1}+\frac {1}{2}+\ \cdots\ +\frac {1}{n}\\
\le T(0)+\log n\\
= \log n+1\\\\
\therefore O(\log n)
$$

