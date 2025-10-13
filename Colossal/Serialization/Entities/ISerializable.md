# Colossal.Serialization.Entities.ISerializable

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ISerializable
{
    public abstract System.Void Deserialize<TReader>(TReader reader);
    public abstract System.Void Serialize<TWriter>(TWriter writer);
}
```


## Methods

- `public abstract Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public abstract System.Void Deserialize<TReader>(TReader reader);
```

- `public abstract Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public abstract System.Void Serialize<TWriter>(TWriter writer);
```


