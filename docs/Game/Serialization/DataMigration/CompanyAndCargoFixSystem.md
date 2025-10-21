# Game.Serialization.DataMigration.CompanyAndCargoFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyAndCargoFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery;
    private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle;

    public CompanyAndCargoFixSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery;
```

- `private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompanyAndCargoFixSystem()`  

```csharp
public CompanyAndCargoFixSystem();
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

- `Game.Serialization.DataMigration.CompanyAndCargoFixSystem+ProfitabilityFixJob`  
- `Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle`  

