# Colossal.UI.Binding.LongWriter

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IWriter<System.Int64>`  

## Code

```csharp
public class LongWriter : Colossal.UI.Binding.IWriter<System.Int64>
{
    public LongWriter();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value);
    public static System.Void WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value);
}
```


## Constructors

- `public LongWriter()`  

```csharp
public LongWriter();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value);
```

- `public static WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value) : System.Void`  

```csharp
public static System.Void WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.Int64 value);
```


