# `fake` C++ meta-programming library

## ***brief:***

`fake` offers a set of tools of `meta-programming`<!--, `stateful meta-programming`--> and `concurrency adapter`.

## ***简介:***

`fake` 提供了一套 `元编程`<!--, `有状态元编程`--> 和 `并发适配器` 工具。

---

## ***compile:***

all codes compiled with `gcc-11.2.0`.

## ***编译:***

所有代码通过 `gcc-11.2.0` 编译。

---

### addtional parameters for `g++`

### 额外的 `g++` 参数

**`always` required:**
**`必需` 参数:**

```sh
-std=c++20 -iquote "fake/include"
```

- *the `fake/include` is the directory of the headers in the `repository` you cloned.*
- *`fake/include` 是 `仓库` 克隆目录内的头文件所在目录。*

---

<!---- >

**parameter for the `stateful meta-programming`:**
**`有状态元编程` 所需参数:**

```sh
-Wno-non-template-friend
```

---

<!---->

**parameter for the `concurrency adapter`:**
**`并发适配器` 所需参数:**

```sh
-fcoroutines
```

---

#### ***example:***

#### ***示例:***

`compile and launch the "demo/tuple.cpp"`
`编译并运行 "demo/tuple.cpp"`

```sh
cd ~
mkdir my_workspace
cd my_workspace
git clone https://github.com/fakeloop/fake
cd fake/demo
g++ tuple.cpp -std=c++20 -iquote "../include/" -o tuple.out
./tuple.out
```

<!---- >
***warning:***
***警告:***

the `stateful meta-programming` is some sort of **black magic**, which has always been ***controversial***.
`有状态元编程` 是一种 **黑魔法**, 一直以来都存在 ***争议***。

<!---->

---

## `meta-programming`

## `元编程`

***version:***
***版本:***

the `meta-programming` subsystem of `fake` is interface-stable currently.
`fake` `元编程` 子系统目前接口稳定。

---

<!---- >

### `"is_valid.h"`

---

### `"traits.h"`

---

<!---->

### `"symbol.h"`

***brief:***
compile time convert `type` to `constexpr std::string_view` or `fake::symbol::view`.

***简介:***
编译期将 `类型` 转换为 `constexpr std::string_view` 或 `fake::symbol::view`。

***usage:***
***使用方法:***

```c++
#include <iostrem>
#include "symbol.h"

int main(int, char*[]){
    std::cout << fake::symbol::string_view<decltype(main)>() << std::endl;
    return 0;
}
```

***output:***
***输出:***

```plain
int(int, char**)
```

---

<!---- >

### `"functor_info.h"`

---

<!---->

### `"tuple.h"`

***brief:***
compile time `lambda` functor algorithm tool kit for `std::tuple`.

***简介:***
用于 `std::tuple` 的 `lambda` 算子编译期算法工具集

***usage:***
***使用方法:***

```c++
#include "tuple.h"
```

***example:***
***示例:***

*demo see `"demo/tuple.cpp"`*
*示例见 `"demo/tuple.cpp"`*

---

<!---- >

## `stateful meta-programming`

## `有状态元编程`

---

<!---->

## `concurrency adapter`

## `并发适配器`

***version:***
***版本:***

the `concurrency adapter` subsystem of `fake` is **NOT** interface-stable yet.
`fake` `并发适配器` 子系统目前接口 **尚未** 稳定。