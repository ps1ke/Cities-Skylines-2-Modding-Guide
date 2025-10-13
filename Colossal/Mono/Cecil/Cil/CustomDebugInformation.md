# Colossal.Mono.Cecil.Cil.CustomDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class CustomDebugInformation : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.Guid identifier;

    public System.Guid Identifier { get; }
    public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }

    internal CustomDebugInformation(System.Guid identifier);

}
```


## Fields

- `private System.Guid identifier`  

```csharp
private System.Guid identifier;
```


## Properties

- `public System.Guid Identifier { get }`  

```csharp
public System.Guid Identifier { get; }
```

- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }
```


## Constructors

- `internal CustomDebugInformation(System.Guid identifier)`  

```csharp
internal CustomDebugInformation(System.Guid identifier);
```


