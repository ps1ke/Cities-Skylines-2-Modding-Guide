# Colossal.OdinSerializer.SerializedUnityObject

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `UnityEngine.Object`  
**Implements:** `UnityEngine.ISerializationCallbackReceiver`  

## Code

```csharp
public abstract class SerializedUnityObject : UnityEngine.Object, UnityEngine.ISerializationCallbackReceiver
{
    private Colossal.OdinSerializer.SerializationData serializationData;

    protected SerializedUnityObject();

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


## Constructors

- `protected SerializedUnityObject()`  

```csharp
protected SerializedUnityObject();
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


