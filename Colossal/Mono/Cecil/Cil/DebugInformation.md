# Colossal.Mono.Cecil.Cil.DebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class DebugInformation : Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal Colossal.Mono.Cecil.MetadataToken token;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos;

    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public System.Boolean HasCustomDebugInformations { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get; }

    internal DebugInformation();

}
```


## Fields

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos;
```


## Properties

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public System.Boolean HasCustomDebugInformations { get }`  

```csharp
public System.Boolean HasCustomDebugInformations { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get; }
```


## Constructors

- `internal DebugInformation()`  

```csharp
internal DebugInformation();
```


