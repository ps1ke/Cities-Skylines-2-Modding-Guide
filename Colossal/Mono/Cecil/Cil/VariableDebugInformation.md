# Colossal.Mono.Cecil.Cil.VariableDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class VariableDebugInformation : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    private System.UInt16 attributes;
    internal Colossal.Mono.Cecil.Cil.VariableIndex index;

    public System.Int32 Index { get; }
    public System.String Name { get; set; }
    public Colossal.Mono.Cecil.Cil.VariableAttributes Attributes { get; set; }
    public System.Boolean IsDebuggerHidden { get; set; }

    internal VariableDebugInformation(System.Int32 index, System.String name);
    public VariableDebugInformation(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String name);

}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `private System.UInt16 attributes`  

```csharp
private System.UInt16 attributes;
```

- `internal Colossal.Mono.Cecil.Cil.VariableIndex index`  

```csharp
internal Colossal.Mono.Cecil.Cil.VariableIndex index;
```


## Properties

- `public System.Int32 Index { get }`  

```csharp
public System.Int32 Index { get; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.VariableAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.VariableAttributes Attributes { get; set; }
```

- `public System.Boolean IsDebuggerHidden { get; set }`  

```csharp
public System.Boolean IsDebuggerHidden { get; set; }
```


## Constructors

- `internal VariableDebugInformation(System.Int32 index, System.String name)`  

```csharp
internal VariableDebugInformation(System.Int32 index, System.String name);
```

- `public VariableDebugInformation(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String name)`  

```csharp
public VariableDebugInformation(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String name);
```


