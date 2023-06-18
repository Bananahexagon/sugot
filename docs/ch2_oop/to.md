# 構造体と列挙型

```
// 構造体はstructキーワードを使って宣言できます
const Person = struct {
    name: String,
    age: u32,
}

// letで構造体を宣言することはできません
let Person = struct {
    name: String,
    age: u32,
} //コンパイルエラー

// 直接構造体を宣言することもできます
struct Person {
    name: String,
    age: u32,
}

```
