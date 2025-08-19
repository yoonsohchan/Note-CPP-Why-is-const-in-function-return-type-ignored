# Why is "const" in function return type, which is fundamental type, ignored?

- Because "const" applies to lvalue expressions only.

>[_"const semantics apply to lvalue expressions only"_](https://en.cppreference.com/w/c/language/const.html)

- Function return type, which is a fundamental type, is non-reference function return type, and non-reference function return type is prvalue.

>_The following expressions are **prvalue** expressions:_
>
>_..._
>
>- [_a function call or an overloaded operator expression, whose return type is non-reference_](https://en.cppreference.com/w/cpp/language/value_category.html)

Therefore,

```
const int Foo();
```
becomes / is identical to
```
int Foo();
```
