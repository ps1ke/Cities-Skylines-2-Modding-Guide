# Colossal.Json.IJsonConverter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IJsonConverter
{
    public abstract System.Object ObjectFromJson(Colossal.Json.Variant data);
    public abstract Colossal.Json.Variant ObjectToJson(System.Object value);
}
```


## Methods

- `public abstract ObjectFromJson(Colossal.Json.Variant data) : System.Object`  

```csharp
public abstract System.Object ObjectFromJson(Colossal.Json.Variant data);
```

- `public abstract ObjectToJson(System.Object value) : Colossal.Json.Variant`  

```csharp
public abstract Colossal.Json.Variant ObjectToJson(System.Object value);
```


