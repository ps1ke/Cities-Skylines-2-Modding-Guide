# Game.Simulation.CountWorkplacesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountWorkplacesSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_WorkplaceQuery;
    private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces;
    private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces;
    public Game.Companies.Workplaces m_LastFreeWorkplaces;
    public Game.Companies.Workplaces m_LastTotalWorkplaces;
    private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle;

    public CountWorkplacesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Companies.Workplaces GetFreeWorkplaces();
    public Game.Companies.Workplaces GetTotalWorkplaces();
    public Game.Companies.Workplaces GetUnemployedWorkspaceByLevel();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceQuery;
```

- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces;
```

- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces;
```

- `public Game.Companies.Workplaces m_LastFreeWorkplaces`  

```csharp
public Game.Companies.Workplaces m_LastFreeWorkplaces;
```

- `public Game.Companies.Workplaces m_LastTotalWorkplaces`  

```csharp
public Game.Companies.Workplaces m_LastTotalWorkplaces;
```

- `private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CountWorkplacesSystem()`  

```csharp
public CountWorkplacesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetFreeWorkplaces() : Game.Companies.Workplaces`  

```csharp
public Game.Companies.Workplaces GetFreeWorkplaces();
```

- `public GetTotalWorkplaces() : Game.Companies.Workplaces`  

```csharp
public Game.Companies.Workplaces GetTotalWorkplaces();
```

- `public GetUnemployedWorkspaceByLevel() : Game.Companies.Workplaces`  

```csharp
public Game.Companies.Workplaces GetUnemployedWorkspaceByLevel();
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

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.CountWorkplacesSystem+CountWorkplacesJob`  
- `Game.Simulation.CountWorkplacesSystem+TypeHandle`  

