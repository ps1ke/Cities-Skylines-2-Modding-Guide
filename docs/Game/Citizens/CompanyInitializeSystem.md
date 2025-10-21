# Game.Citizens.CompanyInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Unity.Entities.EntityQuery m_CreatedGroup;
    private Game.Citizens.CompanyInitializeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1030701297_0;

    public CompanyInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedGroup`  

```csharp
private Unity.Entities.EntityQuery m_CreatedGroup;
```

- `private Game.Citizens.CompanyInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.CompanyInitializeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1030701297_0`  

```csharp
private Unity.Entities.EntityQuery __query_1030701297_0;
```


## Constructors

- `public CompanyInitializeSystem()`  

```csharp
public CompanyInitializeSystem();
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

- `Game.Citizens.CompanyInitializeSystem+InitializeCompanyJob`  
- `Game.Citizens.CompanyInitializeSystem+TypeHandle`  

