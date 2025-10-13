# Colossal.Mono.Cecil.Cil.ImportDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class ImportDebugInformation : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal Colossal.Mono.Cecil.Cil.ImportDebugInformation parent;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> targets;

    public System.Boolean HasTargets { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> Targets { get; }
    public Colossal.Mono.Cecil.Cil.ImportDebugInformation Parent { get; set; }

    public ImportDebugInformation();

}
```


## Fields

- `internal Colossal.Mono.Cecil.Cil.ImportDebugInformation parent`  

```csharp
internal Colossal.Mono.Cecil.Cil.ImportDebugInformation parent;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> targets`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> targets;
```


## Properties

- `public System.Boolean HasTargets { get }`  

```csharp
public System.Boolean HasTargets { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> Targets { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ImportTarget> Targets { get; }
```

- `public Colossal.Mono.Cecil.Cil.ImportDebugInformation Parent { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ImportDebugInformation Parent { get; set; }
```


## Constructors

- `public ImportDebugInformation()`  

```csharp
public ImportDebugInformation();
```


