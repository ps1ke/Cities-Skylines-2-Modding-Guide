# Game.Routes.RaycastJobs+FindRoutesFromTreeJob

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct FindRoutesFromTreeJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
    public Unity.Collections.NativeList<Game.Routes.RaycastJobs+RouteItem> m_RouteList;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  

```csharp
public Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree;
```

- `public Unity.Collections.NativeList<Game.Routes.RaycastJobs+RouteItem> m_RouteList`  

```csharp
public Unity.Collections.NativeList<Game.Routes.RaycastJobs+RouteItem> m_RouteList;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


## Nested types

- `Game.Routes.RaycastJobs+FindRoutesFromTreeJob+FindRoutesIterator`  

