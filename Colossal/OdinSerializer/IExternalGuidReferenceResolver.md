# Colossal.OdinSerializer.IExternalGuidReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IExternalGuidReferenceResolver
{
    public Colossal.OdinSerializer.IExternalGuidReferenceResolver NextResolver { get; set; }

    public abstract System.Boolean CanReference(System.Object value, System.Guid& guid);
    public abstract System.Boolean TryResolveReference(System.Guid guid, System.Object& value);
}
```


## Properties

- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver NextResolver { get; set }`  

```csharp
public Colossal.OdinSerializer.IExternalGuidReferenceResolver NextResolver { get; set; }
```


## Methods

- `public abstract CanReference(System.Object value, System.Guid& guid) : System.Boolean`  

```csharp
public abstract System.Boolean CanReference(System.Object value, System.Guid& guid);
```

- `public abstract TryResolveReference(System.Guid guid, System.Object& value) : System.Boolean`  

```csharp
public abstract System.Boolean TryResolveReference(System.Guid guid, System.Object& value);
```


