# Colossal.Mono.Cecil.ArrayMarshalInfo

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.MarshalInfo`  

## Code

```csharp
public sealed class ArrayMarshalInfo : Colossal.Mono.Cecil.MarshalInfo
{
    internal Colossal.Mono.Cecil.NativeType element_type;
    internal System.Int32 size_parameter_index;
    internal System.Int32 size;
    internal System.Int32 size_parameter_multiplier;

    public Colossal.Mono.Cecil.NativeType ElementType { get; set; }
    public System.Int32 SizeParameterIndex { get; set; }
    public System.Int32 Size { get; set; }
    public System.Int32 SizeParameterMultiplier { get; set; }

    public ArrayMarshalInfo();

}
```


## Fields

- `internal Colossal.Mono.Cecil.NativeType element_type`  

```csharp
internal Colossal.Mono.Cecil.NativeType element_type;
```

- `internal System.Int32 size_parameter_index`  

```csharp
internal System.Int32 size_parameter_index;
```

- `internal System.Int32 size`  

```csharp
internal System.Int32 size;
```

- `internal System.Int32 size_parameter_multiplier`  

```csharp
internal System.Int32 size_parameter_multiplier;
```


## Properties

- `public Colossal.Mono.Cecil.NativeType ElementType { get; set }`  

```csharp
public Colossal.Mono.Cecil.NativeType ElementType { get; set; }
```

- `public System.Int32 SizeParameterIndex { get; set }`  

```csharp
public System.Int32 SizeParameterIndex { get; set; }
```

- `public System.Int32 Size { get; set }`  

```csharp
public System.Int32 Size { get; set; }
```

- `public System.Int32 SizeParameterMultiplier { get; set }`  

```csharp
public System.Int32 SizeParameterMultiplier { get; set; }
```


## Constructors

- `public ArrayMarshalInfo()`  

```csharp
public ArrayMarshalInfo();
```


