# About
关于我的一些东西吧

## 目录

* [介绍](#介绍)
* [Commit message 格式](#Commit-message-格式]
* [代码样式](#代码样式)
  * [C](#C)
    * [include](#include)
    * [function](#function)
    * [表达式](#表达式)
* [LICENSE](LICENSE)

## 介绍

Hello! 我叫辰落火辉Haceau，你同样可以叫我 辰落火辉，Haceau，Zoac，或者辰落/辰辰之类也没关系

这个项目主要就是关于我所有的项目的一些东西

嗯其实没什么

## Commit message 格式

一律使用 Angular 的格式

## 代码样式

### C

#### include

```c
#include "本文件对应的.h"
#include <标准库>
#include <外部库>
#include "本项目的其他.h"
```

#### function

```c
// 不可省略返回值：
/// bad
foo(void)
{
    return 1;
}
/// good
int foo(void)
{
    return 1;
}
// 大括号换行
/// bad
int foo(void) {
    return 1;
}
/// good
int foo(void)
{
    return 1;
}
// 空参数列表应显示用 void 指示
/// bad
int foo()
{
	return 1;
}
/// good
int foo(void)
{
    return 1;
}
// 短函数可只占一样
int foo(void) { return 1; }
// 错误处理到位
/// bad
void foo(char* str) { free(str); }
/// good
_Bool foo(char* str)
{
    _Bool success = false;
    if (str != NULL)
    {
        free(str);
        str = NULL;
		success = true;
	}
    return success;
}
```

### 表达式

```c
// 复杂表达式使用 () 明确运算顺序
/// bad
1 > 2 ? 3 > 4 ? 5 > 6 == true || 7 < 8 == false ? 12 : 3 : 1 : 2;
/// good
  (1 > 2)
? ((3 > 4) 
   ? (((5 > 6) || !(7 < 8)) 
      ? 12 
      : 3) 
   : 1) 
: 2;
// == true 或 == false 不要出现
/// bad
1 == true;
/// good
1;
/// bad
1 == false ? true : false;
/// good
!1;
```



## LICENSE

此项目所有内容皆为 MIT License，详见 [LICENSE](LICENSE)
