# Test: h1 headline

## h2 headline

### h3 headline

#### h4 headline

##### h5 headline

###### h6 headline

### Styles

Normal 常规  
**Bold 粗体**  
*Italic 斜体*  
***Bold and Italic 粗斜体***

[Link 链接](/StudyNotes/index.html "Home 回主页")

### Code

Here is a `code` in a line.

Here is a code section below:

```c
// from https://github.com/RainbowRoad1/Cgame/blob/master/MineSweeper/4_color_27lines.c
// Thanks RainbowRoad1
#include <windows.h>
#include <conio.h>
#include <stdio.h>
int S, W = 9, H = 9, B = 10, s, p = 0, c = 1, i, *m, *M, (*f)(int, int), *O;
int edge(int x, int y) { return x < 0 || W <= x || y < 0 || H <= y; }
void tmp(int x, int y) { edge(x, y) || m[x += W * y] - 9 && ++m[x]; }
void dig(int v, int l) {
	for (l = edge(v, l) || M[v += W * l] || (++M[v], --s, m[v]) ? 0 : 9; l;)
		--l - 4 || --l, f(v % W + l % 3 - 1, v / W + l / 3 - 1);
}
void set(int x, int y) {
	for (f = tmp; c++ < B; m[i] = 0, dig(i % W, i / W), m[i] = 9, M[i]--)
		while (m[i = rand() % S] > 8 || (abs(x - i % W) | abs(y - i / W)) < 2);
	f = dig, s += B, dig(x, y);
}
int main(){
	f = set, s = S = W * H, m = calloc(S * 2, 4), O = GetStdHandle((DWORD)-11);
	SetConsoleCursorInfo(O, &(CONSOLE_CURSOR_INFO){1}), M = m + S, srand(m);
	for (; B % s; c = _getch() & 95, c - 83 || (p += W), c - 87 || (p -= W)) {
		SetConsoleCursorPosition(O, (COORD){0}), c - 68 || ++p, c - 65 || --p;
		p = (p + S) % S, c || (f(p % W, p / W), m[p] < 9 || (B = 0)), i = 0;
		for (c - 27 || (B = 0); c = B | m[i] < 9, i < S; ++i % W || puts(""))
			SetConsoleTextAttribute(O, (M[i] ? m[i] : 9) | (p - i ? 240 : 64)),
				c || ++M[i], printf(M[i] ? " %c" : "■", " 12345678@"[m[i]]);
	}
	_cputs(B ? "You win!" : "Game over!"), _getch();
}
```

### Math

令 $a_i=\left[ \sqrt{i} \right]$ ，则有 $\prod\limits_{i=1}^{p-1} \left(a_i+\frac{i-a_i^2}{2a_i+\frac{i-a_i^2}{2a_i+\frac{i-a_i^2}{2a_i+\ddots}}}\right)^{\sqrt{\ln (\sum\limits_{j=0}^{+\infty} \frac{2^{4j}}{j!})}}\equiv \prod\limits_{i=1}^{p-1} \sqrt{i}^{\sqrt{\ln e^{16}}}\equiv \prod\limits_{i=1}^{p-1} \sqrt{i}^4\equiv ((p-1)!)^2 \equiv p-1\left( \hspace{-0.3cm} \mod p \, \right)$ ．

基本不等式：

$$ H_{n}=\frac{n}{\sum \limits_{i=1}^{n}\frac{1}{x_{i}}}= \frac{n}{\frac{1}{x_{1}}+ \frac{1}{x_{2}}+ \cdots + \frac{1}{x_{n}}} $$

$$ G_{n}=\sqrt[n]{\prod \limits_{i=1}^{n}x_{i}}= \sqrt[n]{x_{1}x_{2}\cdots x_{n}} $$

$$ A_{n}=\frac{1}{n}\sum \limits_{i=1}^{n}x_{i}=\frac{x_{1}+ x_{2}+ \cdots + x_{n}}{n} $$

$$ Q_{n}=\sqrt{\sum \limits_{i=1}^{n}x_{i}^{2}}= \sqrt{\frac{x_{1}^{2}+ x_{2}^{2}+ \cdots + x_{n}^{2}}{n}} $$

$$ H_{n}\leq G_{n}\leq A_{n}\leq Q_{n} $$