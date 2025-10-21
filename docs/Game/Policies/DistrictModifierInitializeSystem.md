# Game.Policies.DistrictModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DistrictModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
    private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle;

    public DistrictModifierInitializeSystem();

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

- `private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
```

- `private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DistrictModifierInitializeSystem()`  

```csharp
public DistrictModifierInitializeSystem();
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

- `Game.Policies.DistrictModifierInitializeSystem+InitializeDistrictModifiersJob`  
- `Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData`  
- `Game.Policies.DistrictModifierInitializeSystem+TypeHandle`  

