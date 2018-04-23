### <a name="il-ret-not-allowed-in-a-try-region"></a>IL ret try 区域中不允许

|   |   |
|---|---|
|详细信息|与 JIT64 中实时编译器，不同 （在.NET 4.6 中使用） 的 RyuJIT 不允许 IL ret try 区域中的指令。 Ecma-335 规范中，返回从 try 区域不允许并且没有已知的托管的编译器会生成此类 IL。 但是，如果由反射发出生成，则 JIT64 编译器执行此类 IL。|
|建议|如果应用程序生成的 IL try 区域中包括 ret 操作码，应用程序可能以.NET 4.5，以使用旧 JIT 并避免出现此中断目标。 或者，可能更新生成的 IL 之后重试区域，将返回。|
|范围|边缘|
|版本|4.6|
|类型|重定目标|
