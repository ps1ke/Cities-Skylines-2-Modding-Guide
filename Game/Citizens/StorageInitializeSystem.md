# Game.Citizens.StorageInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedStorageGroup;
    private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle;

    public StorageInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedStorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_CreatedStorageGroup;
```

- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.StorageInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StorageInitializeSystem()`  

```csharp
public StorageInitializeSystem();
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

- `Game.Citizens.StorageInitializeSystem+InitializeStorageJob`  
- `Game.Citizens.StorageInitializeSystem+TypeHandle`  

