# solidity_note
智能合约学习笔记

---- 

`memory`：存储位置同我们普通程序的内存一致。即分配，即使用，越过作用域即不可被访问，等待被回收。


`storage`：这种类型了，一旦使用这个类型，数据将永远存在。


`calldata`：它存储的是函数参数，是只读的，不会永久存储的一个数据位置。外部函数的参数（不包括返回参数）被强制指定为calldata。效果与memory差不多。

    强制的数据位置
    
    外部函数(External function)的参数(不包括返回参数)强制为：calldata
    
    状态变量:强制为: storage

```pragma solidity ^0.4.0;
contract StateVariable{
      struct S{string a;uint b;}
      //状态变量，默认是storage
      S s;
}
```
默认数据位置

    函数参数，返回参数：memory
    
    局部变量：storage
