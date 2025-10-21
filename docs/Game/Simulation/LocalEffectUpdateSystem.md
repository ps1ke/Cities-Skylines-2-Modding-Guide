# Game.Simulation.LocalEffectUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalEffectUpdateSystem : Game.GameSystemBase
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle;

    public LocalEffectUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LocalEffectUpdateSystem()`  

```csharp
public LocalEffectUpdateSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.LocalEffectUpdateSystem+UpdateLocalEffectsJob`  
- `Game.Simulation.LocalEffectUpdateSystem+TypeHandle`  

