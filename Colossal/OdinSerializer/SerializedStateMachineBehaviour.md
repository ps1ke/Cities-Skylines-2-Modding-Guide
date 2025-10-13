# Colossal.OdinSerializer.SerializedStateMachineBehaviour

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `UnityEngine.StateMachineBehaviour`  
**Implements:** `UnityEngine.ISerializationCallbackReceiver`  

## Code

```csharp
public abstract class SerializedStateMachineBehaviour : UnityEngine.StateMachineBehaviour, UnityEngine.ISerializationCallbackReceiver
{
    private Colossal.OdinSerializer.SerializationData serializationData;

    protected SerializedStateMachineBehaviour();

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

- `protected SerializedStateMachineBehaviour()`  

```csharp
protected SerializedStateMachineBehaviour();
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


