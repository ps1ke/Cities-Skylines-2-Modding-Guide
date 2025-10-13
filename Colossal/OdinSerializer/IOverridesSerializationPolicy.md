# Colossal.OdinSerializer.IOverridesSerializationPolicy

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IOverridesSerializationPolicy
{
    public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get; }
    public System.Boolean OdinSerializesUnityFields { get; }

}
```


## Properties

- `public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get }`  

```csharp
public Colossal.OdinSerializer.ISerializationPolicy SerializationPolicy { get; }
```

- `public System.Boolean OdinSerializesUnityFields { get }`  

```csharp
public System.Boolean OdinSerializesUnityFields { get; }
```


