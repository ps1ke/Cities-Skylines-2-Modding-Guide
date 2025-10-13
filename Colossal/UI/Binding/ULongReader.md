# Colossal.UI.Binding.ULongReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IReader<System.UInt64>`  

## Code

```csharp
public class ULongReader : Colossal.UI.Binding.IReader<System.UInt64>
{
    public ULongReader();

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value);
    public static System.Void ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value);
}
```


## Constructors

- `public ULongReader()`  

```csharp
public ULongReader();
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value);
```

- `public static ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value) : System.Void`  

```csharp
public static System.Void ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.UInt64& value);
```


