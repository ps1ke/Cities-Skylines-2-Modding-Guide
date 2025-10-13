# Game.Net.LaneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.LaneReferencesSystem m_LaneReferencesSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnerQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
    private Unity.Entities.ComponentTypeSet m_TempOwnerTypes;
    private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
    private Game.Net.LaneSystem+TypeHandle __TypeHandle;

    public LaneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Net.LaneReferencesSystem m_LaneReferencesSystem`  

```csharp
private Game.Net.LaneReferencesSystem m_LaneReferencesSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnerQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_DeletedTempTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_DeletedTempTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempOwnerTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempOwnerTypes;
```

- `private Unity.Entities.ComponentTypeSet m_HideLaneTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HideLaneTypes;
```

- `private Game.Net.LaneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneSystem()`  

```csharp
public LaneSystem();
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

- `Game.Net.LaneSystem+LaneKey`  
- `Game.Net.LaneSystem+ConnectionKey`  
- `Game.Net.LaneSystem+ConnectPosition`  
- `Game.Net.LaneSystem+EdgeTarget`  
- `Game.Net.LaneSystem+MiddleConnection`  
- `Game.Net.LaneSystem+SourcePositionComparer`  
- `Game.Net.LaneSystem+TargetPositionComparer`  
- `Game.Net.LaneSystem+MiddleConnectionComparer`  
- `Game.Net.LaneSystem+LaneAnchor`  
- `Game.Net.LaneSystem+LaneBuffer`  
- `Game.Net.LaneSystem+CompositionData`  
- `Game.Net.LaneSystem+UpdateLanesJob`  
- `Game.Net.LaneSystem+TypeHandle`  

