# Game.Tools.NetToolSystem+FixControlPointsJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct FixControlPointsJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks;
    public Game.Tools.NetToolSystem+Mode m_Mode;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;

    public System.Void Execute();
    private System.Void FixControlPoints(Unity.Entities.Entity entity, Unity.Entities.Entity replace);
    private System.Void InverseCurvePositions(Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks;
```

- `public Game.Tools.NetToolSystem+Mode m_Mode`  

```csharp
public Game.Tools.NetToolSystem+Mode m_Mode;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
public Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```

- `private FixControlPoints(Unity.Entities.Entity entity, Unity.Entities.Entity replace) : System.Void`  

```csharp
private System.Void FixControlPoints(Unity.Entities.Entity entity, Unity.Entities.Entity replace);
```

- `private InverseCurvePositions(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void InverseCurvePositions(Unity.Entities.Entity entity);
```


