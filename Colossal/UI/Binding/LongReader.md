# Colossal.UI.Binding.LongReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IReader<System.Int64>`  

## Code

```csharp
public class LongReader : Colossal.UI.Binding.IReader<System.Int64>
{
    public LongReader();

    public System.Void Read(Colossal.UI.Binding.IJsonReader reader, System.Int64& value);
    public static System.Void ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.Int64& value);
}
```


## Constructors

- `public LongReader()`  

```csharp
public LongReader();
```


## Methods

- `public Read(Colossal.UI.Binding.IJsonReader reader, System.Int64& value) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader, System.Int64& value);
```

- `public static ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.Int64& value) : System.Void`  

```csharp
public static System.Void ReadFromArray(Colossal.UI.Binding.IJsonReader reader, System.Int64& value);
```


