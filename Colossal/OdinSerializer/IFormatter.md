# Colossal.OdinSerializer.IFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IFormatter
{
    public System.Type SerializedType { get; }

    public abstract System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
    public abstract System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Properties

- `public System.Type SerializedType { get }`  

```csharp
public System.Type SerializedType { get; }
```


## Methods

- `public abstract Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public abstract System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
```

- `public abstract Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public abstract System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```


