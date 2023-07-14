# 副作用と参照透過性

```
// 関数に副作用がないことを明示的に書くにはsidelessと書きます。
sideless fn add(x, y) {
    return x + y
}

// 関数が参照等価であることを明示的に書くにはreftransと書きます。
reftrans fn add(x, y) {
    return x + y
}

// 純粋関数である(つまり副作用がなく参照等価である)ことを明示的に書くにはpureと書きます。
pure fn add(x, y) {
    return x + y
}

// sidelessな関数の中でsidelessでない関数を呼び出すことはできません。
let x = 0
sideless fn increment_x() {
    x++ //コンパイルエラー
}

//reftransやpureについも同様です。
let x = 0
pure fn increment_x() {
    x++ //コンパイルエラー
}
```
