# Game.UI.InGame.DevTreeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.City.DevTreeSystem m_DevTreeSystem`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Unity.Entities.EntityQuery m_DevTreePointsQuery`  
- `private Unity.Entities.EntityQuery m_DevTreeNodeQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedServiceQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedDevTreeNodeQuery`  
- `private Unity.Entities.EntityQuery m_LockedDevTreeNodeQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PointsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ServicesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_ServiceDetailsBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_NodeDetailsBinding`  
- `private Game.UI.InGame.DevTreeUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Constructors

- `public DevTreeUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private BindNodeDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity node) : System.Void`  
- `private BindNodes(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  
- `private BindServiceDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity service) : System.Void`  
- `private BindServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private GetDevTreeIcon(Game.Prefabs.DevTreeNodePrefab prefab) : System.String`  
- `private GetDevTreeNodes(Unity.Entities.Entity service, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo>`  
- `private GetDevTreePoints() : System.Int32`  
- `private GetMaxDevTreePoints() : System.Int32`  
- `private GetSortedDevTreeServices(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PurchaseNode(Unity.Entities.Entity node) : System.Void`  

## Nested types

- `Game.UI.InGame.DevTreeUISystem+DevTreeNodeInfo`  
- `Game.UI.InGame.DevTreeUISystem+TypeHandle`  

