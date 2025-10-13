# Colossal.OdinSerializer.WeakPrimitiveArrayFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakMinimalBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakPrimitiveArrayFormatter : Colossal.OdinSerializer.WeakMinimalBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly System.Type ElementType;
    private readonly Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType PrimitiveType;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType> PrimitiveTypes;

    public WeakPrimitiveArrayFormatter(System.Type arrayType, System.Type elementType);

    protected virtual System.Object GetUninitializedObject();
    protected virtual System.Void Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly System.Type ElementType`  

```csharp
private readonly System.Type ElementType;
```

- `private readonly Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType PrimitiveType`  

```csharp
private readonly Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType PrimitiveType;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType> PrimitiveTypes`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType> PrimitiveTypes;
```


## Constructors

- `public WeakPrimitiveArrayFormatter(System.Type arrayType, System.Type elementType)`  

```csharp
public WeakPrimitiveArrayFormatter(System.Type arrayType, System.Type elementType);
```


## Methods

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```

- `protected virtual Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


## Nested types

- `Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType`  

