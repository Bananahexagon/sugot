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

// implキーワードを使ってメソッドや関連関数を実装します。
impl Person {
    fn new(name, age) -> Self {
        return Self {
            name: name,
            age: age,
        } //すでに宣言された構造体なら、直接書くことができます。
    }
    fn sayHello(self: &self) {
        println("Hello, my name is ", self.name, "!." )
    } //メソッドとして実装するなら第一引数にselfという名前で&selfの参照を受け取ります。
}

// 列挙型はstructキーワードを使って宣言できます
const Animal = enum {
    dog,
    cat,
    elephant,
}

// 直接列挙型を宣言することもできます
enum Animal {
    dog,
    cat,
    elephant,
}

//列挙型はフィールドを持つこともできます。
enum Animal {
    hunan: Person,
    dog,
    cat,
    elephant,
}

//列挙型もimplキーワードを使って実装します。

```
