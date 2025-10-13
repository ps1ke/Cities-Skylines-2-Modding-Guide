# Game.Simulation.PopulationToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.PopulationCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PopulationToGridSystem : Game.Simulation.CellMapSystem<Game.Simulation.PopulationCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
    private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public PopulationToGridSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.PopulationCell GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
```

- `private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public PopulationToGridSystem()`  

```csharp
public PopulationToGridSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap) : Game.Simulation.PopulationCell`  

```csharp
public static Game.Simulation.PopulationCell GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.PopulationToGridSystem+PopulationToGridJob`  
- `Game.Simulation.PopulationToGridSystem+TypeHandle`  

