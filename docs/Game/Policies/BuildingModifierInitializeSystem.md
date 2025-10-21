# Game.Policies.BuildingModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
    private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle;

    public BuildingModifierInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
```

- `private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingModifierInitializeSystem()`  

```csharp
public BuildingModifierInitializeSystem();
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

- `Game.Policies.BuildingModifierInitializeSystem+InitializeBuildingModifiersJob`  
- `Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData`  
- `Game.Policies.BuildingModifierInitializeSystem+TypeHandle`  

