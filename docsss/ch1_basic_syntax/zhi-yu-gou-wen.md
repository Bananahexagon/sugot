---
description: ifやforなどの制御構文について説明します。
---

# 制御構文

## if式

条件分岐をするにはif式を使います。

```
if x == 5 {
    print("x is five")
}
```

条件を満たさなかった時に何か処理をするには、`else`を使います。

```
if x == 5 {
    print("x is five")
} else {
    print("x is not five")
}
```

さらに別の条件で分岐するには、`else if`を使います。

```
if x == 5 {
    print("x is five")
} else is x == 3 {
    print("x is three")
} else {
    print("x is not five or three")
}
```

条件に一致したブロックの末尾の式の値が`if`式全体の値になります。

```
let y = if x == 5 {
    "x is five"
} else is x == 3 {
    "x is three"
} else {
    "x is not five or three"
}
```

## match式

一つの変数の値を調べながら分岐したい場合は、`match`式を使います。

```
match x {
    0 => print(x is zero)
    1 => print(x is one)
    2 => print(x is two)
    3 => print(x is three)
    4 => print(x is four)
    5 => print(x is five)
    _ => print(maybe x is bigger than five)
}
```

アンダーバーはワイルドカードで、どの値にもマッチしなかったときなどに使います。

## while式

`while`式は、条件式が真の間だけずっとループします。

```
let x = 5
while x != 0 {
    x--
    print(x)
}
/*
 *4
 *3
 *2
 *1
 *0
 */
```

## for式

`for`式は、配列やベクタを受け取って各要素を順番に処理したいときに使います。

```
let x = [0, 1, 4, 9, 16]
for i in x {
    print(x)
}
/*
 *0
 *1
 *4
 *9
 *16
 */
```

`while`式や`for`式の値は、最後のループでの値になります。

```
let x = [0, 1, 4, 9, 16]
let y = for i in x {
    print(x)
    x
} //16
```

`while`や`for`のループは、`break`によっていつでも抜けることができます。

```
let x = [0, 1, 4, 9, 16]
for i in x {
    print(x)
    if x == 9 {
        break
    }
}
/*
 *0
 *1
 *4
 *9
 */
```

`break`の代わりに`continue`を使うと、ループを抜ける代わりにすぐに次のループに移ります。

```
let x = [0, 1, 4, 9, 16]
for i in x {
    if x == 9 {
        continue
    }
    print(x)
}
/*
 *0
 *1
 *4
 *16
 */
```

`break`や`contiune`の後に式を書くと、ループを抜けたときに返す値を設定できます。

```
let x = [0, 1, 4, 9, 16]
let y = for i in x {
    print(x)
    if x == 9 {
        break "x is nine!"
    }
} //"x is nine!"
/*
 *0
 *1
 *4
 *9
 */
```

ラベルを使うことで、`break`の`continue`の対象のループを選択できます。

```
let x = [0, 1, 4, 9, 16]
loop1: for i in x {
    print(x)
    if x == 9 {
        break void loop1
    }
}
```
