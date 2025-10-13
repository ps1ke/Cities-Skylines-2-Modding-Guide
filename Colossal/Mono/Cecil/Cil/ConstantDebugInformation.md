# Colossal.Mono.Cecil.Cil.ConstantDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class ConstantDebugInformation : Colossal.Mono.Cecil.Cil.DebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    private Colossal.Mono.Cecil.TypeReference constant_type;
    private System.Object value;

    public System.String Name { get; set; }
    public Colossal.Mono.Cecil.TypeReference ConstantType { get; set; }
    public System.Object Value { get; set; }

    public ConstantDebugInformation(System.String name, Colossal.Mono.Cecil.TypeReference constant_type, System.Object value);

}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `private Colossal.Mono.Cecil.TypeReference constant_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference constant_type;
```

- `private System.Object value`  

```csharp
private System.Object value;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference ConstantType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ConstantType { get; set; }
```

- `public System.Object Value { get; set }`  

```csharp
public System.Object Value { get; set; }
```


## Constructors

- `public ConstantDebugInformation(System.String name, Colossal.Mono.Cecil.TypeReference constant_type, System.Object value)`  

```csharp
public ConstantDebugInformation(System.String name, Colossal.Mono.Cecil.TypeReference constant_type, System.Object value);
```


