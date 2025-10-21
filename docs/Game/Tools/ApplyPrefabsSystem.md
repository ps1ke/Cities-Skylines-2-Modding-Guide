# Game.Tools.ApplyPrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyPrefabsSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_SaveInstanceQuery;

    public ApplyPrefabsSystem();

    public static T AddComponent<T>(Game.Prefabs.PrefabBase asset);
    private static System.Void CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached);
    private static System.Void CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached);
    private Game.Prefabs.NetPieceRequirements[] CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags);
    private Game.Prefabs.NetPieceRequirements[] CreateRequirementMap();
    private System.Int32 GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary);
    private System.Int32 GetParentMesh(Unity.Entities.Entity node);
    private System.Boolean HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity);
    private System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo> ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public static System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase asset);
    public static System.Void RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType);
    private System.Void UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_SaveInstanceQuery`  

```csharp
private Unity.Entities.EntityQuery m_SaveInstanceQuery;
```


## Constructors

- `public ApplyPrefabsSystem()`  

```csharp
public ApplyPrefabsSystem();
```


## Methods

- `public static AddComponent<T>(Game.Prefabs.PrefabBase asset) : T`  

```csharp
public static T AddComponent<T>(Game.Prefabs.PrefabBase asset);
```

- `private static CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached) : System.Void`  

```csharp
private static System.Void CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached);
```

- `private static CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached) : System.Void`  

```csharp
private static System.Void CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached);
```

- `private CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags) : Game.Prefabs.NetPieceRequirements[]`  

```csharp
private Game.Prefabs.NetPieceRequirements[] CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags);
```

- `private CreateRequirementMap() : Game.Prefabs.NetPieceRequirements[]`  

```csharp
private Game.Prefabs.NetPieceRequirements[] CreateRequirementMap();
```

- `private GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary) : System.Int32`  

```csharp
private System.Int32 GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary);
```

- `private GetParentMesh(Unity.Entities.Entity node) : System.Int32`  

```csharp
private System.Int32 GetParentMesh(Unity.Entities.Entity node);
```

- `private HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity) : System.Boolean`  

```csharp
private System.Boolean HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity);
```

- `private ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo>`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo> ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```

- `private ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private System.Void ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```

- `private ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private System.Void ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static RemoveComponent<T>(Game.Prefabs.PrefabBase asset) : System.Void`  

```csharp
public static System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase asset);
```

- `public static RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType) : System.Void`  

```csharp
public static System.Void RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType);
```

- `private UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private System.Void UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```

- `private UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private System.Void UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```

- `private UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private System.Void UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
```


