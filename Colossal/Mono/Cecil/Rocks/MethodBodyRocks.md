# Colossal.Mono.Cecil.Rocks.MethodBodyRocks

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class MethodBodyRocks
{
    private static System.Void ComputeOffsets(Colossal.Mono.Cecil.Cil.MethodBody body);
    private static System.Void ExpandMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand);
    private static System.Void MakeMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode);
    public static System.Void Optimize(Colossal.Mono.Cecil.Cil.MethodBody self);
    private static System.Boolean OptimizeBranch(Colossal.Mono.Cecil.Cil.Instruction instruction);
    private static System.Void OptimizeBranches(Colossal.Mono.Cecil.Cil.MethodBody body);
    private static System.Void OptimizeLongs(Colossal.Mono.Cecil.Cil.MethodBody self);
    public static System.Void OptimizeMacros(Colossal.Mono.Cecil.Cil.MethodBody self);
    public static System.Void SimplifyMacros(Colossal.Mono.Cecil.Cil.MethodBody self);
}
```


## Methods

- `private static ComputeOffsets(Colossal.Mono.Cecil.Cil.MethodBody body) : System.Void`  

```csharp
private static System.Void ComputeOffsets(Colossal.Mono.Cecil.Cil.MethodBody body);
```

- `private static ExpandMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand) : System.Void`  

```csharp
private static System.Void ExpandMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand);
```

- `private static MakeMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Void`  

```csharp
private static System.Void MakeMacro(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public static Optimize(Colossal.Mono.Cecil.Cil.MethodBody self) : System.Void`  

```csharp
public static System.Void Optimize(Colossal.Mono.Cecil.Cil.MethodBody self);
```

- `private static OptimizeBranch(Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Boolean`  

```csharp
private static System.Boolean OptimizeBranch(Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `private static OptimizeBranches(Colossal.Mono.Cecil.Cil.MethodBody body) : System.Void`  

```csharp
private static System.Void OptimizeBranches(Colossal.Mono.Cecil.Cil.MethodBody body);
```

- `private static OptimizeLongs(Colossal.Mono.Cecil.Cil.MethodBody self) : System.Void`  

```csharp
private static System.Void OptimizeLongs(Colossal.Mono.Cecil.Cil.MethodBody self);
```

- `public static OptimizeMacros(Colossal.Mono.Cecil.Cil.MethodBody self) : System.Void`  

```csharp
public static System.Void OptimizeMacros(Colossal.Mono.Cecil.Cil.MethodBody self);
```

- `public static SimplifyMacros(Colossal.Mono.Cecil.Cil.MethodBody self) : System.Void`  

```csharp
public static System.Void SimplifyMacros(Colossal.Mono.Cecil.Cil.MethodBody self);
```


