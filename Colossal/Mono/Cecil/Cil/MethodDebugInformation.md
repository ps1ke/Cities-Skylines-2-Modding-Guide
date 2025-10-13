# Colossal.Mono.Cecil.Cil.MethodDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class MethodDebugInformation : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal Colossal.Mono.Cecil.MethodDefinition method;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points;
    internal Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope;
    internal Colossal.Mono.Cecil.MethodDefinition kickoff_method;
    internal System.Int32 code_size;
    internal Colossal.Mono.Cecil.MetadataToken local_var_token;

    public Colossal.Mono.Cecil.MethodDefinition Method { get; }
    public System.Boolean HasSequencePoints { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> SequencePoints { get; }
    public Colossal.Mono.Cecil.Cil.ScopeDebugInformation Scope { get; set; }
    public Colossal.Mono.Cecil.MethodDefinition StateMachineKickOffMethod { get; set; }

    internal MethodDebugInformation(Colossal.Mono.Cecil.MethodDefinition method);

    public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> GetScopes();
    private static System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> GetScopes(System.Collections.Generic.IList<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes);
    public Colossal.Mono.Cecil.Cil.SequencePoint GetSequencePoint(Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Collections.Generic.IDictionary<Colossal.Mono.Cecil.Cil.Instruction, Colossal.Mono.Cecil.Cil.SequencePoint> GetSequencePointMapping();
    public System.Boolean TryGetName(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String& name);
}
```


## Fields

- `internal Colossal.Mono.Cecil.MethodDefinition method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition method;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points;
```

- `internal Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope`  

```csharp
internal Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope;
```

- `internal Colossal.Mono.Cecil.MethodDefinition kickoff_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition kickoff_method;
```

- `internal System.Int32 code_size`  

```csharp
internal System.Int32 code_size;
```

- `internal Colossal.Mono.Cecil.MetadataToken local_var_token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken local_var_token;
```


## Properties

- `public Colossal.Mono.Cecil.MethodDefinition Method { get }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition Method { get; }
```

- `public System.Boolean HasSequencePoints { get }`  

```csharp
public System.Boolean HasSequencePoints { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> SequencePoints { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> SequencePoints { get; }
```

- `public Colossal.Mono.Cecil.Cil.ScopeDebugInformation Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ScopeDebugInformation Scope { get; set; }
```

- `public Colossal.Mono.Cecil.MethodDefinition StateMachineKickOffMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition StateMachineKickOffMethod { get; set; }
```


## Constructors

- `internal MethodDebugInformation(Colossal.Mono.Cecil.MethodDefinition method)`  

```csharp
internal MethodDebugInformation(Colossal.Mono.Cecil.MethodDefinition method);
```


## Methods

- `public GetScopes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> GetScopes();
```

- `private static GetScopes(System.Collections.Generic.IList<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes) : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  

```csharp
private static System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> GetScopes(System.Collections.Generic.IList<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes);
```

- `public GetSequencePoint(Colossal.Mono.Cecil.Cil.Instruction instruction) : Colossal.Mono.Cecil.Cil.SequencePoint`  

```csharp
public Colossal.Mono.Cecil.Cil.SequencePoint GetSequencePoint(Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public GetSequencePointMapping() : System.Collections.Generic.IDictionary<Colossal.Mono.Cecil.Cil.Instruction, Colossal.Mono.Cecil.Cil.SequencePoint>`  

```csharp
public System.Collections.Generic.IDictionary<Colossal.Mono.Cecil.Cil.Instruction, Colossal.Mono.Cecil.Cil.SequencePoint> GetSequencePointMapping();
```

- `public TryGetName(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String& name) : System.Boolean`  

```csharp
public System.Boolean TryGetName(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String& name);
```


## Nested types

- `Colossal.Mono.Cecil.Cil.MethodDebugInformation+<GetScopes>d__22`  

