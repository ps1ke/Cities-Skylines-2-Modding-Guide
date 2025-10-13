# Colossal.Mono.Cecil.Cil.BinaryCustomDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class BinaryCustomDebugInformation : Colossal.Mono.Cecil.Cil.CustomDebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.Byte[] data;

    public System.Byte[] Data { get; set; }
    public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }

    public BinaryCustomDebugInformation(System.Guid identifier, System.Byte[] data);

}
```


## Fields

- `private System.Byte[] data`  

```csharp
private System.Byte[] data;
```


## Properties

- `public System.Byte[] Data { get; set }`  

```csharp
public System.Byte[] Data { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }
```


## Constructors

- `public BinaryCustomDebugInformation(System.Guid identifier, System.Byte[] data)`  

```csharp
public BinaryCustomDebugInformation(System.Guid identifier, System.Byte[] data);
```


