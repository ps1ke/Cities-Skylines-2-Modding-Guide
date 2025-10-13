# Game.Objects.DestroySystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DestroySystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
    private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
    private Game.Objects.DestroySystem+TypeHandle __TypeHandle;

    public DestroySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingConfigurationQuery;
```

- `private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents`  

```csharp
private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
```

- `private Game.Objects.DestroySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.DestroySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DestroySystem()`  

```csharp
public DestroySystem();
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

- `Game.Objects.DestroySystem+DestroyObjectsJob`  
- `Game.Objects.DestroySystem+TypeHandle`  

