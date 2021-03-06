---
type: doc
layout: reference
category: "Other"
title: "相等判断"
---

# 相等判断

在 Kotlin 中存在两种相等判断:

* 引用相等 (两个引用指向同一个对象)
* 结构相等 (`equals()` 判断)

## 引用相等

引用相等使用 `===` 操作 (以及它的相反操作 `!==`) 来判断. 当, 且仅当, `a` 与`b` 指向同一个对象时, `a === b` 结果为 true.

## 结构相等

结构相等使用 `==` 操作 (以及它的相反操作 `!=`) 来判断. 按照约定, `a == b` 这样的表达式将被转换为:

``` kotlin
a?.equals(b) ?: (b === null)
```

也就是说, 如果 `a` 不为 `null`, 将会调用 `equals(Any?)` 函数, 否则(也就是 `a` 为 `null`) 将会检查 `b` 是否指向 `null`.

注意, 当明确地与 `null` 进行比较时, 没有必要优化代码: `a == null` 将会自动转换为 `a === null`.


