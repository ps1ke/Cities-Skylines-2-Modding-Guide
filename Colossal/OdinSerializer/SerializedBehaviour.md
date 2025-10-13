# Colossal.OdinSerializer.SerializedBehaviour

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `UnityEngine.Behaviour`  
**Implements:** `UnityEngine.ISerializationCallbackReceiver`, `Colossal.OdinSerializer.ISupportsPrefabSerialization`  

## Code

```csharp
public abstract class SerializedBehaviour : UnityEngine.Behaviour, UnityEngine.ISerializationCallbackReceiver, Colossal.OdinSerializer.ISupportsPrefabSerialization
{
    private Colossal.OdinSerializer.SerializationData serializationData;

    private Colossal.OdinSerializer.SerializationData Colossal.OdinSerializer.ISupportsPrefabSerialization.SerializationData { private get; private set; }

    protected SerializedBehaviour();

    protected virtual System.Void OnAfterDeserialize();
    protected virtual System.Void OnBeforeSerialize();
    private System.Void UnityEngine.ISerializationCallbackReceiver.OnAfterDeserialize();
    private System.Void UnityEngine.ISerializationCallbackReceiver.OnBeforeSerialize();
}
```


## Fields

- `private Colossal.OdinSerializer.SerializationData serializationData`  

```csharp
private Colossal.OdinSerializer.SerializationData serializationData;
```


## Properties

- `private Colossal.OdinSerializer.SerializationData Colossal.OdinSerializer.ISupportsPrefabSerialization.SerializationData { private get; private set }`  

```csharp
private Colossal.OdinSerializer.SerializationData Colossal.OdinSerializer.ISupportsPrefabSerialization.SerializationData { private get; private set; }
```


## Constructors

- `protected SerializedBehaviour()`  

```csharp
protected SerializedBehaviour();
```


## Methods

- `protected virtual OnAfterDeserialize() : System.Void`  

```csharp
protected virtual System.Void OnAfterDeserialize();
```

- `protected virtual OnBeforeSerialize() : System.Void`  

```csharp
protected virtual System.Void OnBeforeSerialize();
```

- `private UnityEngine.ISerializationCallbackReceiver.OnAfterDeserialize() : System.Void`  

```csharp
private System.Void UnityEngine.ISerializationCallbackReceiver.OnAfterDeserialize();
```

- `private UnityEngine.ISerializationCallbackReceiver.OnBeforeSerialize() : System.Void`  

```csharp
private System.Void UnityEngine.ISerializationCallbackReceiver.OnBeforeSerialize();
```


