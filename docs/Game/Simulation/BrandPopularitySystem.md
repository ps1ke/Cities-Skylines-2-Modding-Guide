# Game.Simulation.BrandPopularitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BrandPopularitySystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity;
    private Unity.Jobs.JobHandle m_Readers;
    private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdatesPerDay;

    public BrandPopularitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> ReadBrandPopularity(Unity.Jobs.JobHandle& dependency);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity;
```

- `private Unity.Jobs.JobHandle m_Readers`  

```csharp
private Unity.Jobs.JobHandle m_Readers;
```

- `private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BrandPopularitySystem()`  

```csharp
public BrandPopularitySystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public ReadBrandPopularity(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity>`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> ReadBrandPopularity(Unity.Jobs.JobHandle& dependency);
```


## Nested types

- `Game.Simulation.BrandPopularitySystem+BrandPopularity`  
- `Game.Simulation.BrandPopularitySystem+UpdateBrandPopularityJob`  
- `Game.Simulation.BrandPopularitySystem+TypeHandle`  

