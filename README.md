# sjson
Smart JSON Specification

# Description
This specification extends JSON specification and adds more features.
All json basics will be left unchanged.

# Embedded values
With smartjson you can set an embedded value with calling a smartjson function (sjson-funcs, SmartJSON funcs) that will return it.

### Syntax
Smartjson function identifier is `@`. sjson-funcs are called when used as value without qoutes,
so you can't use it in strings or concatenate it.

In this examples we'll use `funcName` as an example of user-defined function name.

Full syntax:
```
@funcName[(arg1="a"[, arg2=123[, arg3=bool]])]
```

Usage example:
```
{
  "stdBool": true,
  "stdInt": 123,
  "strStr": "a string",
  
  "sjsonFuncCall": @funcName,
  "sjsonFuncCallWithOneArg": @funcName(arg1="a"),
  "sjsonFuncCallWithMultiArgs": @funcName(arg1="a", arg2=123, arg3=true),
}
```

SmartJSON func call without args:
```
@funcName
```

SmartJSON func call with one arg:
```
@funcName(arg1=1)
```

SmartJSON func call with multiple args:
```
@funcName(arg1=1, arg2=123, arg3=false)
```

