http://martinfowler.com/bliki/TechnicalDebtQuadrant.html

2009/10/14

ここ数ヶ月の間に、
[[TechnicalDebt]]
に関する投稿がいくつかあった。設計上の不備の中で、技術的負債と呼ぶべきものは何か？
逆に、そう呼ぶべきでないものは何か？といった疑問が挙げられていた。

その一例が、アンクル・ボブの投稿「
[[a mess is not a debt|http://blog.objectmentor.com/articles/2009/09/22/a-mess-is-not-a-technical-debt]]」だ。
彼の意見は、こういうことだ。
良い設計方法を知らない人が書いた単に汚いだけのコードを負債と呼ぶべきではない。
技術的負債という言葉はもっと特別な場合を指すものだ。
検討の末に、長期的な持続性のない(けれども短期的には利益を生み出す。たとえばすぐにリリースできるなどの)
設計指針を敢えて選択するといった場合に使う。
要するに、負債を抱えれば早めに価値を生み出せるけれども、いずれ返済しないといけなくなる。

私に言わせると、設計の不備が負債かそうじゃないかなんて考えることがそもそも間違ってる。
技術的負債っていうのは単なるたとえ話なんだから、
ここで問うべきなのは「これを負債にたとえた場合に、
設計上の問題を考える助けになるだろうか？そして他人と意見交換しやすくなるだろうか？」だ。
このたとえ話を使う大きなメリットは、技術者以外にも話が通じやすくなることだ。

私見だが、設計上の不備も検討の末の判断も、どちらも負債のたとえがうまく当てはまると思う。
ただ、負債の性質が違うというだけのことだ。
きたないコードは無鉄砲な(reckless)負債だ。結果として利息の支払いが不能になったり、
いくら払っても元金が減らなかったりすることになる。
私たちのプロジェクトの中にも、コードベースが負債まみれになっているものがいくつかある。
その対策についてクライアントの担当者と話し合うときに、このたとえはとても便利だ。

負債のたとえを聞いて思い出すのが、設計上の不備に対して私たちがとれる選択肢のことだ。
用心深く考えた結果として負債を抱えたリリースをした場合、
支払う利息が無視できるほど小さいのならその返済をしなくてもかまわないだろう。
たとえば、めったに使われることのない部分などがこれにあたる。

つまり、負債かそうじゃないかっていう区別はあまり意味がなくて、
考えた上での負債なのか考えが足りない負債なのかのほうが大事だ。

いまあげた例について、もうひとつ別の切り口で区別することもできる。
無鉄砲な負債か用心深い負債化という違いのほかに、
意図的な負債なのか無意識のうちの負債なのかという区別があるのだ。
用心深い負債の例は、この区別では意図的な負債にあたる。
チームはそれが負債であることを認識しており、早めにリリースすることで
十分元が取れるという判断をしたわけだ。
設計について無関心なチームは、無意識のうちに負債を抱えてしまうことがある。
いったいどれだけのものを質入れしているのかを認識することもない。

無鉄砲な負債は必ずしも無意識なものばかりというわけではない。
設計の重要性をきちんと理解していて実践できるチームでも、あえて
「間に合わせの適当な」設計を選ぶこともある。
クリーンなコードを書くだけの余裕がないと判断した場合などだ。
こんな場合はほとんど無鉄砲な負債になるっていうことについては、私もアンクル・ボブに同意する。
人はみな、[[DesignPayoffLine]]を過小評価するものだからだ。
よい設計とクリーンなコードの本質は、開発をすばやく進められるようにすることだ。
そうでもなければ、アンクル・ボブやケント・ベックそしてウォード・カニンガムといった面々が、わざわざ時間をかけて議論することもないだろう。

「無鉄砲／用心深い」と「意図的な／無意識な」の二つの基準を使うと、
負債を四象限に分類できることになる。ここまでで議論したのは、その中の三つの部分だ。
残りの一つ、つまり「用心深く、かつ無意識な」負債については何が言えるだろう？
ちょっと奇妙な感じもするが、私はこれもアリだと思う。
普通にあり得る話だっていうだけじゃなく、よくできる設計者が集ったチームでは避けられない事態だ。

私の同僚と、彼が最近リリースしたプロジェクトのことについて話をした。
彼が言うには、そのプロジェクトは価値のあるソフトウェアを提供できたし、
顧客も喜んでくれたし、そしてコードもクリーンだった。
でも、なぜか彼はそのコードに満足していなかった。
自分のチームがいい仕事をしてくれたというのはわかっている。
でも、今になって「あそこはこうしておくべきだった」ということがわかってきたというのだ。

デキる開発者たちは、いつもこんなことを言っている。
要するに、プログラミングをしているときには、同時に学んでもいるということだ。
何かのプロジェクトに参加して1年ほどプログラミングをし続けて、
ようやくその課題に対する最善のアプローチを理解したりするってことも珍しくない。
おそらく、最初からそれを見越した計画を立てるべきなんだろう。最初の1年で組み立てたシステムを
いったん破棄して最初から作り直すということだ。かつてフレッド・ブルックスもそんな提案をしていた。
でも、なかなかそんなことも言っていられない。
本来そうすべきだった設計を発見した時点で、あなたは無意識な負債を抱えたことを自覚することになる。
これはある意味、ウォードが[[この映像|http://www.c2.com/cgi/wiki?ComplexityAsDebt]]で話している負債みたいなものだ。

利息を払うことを選ぶか元本を返済することを選ぶかという判断がここでもあてはまる。
今回の場合も、このたとえ話が使えるだろう。
でも、このたとえ話にも問題はある。
というのは、「用心深い・無意識な」型の負債なんていうのは、実際の財務では想像できないからだ。
なので、なぜこんな負債が発生することになったのかを上司に説明しづらくなる。
個人的には、この手の負債は避けられないものなのだから、あらかじめ想定しておくべきだと考える。
どんなにすばらしいチームだって、プロジェクトが進むにつれて負債を抱えることになる。
そうしないで無茶をすれば、質の悪いコードに押しつぶされてしまうからだ。

[[技術的負債の四象限|http://martinfowler.com/bliki/images/techDebtQuadrant.png]]

*Reckless(無鉄砲な) / Prudent(用心深い)
*Deliberate(意図的な) / Inadvertent(無意識な)

*reckless-deliberate 「設計する時間がないんだからしょうがない」
*prudent-deliberate 「今すぐリリースしないといけない。リスクは承知の上だ」
*reckless-inadvertent 「レイヤー化？なにそれ？」
*prudent-inadvertent 「よし、これでオッケー！」

{{rcomment}}