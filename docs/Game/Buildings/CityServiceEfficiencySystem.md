# Game.Buildings.CityServiceEfficiencySystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceEfficiencySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedBudgetQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_ChangedBuildingQuery;
    private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_339138653_0;
    private Unity.Entities.EntityQuery __query_339138653_1;

    public CityServiceEfficiencySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBudgetQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ChangedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChangedBuildingQuery;
```

- `private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_339138653_0`  

```csharp
private Unity.Entities.EntityQuery __query_339138653_0;
```

- `private Unity.Entities.EntityQuery __query_339138653_1`  

```csharp
private Unity.Entities.EntityQuery __query_339138653_1;
```


## Constructors

- `public CityServiceEfficiencySystem()`  

```csharp
public CityServiceEfficiencySystem();
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

- `Game.Buildings.CityServiceEfficiencySystem+BuildingStateEfficiencyJob`  
- `Game.Buildings.CityServiceEfficiencySystem+TypeHandle`  

