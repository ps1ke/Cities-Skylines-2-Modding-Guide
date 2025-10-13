# Game.Tools.GenerateObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateObjectsSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.ComponentTypeSet m_SubTypes;
    private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes;
    private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap;
    private Unity.Jobs.JobHandle m_OwnerMapReadDeps;
    private Unity.Jobs.JobHandle m_OwnerMapWriteDeps;
    private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle;

    public GenerateObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddOwnerMapReader(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.ComponentTypeSet m_SubTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SubTypes;
```

- `private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes;
```

- `private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap`  

```csharp
private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap;
```

- `private Unity.Jobs.JobHandle m_OwnerMapReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_OwnerMapReadDeps;
```

- `private Unity.Jobs.JobHandle m_OwnerMapWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_OwnerMapWriteDeps;
```

- `private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateObjectsSystem()`  

```csharp
public GenerateObjectsSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddOwnerMapReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddOwnerMapReader(Unity.Jobs.JobHandle dependencies);
```

- `public GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity>`  

```csharp
public Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.GenerateObjectsSystem+CreationData`  
- `Game.Tools.GenerateObjectsSystem+OldObjectKey`  
- `Game.Tools.GenerateObjectsSystem+OldObjectValue`  
- `Game.Tools.GenerateObjectsSystem+FillOldObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+FillCreationListJob`  
- `Game.Tools.GenerateObjectsSystem+CollectCreationDataJob`  
- `Game.Tools.GenerateObjectsSystem+CreateObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+TypeHandle`  

