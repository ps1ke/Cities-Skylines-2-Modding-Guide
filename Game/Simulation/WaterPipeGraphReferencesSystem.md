# Game.Simulation.WaterPipeGraphReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeGraphReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle;

    public WaterPipeGraphReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeGraphReferencesSystem()`  

```csharp
public WaterPipeGraphReferencesSystem();
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

- `Game.Simulation.WaterPipeGraphReferencesSystem+UpdateGraphReferencesJob`  
- `Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle`  

