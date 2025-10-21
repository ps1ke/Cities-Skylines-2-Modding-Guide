# Game.Tools.ValidationSystem+ChunkType

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ChunkType
{
    public Unity.Entities.EntityTypeHandle m_Entity;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_Temp;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_Owner;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Native> m_Native;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Brush> m_Brush;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRef;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Object> m_Object;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_Transform;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Attached> m_Attached;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.NetObject> m_NetObject;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnection;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_Building;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.ServiceUpgrade> m_ServiceUpgrade;
    public Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStop;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_Edge;
    public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometry;
    public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometry;
    public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometry;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_Composition;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_Lane;
    public Unity.Entities.ComponentTypeHandle<Game.Net.TrackLane> m_TrackLane;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_Curve;
    public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeLane> m_EdgeLane;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Fixed> m_Fixed;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.Area> m_Area;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_AreaGeometry;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.Storage> m_AreaStorage;
    public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_AreaNode;
    public Unity.Entities.BufferTypeHandle<Game.Routes.RouteWaypoint> m_RouteWaypoint;
    public Unity.Entities.BufferTypeHandle<Game.Routes.RouteSegment> m_RouteSegment;
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterSourceData> m_WaterSourceData;

    public ChunkType(Unity.Entities.SystemBase system);

    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_Entity`  

```csharp
public Unity.Entities.EntityTypeHandle m_Entity;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_Temp`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_Temp;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_Owner`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_Owner;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Native> m_Native`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Native> m_Native;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Brush> m_Brush`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Brush> m_Brush;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRef`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRef;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Object> m_Object`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Object> m_Object;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_Transform`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_Transform;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Attached> m_Attached`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Attached> m_Attached;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.NetObject> m_NetObject`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.NetObject> m_NetObject;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnection`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnection;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_Building`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_Building;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.ServiceUpgrade> m_ServiceUpgrade`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.ServiceUpgrade> m_ServiceUpgrade;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStop`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStop;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_Edge`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_Edge;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometry`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeGeometry> m_EdgeGeometry;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometry`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.StartNodeGeometry> m_StartNodeGeometry;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometry`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.EndNodeGeometry> m_EndNodeGeometry;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_Composition`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Composition> m_Composition;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_Lane`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_Lane;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.TrackLane> m_TrackLane`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.TrackLane> m_TrackLane;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_Curve`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Curve> m_Curve;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeLane> m_EdgeLane`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.EdgeLane> m_EdgeLane;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Fixed> m_Fixed`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Fixed> m_Fixed;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Area> m_Area`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.Area> m_Area;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_AreaGeometry`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_AreaGeometry;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Storage> m_AreaStorage`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.Storage> m_AreaStorage;
```

- `public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_AreaNode`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Areas.Node> m_AreaNode;
```

- `public Unity.Entities.BufferTypeHandle<Game.Routes.RouteWaypoint> m_RouteWaypoint`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Routes.RouteWaypoint> m_RouteWaypoint;
```

- `public Unity.Entities.BufferTypeHandle<Game.Routes.RouteSegment> m_RouteSegment`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Routes.RouteSegment> m_RouteSegment;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterSourceData> m_WaterSourceData`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterSourceData> m_WaterSourceData;
```


## Constructors

- `public ChunkType(Unity.Entities.SystemBase system)`  

```csharp
public ChunkType(Unity.Entities.SystemBase system);
```


## Methods

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


