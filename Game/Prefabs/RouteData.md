# Game.Prefabs.RouteData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct RouteData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.EntityArchetype m_RouteArchetype;
    public Unity.Entities.EntityArchetype m_WaypointArchetype;
    public Unity.Entities.EntityArchetype m_ConnectedArchetype;
    public Unity.Entities.EntityArchetype m_SegmentArchetype;
    public System.Single m_SnapDistance;
    public Game.Routes.RouteType m_Type;
    public UnityEngine.Color32 m_Color;
    public System.Single m_Width;
    public System.Single m_SegmentLength;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.EntityArchetype m_RouteArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_RouteArchetype;
```

- `public Unity.Entities.EntityArchetype m_WaypointArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_WaypointArchetype;
```

- `public Unity.Entities.EntityArchetype m_ConnectedArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_ConnectedArchetype;
```

- `public Unity.Entities.EntityArchetype m_SegmentArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_SegmentArchetype;
```

- `public System.Single m_SnapDistance`  

```csharp
public System.Single m_SnapDistance;
```

- `public Game.Routes.RouteType m_Type`  

```csharp
public Game.Routes.RouteType m_Type;
```

- `public UnityEngine.Color32 m_Color`  

```csharp
public UnityEngine.Color32 m_Color;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public System.Single m_SegmentLength`  

```csharp
public System.Single m_SegmentLength;
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


