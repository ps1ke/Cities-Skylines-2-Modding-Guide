# Colossal.OdinSerializer.IExternalIndexReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IExternalIndexReferenceResolver
{
    public abstract System.Boolean CanReference(System.Object value, System.Int32& index);
    public abstract System.Boolean TryResolveReference(System.Int32 index, System.Object& value);
}
```


## Methods

- `public abstract CanReference(System.Object value, System.Int32& index) : System.Boolean`  

```csharp
public abstract System.Boolean CanReference(System.Object value, System.Int32& index);
```

- `public abstract TryResolveReference(System.Int32 index, System.Object& value) : System.Boolean`  

```csharp
public abstract System.Boolean TryResolveReference(System.Int32 index, System.Object& value);
```


