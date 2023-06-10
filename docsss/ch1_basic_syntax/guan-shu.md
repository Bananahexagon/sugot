---
description: Butterで関数を使用する方法を説明します。
---

# 関数

例えば、引数として整数値を受け取って、その数までの総和を返す関数は以下のように書きます。

```
const sum = (x: int): int => {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}
```

この関数宣言のエイリアスとして、`fn`キーワードを使ったものがあります。以下のコードは上記のコードと全く同じ働きをします。

```
fn sum(x: int): int {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}
```

値を返したくない場合は、戻り値の型を`void`にします。

```
fn countUp(x: int): void {
    for i in 1..x {
        print(x)
    }
}
```

関数の宣言でも型推論を使うことができます。例えば、以下のコードは正常に動作します。

```
fn sum(x: int) {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}
```

引数の型については型推論を使うことはできません。

{% code overflow="wrap" %}
```
//コンパイルエラー
fn sum(x) {
    let y = 0
    for i in 1..x {
        y += i
    }
    return y
}
```
{% endcode %}

再帰的に関数を定義することもできます。

```
fn factorial (x: int) {
    if x <= 1 {
        return 1
    } else {
        return factorial(x - 1) * x
    }
}
```
