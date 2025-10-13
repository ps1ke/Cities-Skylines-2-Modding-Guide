# Game.Simulation.TreeGrowthSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TreeGrowthSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_TreeQuery;
    private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle;
    public static const System.Int32 UPDATES_PER_DAY;
    public static const System.Int32 TICK_SPEED_CHILD;
    public static const System.Int32 TICK_SPEED_TEEN;
    public static const System.Int32 TICK_SPEED_ADULT;
    public static const System.Int32 TICK_SPEED_ELDERLY;
    public static const System.Int32 TICK_SPEED_DEAD;

    public TreeGrowthSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_TreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeQuery;
```

- `private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TreeGrowthSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```

- `public static const System.Int32 TICK_SPEED_CHILD`  

```csharp
public static const System.Int32 TICK_SPEED_CHILD;
```

- `public static const System.Int32 TICK_SPEED_TEEN`  

```csharp
public static const System.Int32 TICK_SPEED_TEEN;
```

- `public static const System.Int32 TICK_SPEED_ADULT`  

```csharp
public static const System.Int32 TICK_SPEED_ADULT;
```

- `public static const System.Int32 TICK_SPEED_ELDERLY`  

```csharp
public static const System.Int32 TICK_SPEED_ELDERLY;
```

- `public static const System.Int32 TICK_SPEED_DEAD`  

```csharp
public static const System.Int32 TICK_SPEED_DEAD;
```


## Constructors

- `public TreeGrowthSystem()`  

```csharp
public TreeGrowthSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.TreeGrowthSystem+TreeGrowthJob`  
- `Game.Simulation.TreeGrowthSystem+TypeHandle`  

