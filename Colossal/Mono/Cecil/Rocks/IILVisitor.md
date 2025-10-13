# Colossal.Mono.Cecil.Rocks.IILVisitor

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Rocks`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IILVisitor
{
    public abstract System.Void OnInlineArgument(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
    public abstract System.Void OnInlineBranch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 offset);
    public abstract System.Void OnInlineByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
    public abstract System.Void OnInlineDouble(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
    public abstract System.Void OnInlineField(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
    public abstract System.Void OnInlineInt32(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
    public abstract System.Void OnInlineInt64(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
    public abstract System.Void OnInlineMethod(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
    public abstract System.Void OnInlineNone(Colossal.Mono.Cecil.Cil.OpCode opcode);
    public abstract System.Void OnInlineSByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
    public abstract System.Void OnInlineSignature(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite callSite);
    public abstract System.Void OnInlineSingle(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
    public abstract System.Void OnInlineString(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
    public abstract System.Void OnInlineSwitch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32[] offsets);
    public abstract System.Void OnInlineType(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
    public abstract System.Void OnInlineVariable(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
}
```


## Methods

- `public abstract OnInlineArgument(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : System.Void`  

```csharp
public abstract System.Void OnInlineArgument(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
```

- `public abstract OnInlineBranch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 offset) : System.Void`  

```csharp
public abstract System.Void OnInlineBranch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 offset);
```

- `public abstract OnInlineByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : System.Void`  

```csharp
public abstract System.Void OnInlineByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
```

- `public abstract OnInlineDouble(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : System.Void`  

```csharp
public abstract System.Void OnInlineDouble(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
```

- `public abstract OnInlineField(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : System.Void`  

```csharp
public abstract System.Void OnInlineField(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
```

- `public abstract OnInlineInt32(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : System.Void`  

```csharp
public abstract System.Void OnInlineInt32(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
```

- `public abstract OnInlineInt64(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : System.Void`  

```csharp
public abstract System.Void OnInlineInt64(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
```

- `public abstract OnInlineMethod(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : System.Void`  

```csharp
public abstract System.Void OnInlineMethod(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
```

- `public abstract OnInlineNone(Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Void`  

```csharp
public abstract System.Void OnInlineNone(Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public abstract OnInlineSByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : System.Void`  

```csharp
public abstract System.Void OnInlineSByte(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
```

- `public abstract OnInlineSignature(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite callSite) : System.Void`  

```csharp
public abstract System.Void OnInlineSignature(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite callSite);
```

- `public abstract OnInlineSingle(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : System.Void`  

```csharp
public abstract System.Void OnInlineSingle(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
```

- `public abstract OnInlineString(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : System.Void`  

```csharp
public abstract System.Void OnInlineString(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
```

- `public abstract OnInlineSwitch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32[] offsets) : System.Void`  

```csharp
public abstract System.Void OnInlineSwitch(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32[] offsets);
```

- `public abstract OnInlineType(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : System.Void`  

```csharp
public abstract System.Void OnInlineType(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
```

- `public abstract OnInlineVariable(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : System.Void`  

```csharp
public abstract System.Void OnInlineVariable(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
```


