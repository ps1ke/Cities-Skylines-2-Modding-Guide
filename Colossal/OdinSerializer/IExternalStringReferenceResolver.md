# Colossal.OdinSerializer.IExternalStringReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IExternalStringReferenceResolver
{
    public Colossal.OdinSerializer.IExternalStringReferenceResolver NextResolver { get; set; }

    public abstract System.Boolean CanReference(System.Object value, System.String& id);
    public abstract System.Boolean TryResolveReference(System.Type serializedType, System.String id, System.Object& value);
}
```


## Properties

- `public Colossal.OdinSerializer.IExternalStringReferenceResolver NextResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalStringReferenceResolver NextResolver { get; set; }
```


## Methods

- `public abstract CanReference(System.Object value, System.String& id) : System.Boolean`  

```csharp
public abstract System.Boolean CanReference(System.Object value, System.String& id);
```

- `public abstract TryResolveReference(System.Type serializedType, System.String id, System.Object& value) : System.Boolean`  

```csharp
public abstract System.Boolean TryResolveReference(System.Type serializedType, System.String id, System.Object& value);
```


