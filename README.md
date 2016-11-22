投资复利计算
------------

### 假定我们按以下设定场景进行投资并收取回报。

1.  每年投入固定数量资金。
2.  每年的投资回报率是固定的。
3.  资金复利增长。
4.  到一定年数后停止投资，开始收取回报，但是剩余资金仍然按复利增长，投资回报率不变。
5.  每年收取的回报相同，直至资金枯竭。

### 变量定义：

a = 每年的投资额, b = 每年收取的回报, m = 总投资年数, n = 收取回报年数

k = 投资回报率（例：如果回报率为5%, k = 1.05）

当投资停止时，积累的资金可推导如下：

第一年：![equation](http://latex.codecogs.com/gif.latex?a \\times k)

第二年：![equation](http://latex.codecogs.com/gif.latex?(a \\times k + a) \\times k = ak^2 + ak = a(k^2 + k))

第三年：![equation](http://latex.codecogs.com/gif.latex?(ak^2 + ak + a) \\times k = ak^3 + ak^2 + ak = a(k^3 +
k^2 +k))

  ....

第M年：![equation](http://latex.codecogs.com/gif.latex?a(k^m + k^{m-1} + k^{m-2} + .... + k) = a {k(k^m - 1)
\\over k - 1})

当开始收取回报后，资金的变化可推导如下：


设开始的资金为![equation](http://latex.codecogs.com/gif.latex?Q, Q = a {k(k^m - 1) \\over k - 1})

第一年：![equation](http://latex.codecogs.com/gif.latex?(Q - b) \\times k = Qk - bk)

第二年：![equation](http://latex.codecogs.com/gif.latex?(Qk - bk - b) \\times k = Qk^2 - bk^2 - bk)

第三年：![equation](http://latex.codecogs.com/gif.latex?(Qk^2 - bk^2 -bk - b) \\times k = Qk^3 - bk^3 - bk^2 -
bk)

  ....

第N年：![equation](http://latex.codecogs.com/gif.latex?Qk^n - bk^n - bk^{n-1} - bk^{n-2} .... -bk = Qk^n - b
{k(k^n - 1) \\over k - 1})

因为收取回报一直到资金枯竭，所以


![equation](http://latex.codecogs.com/gif.latex?Qk^n - b{k(k^n - 1) \\over k - 1} = 0)，即![equation](http://latex.codecogs.com/gif.latex?b{k(k^n - 1) \\over
k - 1} = a {k(k^m - 1) \\over k - 1}k^n, b(k^n - 1) = a(k^m -
1)k^n)

有以上这个基本公式后，我们可作以下计算：


1.  当知道回报率，投资年数，每年收取回报额，收取回报年数，求每年投资额

    ![equation](http://latex.codecogs.com/gif.latex?a={b(k^n - 1) \\over (k^m - 1)k^n})
2.  当知道回报率，每年投资额，每年收取回报额，收取回报年数，求投资年数

    ![equation](http://latex.codecogs.com/gif.latex?m={ln({b(k^n - 1) \\over ak^n} + 1) \\over ln(k)})
3.  当知道回报率，每年投资额，投资年数，每年收取回报额，求取回报年数

    ![equation](http://latex.codecogs.com/gif.latex?n={ln({b \\over b - a(k^m - 1)}) \\over ln(k)})
4.  当知道回报率，每年投资额，投资年数，回报年数，求取每年回报额

    ![equation](http://latex.codecogs.com/gif.latex?b={a(k^m - 1)k^n \\over k^n - 1})
5.  当知道每年投资额，投资年数，回报年数，每年回报额，求取回报率

    从基本公式我们可以推导出
    ![equation](http://latex.codecogs.com/gif.latex?ak^{m+n} - ak^n - bk^n + b = 0)， 当a,b,m,n已知时，求k的解。<br>
    对于高阶方程，没有直接的代数根解，但我们可以用牛顿迭代求近似解。<br>
    设![equation](http://latex.codecogs.com/gif.latex?f(k)=ak^{m+n} - ak^n - bk^n + b = 0)，则![equation](http://latex.codecogs.com/gif.latex?f'(k)=(m+n)ak^{m+n-1} - nak^{n-1} - bnk^{n-1})<br>
    定义d为可以接受的误差，例如![equation](http://latex.codecogs.com/gif.latex?d=0.00001)，
    取任意![equation](http://latex.codecogs.com/gif.latex?x_{0}, x'_{0}=x_{0} - {f(x_{0}) \\over f'(x_{0})})，<br>
    如果![equation](http://latex.codecogs.com/gif.latex?abs(x_{0} - x'_{0}) >= d)，令![equation](http://latex.codecogs.com/gif.latex?x_{0} = x'_{0}, x'_{0}=x_{0} - {f(x_{0}) \\over f'(x_{0})})。一直迭代到![equation](http://latex.codecogs.com/gif.latex?abs(x_{0} - x'_{0}) < d)
