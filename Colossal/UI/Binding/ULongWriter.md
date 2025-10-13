# Colossal.UI.Binding.ULongWriter

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IWriter<System.UInt64>`  

## Code

```csharp
public class ULongWriter : Colossal.UI.Binding.IWriter<System.UInt64>
{
    public ULongWriter();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value);
    public static System.Void WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value);
}
```


## Constructors

- `public ULongWriter()`  

```csharp
public ULongWriter();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value);
```

- `public static WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value) : System.Void`  

```csharp
public static System.Void WriteAsArray(Colossal.UI.Binding.IJsonWriter writer, System.UInt64 value);
```


