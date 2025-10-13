# Colossal.Mono.Cecil.Cil.MethodBody

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class MethodBody
{
    internal readonly Colossal.Mono.Cecil.MethodDefinition method;
    internal Colossal.Mono.Cecil.ParameterDefinition this_parameter;
    internal System.Int32 max_stack_size;
    internal System.Int32 code_size;
    internal System.Boolean init_locals;
    internal Colossal.Mono.Cecil.MetadataToken local_var_token;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> exceptions;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> variables;

    public Colossal.Mono.Cecil.MethodDefinition Method { get; }
    public System.Int32 MaxStackSize { get; set; }
    public System.Int32 CodeSize { get; }
    public System.Boolean InitLocals { get; set; }
    public Colossal.Mono.Cecil.MetadataToken LocalVarToken { get; set; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> Instructions { get; }
    public System.Boolean HasExceptionHandlers { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> ExceptionHandlers { get; }
    public System.Boolean HasVariables { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> Variables { get; }
    public Colossal.Mono.Cecil.ParameterDefinition ThisParameter { get; }

    public MethodBody(Colossal.Mono.Cecil.MethodDefinition method);

    private static Colossal.Mono.Cecil.ParameterDefinition CreateThisParameter(Colossal.Mono.Cecil.MethodDefinition method);
    public Colossal.Mono.Cecil.Cil.ILProcessor GetILProcessor();
}
```


## Fields

- `internal readonly Colossal.Mono.Cecil.MethodDefinition method`  

```csharp
internal readonly Colossal.Mono.Cecil.MethodDefinition method;
```

- `internal Colossal.Mono.Cecil.ParameterDefinition this_parameter`  

```csharp
internal Colossal.Mono.Cecil.ParameterDefinition this_parameter;
```

- `internal System.Int32 max_stack_size`  

```csharp
internal System.Int32 max_stack_size;
```

- `internal System.Int32 code_size`  

```csharp
internal System.Int32 code_size;
```

- `internal System.Boolean init_locals`  

```csharp
internal System.Boolean init_locals;
```

- `internal Colossal.Mono.Cecil.MetadataToken local_var_token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken local_var_token;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> exceptions`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> exceptions;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> variables`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> variables;
```


## Properties

- `public Colossal.Mono.Cecil.MethodDefinition Method { get }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition Method { get; }
```

- `public System.Int32 MaxStackSize { get; set }`  

```csharp
public System.Int32 MaxStackSize { get; set; }
```

- `public System.Int32 CodeSize { get }`  

```csharp
public System.Int32 CodeSize { get; }
```

- `public System.Boolean InitLocals { get; set }`  

```csharp
public System.Boolean InitLocals { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataToken LocalVarToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken LocalVarToken { get; set; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> Instructions { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> Instructions { get; }
```

- `public System.Boolean HasExceptionHandlers { get }`  

```csharp
public System.Boolean HasExceptionHandlers { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> ExceptionHandlers { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ExceptionHandler> ExceptionHandlers { get; }
```

- `public System.Boolean HasVariables { get }`  

```csharp
public System.Boolean HasVariables { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> Variables { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDefinition> Variables { get; }
```

- `public Colossal.Mono.Cecil.ParameterDefinition ThisParameter { get }`  

```csharp
public Colossal.Mono.Cecil.ParameterDefinition ThisParameter { get; }
```


## Constructors

- `public MethodBody(Colossal.Mono.Cecil.MethodDefinition method)`  

```csharp
public MethodBody(Colossal.Mono.Cecil.MethodDefinition method);
```


## Methods

- `private static CreateThisParameter(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.ParameterDefinition`  

```csharp
private static Colossal.Mono.Cecil.ParameterDefinition CreateThisParameter(Colossal.Mono.Cecil.MethodDefinition method);
```

- `public GetILProcessor() : Colossal.Mono.Cecil.Cil.ILProcessor`  

```csharp
public Colossal.Mono.Cecil.Cil.ILProcessor GetILProcessor();
```


