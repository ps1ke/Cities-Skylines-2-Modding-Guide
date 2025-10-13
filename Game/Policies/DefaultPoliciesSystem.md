# Game.Policies.DefaultPoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DefaultPoliciesSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_CityConfigurationQuery;
    private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle;

    public DefaultPoliciesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_CityConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityConfigurationQuery;
```

- `private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DefaultPoliciesSystem()`  

```csharp
public DefaultPoliciesSystem();
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Policies.DefaultPoliciesSystem+AddDefaultPoliciesJob`  
- `Game.Policies.DefaultPoliciesSystem+TypeHandle`  

