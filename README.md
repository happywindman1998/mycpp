# mycpp
c++笔记
# 类型转换
对变量的初始化有两种
1.int a=2.0  自动做类型转换
2.int a{2.0} 非法，不自动做类型转换
3.int a{c}   c必须是const 或#define,否则非法
# 常量赋值默认类型
a=10 a为int
a=10.0 a为double

做运算时
如果short比int短，则unsigned short类型将
被转换为int；如果两种类型的长度相同，则unsigned short类型将被转换
为unsigned int。这种规则确保了在对unsigned short进行提升时不会损失
数据。
同样，wchar_t被提升成为下列类型中第一个宽度足够存储wchar_t
取值范围的类型：int、unsigned int、long或unsigned long。
# 联合体
共用体（union）是一种数据格式，它能够存储不同的数据类型，
但只能同时存储其中的一种类型。成员名称标识了变量的容量。由于共用体每次只能存储一个值，因此它必须
有足够的空间来存储最大的成员，所以，共用体的长度为其最大成员的
长度。
# 枚举类型
枚举量是整型，可被提升为int类型，但int类型不能自动转换为枚举
类型。
enum var{red,blue,green,purple}; //将red、blue、green等作为符号常量，它们对应整数值0～3。这些常量叫作枚举量（enumerator）
int a=blue //正确，枚举类型可以被提升为int
var band
band=blue 
band=3 //错误，int类型不可转为enum