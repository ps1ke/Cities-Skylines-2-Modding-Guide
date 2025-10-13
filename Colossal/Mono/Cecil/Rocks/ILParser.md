# Colossal.Mono.Cecil.Rocks.ILParser

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ILParser
{
    private static Colossal.Mono.Cecil.Rocks.ILParser+ParseContext CreateContext(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
    private static Colossal.Mono.Cecil.Cil.VariableDefinition GetVariable(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context, System.Int32 index);
    public static System.Void Parse(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
    private static System.Void ParseCode(System.Int32 code_size, Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context);
    private static System.Void ParseFatMethod(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context);
    private static System.Void ParseMethod(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
}
```


## Methods

- `private static CreateContext(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor) : Colossal.Mono.Cecil.Rocks.ILParser+ParseContext`  

```csharp
private static Colossal.Mono.Cecil.Rocks.ILParser+ParseContext CreateContext(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
```

- `private static GetVariable(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context, System.Int32 index) : Colossal.Mono.Cecil.Cil.VariableDefinition`  

```csharp
private static Colossal.Mono.Cecil.Cil.VariableDefinition GetVariable(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context, System.Int32 index);
```

- `public static Parse(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor) : System.Void`  

```csharp
public static System.Void Parse(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
```

- `private static ParseCode(System.Int32 code_size, Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context) : System.Void`  

```csharp
private static System.Void ParseCode(System.Int32 code_size, Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context);
```

- `private static ParseFatMethod(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context) : System.Void`  

```csharp
private static System.Void ParseFatMethod(Colossal.Mono.Cecil.Rocks.ILParser+ParseContext context);
```

- `private static ParseMethod(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor) : System.Void`  

```csharp
private static System.Void ParseMethod(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.Rocks.IILVisitor visitor);
```


## Nested types

- `Colossal.Mono.Cecil.Rocks.ILParser+ParseContext`  
- `Colossal.Mono.Cecil.Rocks.ILParser+<>c`  
- `Colossal.Mono.Cecil.Rocks.ILParser+<>c__DisplayClass1_0`  

