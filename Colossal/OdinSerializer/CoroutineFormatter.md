# Colossal.OdinSerializer.CoroutineFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatter<UnityEngine.Coroutine>`, `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class CoroutineFormatter : Colossal.OdinSerializer.IFormatter<UnityEngine.Coroutine>, Colossal.OdinSerializer.IFormatter
{
    public System.Type SerializedType { get; }

    public CoroutineFormatter();

    private System.Object Colossal.OdinSerializer.IFormatter.Deserialize(Colossal.OdinSerializer.IDataReader reader);
    public UnityEngine.Coroutine Deserialize(Colossal.OdinSerializer.IDataReader reader);
    public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
    public System.Void Serialize(UnityEngine.Coroutine value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Properties

- `public System.Type SerializedType { get }`  

```csharp
public System.Type SerializedType { get; }
```


## Constructors

- `public CoroutineFormatter()`  

```csharp
public CoroutineFormatter();
```


## Methods

- `private Colossal.OdinSerializer.IFormatter.Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
private System.Object Colossal.OdinSerializer.IFormatter.Deserialize(Colossal.OdinSerializer.IDataReader reader);
```

- `public Deserialize(Colossal.OdinSerializer.IDataReader reader) : UnityEngine.Coroutine`  

```csharp
public UnityEngine.Coroutine Deserialize(Colossal.OdinSerializer.IDataReader reader);
```

- `public Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```

- `public Serialize(UnityEngine.Coroutine value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public System.Void Serialize(UnityEngine.Coroutine value, Colossal.OdinSerializer.IDataWriter writer);
```


