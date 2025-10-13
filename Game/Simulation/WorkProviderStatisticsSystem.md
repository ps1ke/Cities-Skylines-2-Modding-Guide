# Game.Simulation.WorkProviderStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkProviderStatisticsSystem : Game.GameSystemBase
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_WorkProviderQuery;
    private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1149970541_0;
    private Unity.Entities.EntityQuery __query_1149970541_1;

    public WorkProviderStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_WorkProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkProviderQuery;
```

- `private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1149970541_0`  

```csharp
private Unity.Entities.EntityQuery __query_1149970541_0;
```

- `private Unity.Entities.EntityQuery __query_1149970541_1`  

```csharp
private Unity.Entities.EntityQuery __query_1149970541_1;
```


## Constructors

- `public WorkProviderStatisticsSystem()`  

```csharp
public WorkProviderStatisticsSystem();
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

- `Game.Simulation.WorkProviderStatisticsSystem+CountSeniorWorkplacesJob`  
- `Game.Simulation.WorkProviderStatisticsSystem+StatisticsJob`  
- `Game.Simulation.WorkProviderStatisticsSystem+TypeHandle`  

