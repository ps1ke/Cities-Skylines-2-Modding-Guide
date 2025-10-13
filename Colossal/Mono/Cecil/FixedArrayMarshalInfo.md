# Colossal.Mono.Cecil.FixedArrayMarshalInfo

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.MarshalInfo`  

## Code

```csharp
public sealed class FixedArrayMarshalInfo : Colossal.Mono.Cecil.MarshalInfo
{
    internal Colossal.Mono.Cecil.NativeType element_type;
    internal System.Int32 size;

    public Colossal.Mono.Cecil.NativeType ElementType { get; set; }
    public System.Int32 Size { get; set; }

    public FixedArrayMarshalInfo();

}
```


## Fields

- `internal Colossal.Mono.Cecil.NativeType element_type`  

```csharp
internal Colossal.Mono.Cecil.NativeType element_type;
```

- `internal System.Int32 size`  

```csharp
internal System.Int32 size;
```


## Properties

- `public Colossal.Mono.Cecil.NativeType ElementType { get; set }`  

```csharp
public Colossal.Mono.Cecil.NativeType ElementType { get; set; }
```

- `public System.Int32 Size { get; set }`  

```csharp
public System.Int32 Size { get; set; }
```


## Constructors

- `public FixedArrayMarshalInfo()`  

```csharp
public FixedArrayMarshalInfo();
```


