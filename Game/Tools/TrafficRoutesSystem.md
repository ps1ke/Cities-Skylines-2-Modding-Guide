# Game.Tools.TrafficRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficRoutesSystem : Game.GameSystemBase
{
    private System.Boolean <routesVisible>k__BackingField;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_LivePathQuery;
    private Unity.Entities.EntityQuery m_PathSourceQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Int32 m_UpdateFrameIndex;
    private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle;

    public System.Boolean routesVisible { get; set; }

    public TrafficRoutesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <routesVisible>k__BackingField`  

```csharp
private System.Boolean <routesVisible>k__BackingField;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_LivePathQuery`  

```csharp
private Unity.Entities.EntityQuery m_LivePathQuery;
```

- `private Unity.Entities.EntityQuery m_PathSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathSourceQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Int32 m_UpdateFrameIndex`  

```csharp
private System.Int32 m_UpdateFrameIndex;
```

- `private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TrafficRoutesSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean routesVisible { get; set }`  

```csharp
public System.Boolean routesVisible { get; set; }
```


## Constructors

- `public TrafficRoutesSystem()`  

```csharp
public TrafficRoutesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.TrafficRoutesSystem+LivePathEntityData`  
- `Game.Tools.TrafficRoutesSystem+FillTargetMapJob`  
- `Game.Tools.TrafficRoutesSystem+FindPathSourcesJob`  
- `Game.Tools.TrafficRoutesSystem+UpdateLivePathsJob`  
- `Game.Tools.TrafficRoutesSystem+TypeHandle`  

