# Game.Prefabs.NetData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NetData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.EntityArchetype m_NodeArchetype;
    public Unity.Entities.EntityArchetype m_EdgeArchetype;
    public Game.Net.Layer m_RequiredLayers;
    public Game.Net.Layer m_ConnectLayers;
    public Game.Net.Layer m_LocalConnectLayers;
    public Game.Prefabs.CompositionFlags+General m_GeneralFlagMask;
    public Game.Prefabs.CompositionFlags+Side m_SideFlagMask;
    public System.Single m_NodePriority;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.EntityArchetype m_NodeArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_NodeArchetype;
```

- `public Unity.Entities.EntityArchetype m_EdgeArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_EdgeArchetype;
```

- `public Game.Net.Layer m_RequiredLayers`  

```csharp
public Game.Net.Layer m_RequiredLayers;
```

- `public Game.Net.Layer m_ConnectLayers`  

```csharp
public Game.Net.Layer m_ConnectLayers;
```

- `public Game.Net.Layer m_LocalConnectLayers`  

```csharp
public Game.Net.Layer m_LocalConnectLayers;
```

- `public Game.Prefabs.CompositionFlags+General m_GeneralFlagMask`  

```csharp
public Game.Prefabs.CompositionFlags+General m_GeneralFlagMask;
```

- `public Game.Prefabs.CompositionFlags+Side m_SideFlagMask`  

```csharp
public Game.Prefabs.CompositionFlags+Side m_SideFlagMask;
```

- `public System.Single m_NodePriority`  

```csharp
public System.Single m_NodePriority;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


