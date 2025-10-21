# Game.UI.InGame.DevTreeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DevTreeUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.City.DevTreeSystem m_DevTreeSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_DevTreePointsQuery;
    private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
    private Unity.Entities.EntityQuery m_UnlockedServiceQuery;
    private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery;
    private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding;
    private Colossal.UI.Binding.RawValueBinding m_ServicesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding;
    private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    public DevTreeUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node);
    private System.Void BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
    private System.Void BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
    private System.Void BindServices(Colossal.UI.Binding.IJsonWriter writer);
    private System.String GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab);
    private Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo> GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator);
    private System.Int32 GetDevTreePoints();
    private System.Int32 GetMaxDevTreePoints();
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedDevTreeServices(Unity.Collections.Allocator allocator);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void PurchaseNode(Unity.Entities.Entity node);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.City.DevTreeSystem m_DevTreeSystem`  

```csharp
private Game.City.DevTreeSystem m_DevTreeSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreePointsQuery;
```

- `private Unity.Entities.EntityQuery m_DevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedServiceQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery;
```

- `private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ServicesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ServicesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding;
```

- `private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public DevTreeUISystem()`  

```csharp
public DevTreeUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node) : System.Void`  

```csharp
private System.Void BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node);
```

- `private BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  

```csharp
private System.Void BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
```

- `private BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  

```csharp
private System.Void BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service);
```

- `private BindServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindServices(Colossal.UI.Binding.IJsonWriter writer);
```

- `private GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab) : System.String`  

```csharp
private System.String GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab);
```

- `private GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo> GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator);
```

- `private GetDevTreePoints() : System.Int32`  

```csharp
private System.Int32 GetDevTreePoints();
```

- `private GetMaxDevTreePoints() : System.Int32`  

```csharp
private System.Int32 GetMaxDevTreePoints();
```

- `private GetSortedDevTreeServices(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedDevTreeServices(Unity.Collections.Allocator allocator);
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

- `private PurchaseNode(Unity.Entities.Entity node) : System.Void`  

```csharp
private System.Void PurchaseNode(Unity.Entities.Entity node);
```


## Nested types

- `Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo`  
- `Game.UI.InGame.DevTreeUISystem+TypeHandle`  

