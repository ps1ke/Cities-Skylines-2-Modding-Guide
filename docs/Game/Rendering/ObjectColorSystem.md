# Game.Rendering.ObjectColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectColorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_MiddleObjectQuery;
    private Unity.Entities.EntityQuery m_TempObjectQuery;
    private Unity.Entities.EntityQuery m_SubObjectQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.FireHazardSystem m_FireHazardSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle;

    public ObjectColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_MiddleObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_MiddleObjectQuery;
```

- `private Unity.Entities.EntityQuery m_TempObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempObjectQuery;
```

- `private Unity.Entities.EntityQuery m_SubObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubObjectQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  

```csharp
private Game.Simulation.FireHazardSystem m_FireHazardSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ObjectColorSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectColorSystem()`  

```csharp
public ObjectColorSystem();
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

- `Game.Rendering.ObjectColorSystem+UpdateObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateMiddleObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateTempObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+UpdateSubObjectColorsJob`  
- `Game.Rendering.ObjectColorSystem+TypeHandle`  

