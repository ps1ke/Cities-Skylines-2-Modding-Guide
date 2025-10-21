# Game.Objects.SubObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubObjectSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_ContainerQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LoopErrorPrefabs;
    private Game.Objects.SubObjectSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kMaxSubObjectDepth;

    public SubObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ShowLoopErrors();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_ContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContainerQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LoopErrorPrefabs`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_LoopErrorPrefabs;
```

- `private Game.Objects.SubObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SubObjectSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kMaxSubObjectDepth`  

```csharp
private static const System.Int32 kMaxSubObjectDepth;
```


## Constructors

- `public SubObjectSystem()`  

```csharp
public SubObjectSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ShowLoopErrors() : System.Void`  

```csharp
private System.Void ShowLoopErrors();
```


## Nested types

- `Game.Objects.SubObjectSystem+SubObjectOwnerData`  
- `Game.Objects.SubObjectSystem+SubObjectData`  
- `Game.Objects.SubObjectSystem+DeepSubObjectOwnerData`  
- `Game.Objects.SubObjectSystem+PlaceholderKey`  
- `Game.Objects.SubObjectSystem+UpdateSubObjectsData`  
- `Game.Objects.SubObjectSystem+CheckSubObjectOwnersJob`  
- `Game.Objects.SubObjectSystem+CollectSubObjectOwnersJob`  
- `Game.Objects.SubObjectSystem+FillIgnoreSetJob`  
- `Game.Objects.SubObjectSystem+UpdateSubObjectsJob`  
- `Game.Objects.SubObjectSystem+TypeHandle`  

