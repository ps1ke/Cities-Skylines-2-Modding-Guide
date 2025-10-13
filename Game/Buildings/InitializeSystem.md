# Game.Buildings.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Simulation.ElectricityRoadConnectionGraphSystem m_ElectricityRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Unity.Entities.EntityQuery m_CoverageQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
    private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

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

- `private Unity.Entities.EntityQuery m_CoverageQuery`  

```csharp
private Unity.Entities.EntityQuery m_CoverageQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents`  

```csharp
private Unity.Entities.ComponentTypeSet m_DestroyedBuildingComponents;
```

- `private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
public InitializeSystem();
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

- `Game.Buildings.InitializeSystem+InitializeCoverageTypeJob`  
- `Game.Buildings.InitializeSystem+InitializeBuildingsJob`  
- `Game.Buildings.InitializeSystem+TypeHandle`  

