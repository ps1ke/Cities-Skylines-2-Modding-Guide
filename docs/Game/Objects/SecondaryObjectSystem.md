# Game.Objects.SecondaryObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryObjectSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes;
    private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
    private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle;

    public SecondaryObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
    private System.Void UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
```

- `private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryObjectSystem()`  

```csharp
public SecondaryObjectSystem();
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

- `private UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  

```csharp
private System.Void UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
```

- `private UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  

```csharp
private System.Void UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
```


## Nested types

- `Game.Objects.SecondaryObjectSystem+UpdateData`  
- `Game.Objects.SecondaryObjectSystem+SubObjectOwnerData`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignNeeds`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignData`  
- `Game.Objects.SecondaryObjectSystem+StreetLightData`  
- `Game.Objects.SecondaryObjectSystem+UtilityObjectData`  
- `Game.Objects.SecondaryObjectSystem+UtilityNodeData`  
- `Game.Objects.SecondaryObjectSystem+TargetLaneData`  
- `Game.Objects.SecondaryObjectSystem+PlaceholderKey`  
- `Game.Objects.SecondaryObjectSystem+UpdateSecondaryObjectsData`  
- `Game.Objects.SecondaryObjectSystem+FillUpdateMapJob`  
- `Game.Objects.SecondaryObjectSystem+SecondaryLaneAnchorJob`  
- `Game.Objects.SecondaryObjectSystem+CheckSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+CollectSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+UpdateSubObjectsJob`  
- `Game.Objects.SecondaryObjectSystem+TypeHandle`  

