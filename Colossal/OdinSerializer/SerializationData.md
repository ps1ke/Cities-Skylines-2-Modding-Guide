# Colossal.OdinSerializer.SerializationData

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct SerializationData
{
    public Colossal.OdinSerializer.DataFormat SerializedFormat;
    public System.Byte[] SerializedBytes;
    public System.Collections.Generic.List<UnityEngine.Object> ReferencedUnityObjects;
    public System.String SerializedBytesString;
    public UnityEngine.Object Prefab;
    public System.Collections.Generic.List<UnityEngine.Object> PrefabModificationsReferencedUnityObjects;
    public System.Collections.Generic.List<System.String> PrefabModifications;
    public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> SerializationNodes;
    public static const System.String PrefabModificationsReferencedUnityObjectsFieldName;
    public static const System.String PrefabModificationsFieldName;
    public static const System.String PrefabFieldName;

    public System.Boolean HasEditorData { get; }
    public System.Boolean ContainsData { get; }

    public System.Void Reset();
}
```


## Fields

- `public Colossal.OdinSerializer.DataFormat SerializedFormat`  

```csharp
public Colossal.OdinSerializer.DataFormat SerializedFormat;
```

- `public System.Byte[] SerializedBytes`  

```csharp
public System.Byte[] SerializedBytes;
```

- `public System.Collections.Generic.List<UnityEngine.Object> ReferencedUnityObjects`  

```csharp
public System.Collections.Generic.List<UnityEngine.Object> ReferencedUnityObjects;
```

- `public System.String SerializedBytesString`  

```csharp
public System.String SerializedBytesString;
```

- `public UnityEngine.Object Prefab`  

```csharp
public UnityEngine.Object Prefab;
```

- `public System.Collections.Generic.List<UnityEngine.Object> PrefabModificationsReferencedUnityObjects`  

```csharp
public System.Collections.Generic.List<UnityEngine.Object> PrefabModificationsReferencedUnityObjects;
```

- `public System.Collections.Generic.List<System.String> PrefabModifications`  

```csharp
public System.Collections.Generic.List<System.String> PrefabModifications;
```

- `public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> SerializationNodes`  

```csharp
public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> SerializationNodes;
```

- `public static const System.String PrefabModificationsReferencedUnityObjectsFieldName`  

```csharp
public static const System.String PrefabModificationsReferencedUnityObjectsFieldName;
```

- `public static const System.String PrefabModificationsFieldName`  

```csharp
public static const System.String PrefabModificationsFieldName;
```

- `public static const System.String PrefabFieldName`  

```csharp
public static const System.String PrefabFieldName;
```


## Properties

- `public System.Boolean HasEditorData { get }`  

```csharp
public System.Boolean HasEditorData { get; }
```

- `public System.Boolean ContainsData { get }`  

```csharp
public System.Boolean ContainsData { get; }
```


## Methods

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


