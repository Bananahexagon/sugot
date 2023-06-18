# 関数

```
// アロー関数式を使うと関数を定義できます。
const sum = x: int => int {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
} // 引数として整数値を受け取って、その数までの総和を返す関数

// 複数の値を受け取る関数を定義するにはタプルを使います。
const sum = (x: int, y: int) => int {
    x + y
}

// この関数宣言のエイリアスとして、fnキーワードを使うことができます。
fn sum x: int => int {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}

// 値を返したくない場合は、戻り値の型をvoidにします。
fn countUp x: int => void {
    for i in 1..x {
        print(x)
    }
}

// 関数の宣言でも型推論を使うことができます。
fn sum x: int {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}

// 引数の型については型推論を使うことはできません。
fn sum x { // コンパイルエラー
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}

// 再帰的に関数を定義することもできます。
fn factorial x: int {
    if x <= 1 {
        return 1
    } else {
        return factorial(x - 1) * x
    }
}
```
