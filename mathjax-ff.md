Требования к оформлению $\mathrm{\LaTeX}$
---

#### Правильные команды

* Команды <code>\tg x</code>, <code>\ctg x</code>, <code>\arctg x</code> и <code>\arcctg x</code> должны рендериться как $\DeclareMathOperator{\tg}{tg} \tg x$, $\DeclareMathOperator{\tg}{ctg} \tg x$, $\DeclareMathOperator{\tg}{arctg} \tg x$ и $\DeclareMathOperator{\tg}{arcctg} \tg x$ соответственно. В настоящее время оператор <code>\tg</code> обрабатывается неправильно. 
* Аналогично: команды <code>\le</code> и <code>\ge</code> должны выводить наклонные знаки: $\leqslant$ и $\geqslant$.
* Буквы $\varphi$ и $\varepsilon$ должны выводиться командами <code>\phi</code> и <code>\epsilon</code>.

Кажется, это решается так: 
	
```
MathJax.Hub.Config({
  TeX: {
    extensions: ["AMSmath.js","AMSsymbols.js"],
    Macros: {
      le: ['\\leqslant', 0],
      ge: ['\\geqslant', 0],
      phi: ['\\varphi', 0],
      epsilon: ['\\varepsilon', 0],
      arctg: ['\\mathop{\\rm arctg}\\nolimits', 0],
      ctg: ['\\mathop{\\rm ctg}\\nolimits', 0],
      arcctg: ['\\mathop{\\rm arcctg}\\nolimits', 0],
      tg: ['\\mathop{\\rm tg}\\nolimits', 0],
  },
});
```

#### Правильная запятая

По умолчанию mathjax считает запятую разделителем элементов списка, и только. Нам нужно, чтобы он ее считал разделителем целой и дробной частей в десятичной дроби. То есть, нужно, чтобы код <code>
$2,3$</code> выводил на экран $2{,}3$ а не $2,3$ (обратите внимание на лишний пробел). 

Кажется, решение описано [здесь](https://github.com/mathjax/MathJax/issues/169#issuecomment-2040235).

> Written with [StackEdit](https://stackedit.io/).