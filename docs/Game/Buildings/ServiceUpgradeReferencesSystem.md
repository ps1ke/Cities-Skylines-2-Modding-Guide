# Game.Buildings.ServiceUpgradeReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceUpgradeReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpgradeQuery;
    private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle;

    public ServiceUpgradeReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpgradeQuery;
```

- `private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceUpgradeReferencesSystem()`  

```csharp
public ServiceUpgradeReferencesSystem();
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

- `Game.Buildings.ServiceUpgradeReferencesSystem+UpdateUpgradeReferencesJob`  
- `Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle`  

