# [ソフトウェアサイエンス実験A / 情報システム実験A / 知能情報メディア実験A　テーマ S-14: ランダムネス](https://sites.google.com/view/pis-univ-tsukuba/education/S-14)

本 github の使い方
* ファイル名は出来る限り「****-fy(year)-(name).**」としてください。
* 後輩たちが同じ実験を受講した時に、このファイルを参照します。
* 出来る限り多くのプログラミング言語で実装してみてください。(この際、勉強してみるのもOKです。)

疑似乱数生成・抽出・検出について学びます。

- 乱数検定のリスト
  * スペクトル検定 (授業で解説します) \
  線形合同法で生成された疑似乱数に対する検定法。 \
  線形合同法 $`X_{n+1} = (a X_n + c) \ {\rm mod} \ M`$ から生成される疑似乱数列に対して、\
  $`\nu_k = {\rm min} \ \{ |\vec{s}| = \sqrt{s_1^2+s_2^2+ \cdots + s_k^2} \ {\rm with} \ s_1 + a s_2 + a^2 s_3 + \cdots + a^{k-1} s_k = 0 \ {\rm mod} \ M \}`$ \
  を定義し (Coveyou and McPherson 1969) 、この $`k`$に対する最小値を(線形合同法における)ランダムネスの尺度とする。全ての $`k`$に対して調べることは非常に大変なので、
  Kunuth 1981 によりスペクトル検定の合格の基準として \
  $`\log_2 \nu_k \geq \frac{30}{k} \ (2 \leq k \leq 6) `$ \
  が提案されている。
  * 高次元均等分布 (授業で解説します) \
  まず、1ビット乱数列$`\{ X_n \}`$を用いて、[0,1) 上の$`l`$ビットの2進小数を \
  $`x_t = 0.X_{t+\tau_1} X_{t+\tau_2} \cdots X_{t+\tau_l}`$ \
  と定義する。ここで、$`\tau_1, \tau_2, \cdots, \tau_l`$は互いに異なり、$`t`$いは無関係な定数である。\
  この際、確率変数の列$`\{ U_n \}`$が互いに独立で、[0,1) の一様分布に従っている時、任意の自然数 $`k`$ に対して、$`k`$次元確率変数ベクトル $`( U_t, U_{t+1}, \cdots, U_{t+k} )`$ は
  $`k`$次元単位超立方体で一様分布することを利用すると、$` \omega_j \ (1 \leq j \leq k) `$を任意の$`l`$ビット2進小数とした際、\
  $` {\rm Pr} \ \{ x_t= \omega_1, x_{t+1} = \omega_2, \cdots x_{t+k-1} = \omega_k \} = \frac{1}{2^{kl}}`$ \
  という性質が導かれる。この性質を乱数列だと思われる数列か確かめることことより、乱数生成に対する能力を測るものである。
  * [NIST Test Suites](https://csrc.nist.gov/pubs/sp/800/22/r1/upd1/final)
  * [TEST U01](https://dl.acm.org/doi/10.1145/1268776.1268777) 
  * [Diehard tests](https://webhome.phy.duke.edu/~rgb/General/dieharder.php)
- 疑似乱数生成のリスト \
https://en.wikipedia.org/wiki/List_of_random_number_generators \
出来れば実装してもらいたいリスト
  * 線形合同法 (授業で解説します) (Lehmer 1951) \
$`X_{n+1} = (a X_n + c) \ {\rm mod} \ M`$　
$`a, c, M`$ は定数なので、色んな数字を入れて確かめてみてください。
  * (余力のある方のみ) メルセンヌツイスター ([Matsumoto and Nishimura 1998](https://www.math.sci.hiroshima-u.ac.jp/m-mat/MT/ARTICLES/mt.pdf))
- 乱数抽出のリスト\
https://en.wikipedia.org/wiki/Randomness_extractor \
出来れば実装してもらいたいリスト
  * von Neumann extractor \
    2 bit ずつ区切って 01 なら 0, 10 なら 1, そのほかは何もしない。
  * Samuelson extractor \
    2 bit ずつ区切って 10 なら 0, 11 なら 1, そのほかは何もしない。
