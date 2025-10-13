# Game.Buildings.BuildingPoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingPoliciesSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_PolicyModifyQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle;

    public BuildingPoliciesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_PolicyModifyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyModifyQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingPoliciesSystem()`  

```csharp
public BuildingPoliciesSystem();
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

- `Game.Buildings.BuildingPoliciesSystem+CheckBuildingsJob`  
- `Game.Buildings.BuildingPoliciesSystem+TypeHandle`  

