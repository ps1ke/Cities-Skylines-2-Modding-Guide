# Colossal.Mono.Cecil.Cil.SourceLinkDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class SourceLinkDebugInformation : Colossal.Mono.Cecil.Cil.CustomDebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal System.String content;
    public static System.Guid KindIdentifier;

    public System.String Content { get; set; }
    public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }

    public SourceLinkDebugInformation(System.String content);

}
```


## Fields

- `internal System.String content`  

```csharp
internal System.String content;
```

- `public static System.Guid KindIdentifier`  

```csharp
public static System.Guid KindIdentifier;
```


## Properties

- `public System.String Content { get; set }`  

```csharp
public System.String Content { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }
```


## Constructors

- `public SourceLinkDebugInformation(System.String content)`  

```csharp
public SourceLinkDebugInformation(System.String content);
```


