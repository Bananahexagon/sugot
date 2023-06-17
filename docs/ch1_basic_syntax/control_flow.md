# 制御構文

<pre><code><strong>// ブロック
</strong>{
    let x // ブロック内のみの変数を宣言する
    print("x is in block scope!")
}
print(x) // コンパイルエラー

// if文
if x % 2 == 1 {
    print("x is odd!")
} else {
    print("x is even!")
} // xの偶奇を判定する

// match文
match x {
    0 => print("x is zero")
    1 => print("x is one")
    2 => print("x is two")
    3 => print("x is three")
    4 => print("x is four")
    _ => print("x is too big!")
} // xの値に応じて処理を変える

// for文
for i in 0..10 {
    print(i)
} // 0から9まで順番に出力する

// while文
while 0 &#x3C; x {
    print(x)
    x--
} // xが0になるまでxを減らし続ける

// Butterではすべての文は式として扱うことができます
let y = if x % 2 == 1 {
    "x is odd!"
} else {
    "x is even!"
} // xの偶奇に応じた文字列が代入される

// ブロック内に複数の式がある場合は最後の式がブロックの値になります
let x = {
    "apple"
    3
    true
    5
} // xは5

// ループの戻り値は最後のループの最後の値になります
let x = for i in 0..10 {
    print(i)
    i
} // xは9
</code></pre>
