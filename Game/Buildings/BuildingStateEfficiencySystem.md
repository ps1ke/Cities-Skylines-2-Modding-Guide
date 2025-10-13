# Game.Buildings.BuildingStateEfficiencySystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingStateEfficiencySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Buildings.BuildingStateEfficiencySystem+TypeHandle __TypeHandle;

    public BuildingStateEfficiencySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Buildings.BuildingStateEfficiencySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.BuildingStateEfficiencySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingStateEfficiencySystem()`  

```csharp
public BuildingStateEfficiencySystem();
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

- `Game.Buildings.BuildingStateEfficiencySystem+BuildingStateEfficiencyJob`  
- `Game.Buildings.BuildingStateEfficiencySystem+TypeHandle`  

