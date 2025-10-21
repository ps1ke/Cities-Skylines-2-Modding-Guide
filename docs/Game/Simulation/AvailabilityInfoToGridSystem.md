# Game.Simulation.AvailabilityInfoToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.AvailabilityInfoCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvailabilityInfoToGridSystem : Game.Simulation.CellMapSystem<Game.Simulation.AvailabilityInfoCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public AvailabilityInfoToGridSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Game.Simulation.AvailabilityInfoCell GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle;
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

- `public AvailabilityInfoToGridSystem()`  

```csharp
public AvailabilityInfoToGridSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap) : Game.Simulation.AvailabilityInfoCell`  

```csharp
public static Game.Simulation.AvailabilityInfoCell GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
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

- `Game.Simulation.AvailabilityInfoToGridSystem+NetIterator`  
- `Game.Simulation.AvailabilityInfoToGridSystem+AvailabilityInfoToGridJob`  
- `Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle`  

