# Game.Simulation.ElectricityGraphReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityGraphReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Game.Simulation.ElectricityGraphReferencesSystem+TypeHandle __TypeHandle;

    public ElectricityGraphReferencesSystem();

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

- `private Game.Simulation.ElectricityGraphReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityGraphReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ElectricityGraphReferencesSystem()`  

```csharp
public ElectricityGraphReferencesSystem();
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

- `Game.Simulation.ElectricityGraphReferencesSystem+UpdateGraphReferencesJob`  
- `Game.Simulation.ElectricityGraphReferencesSystem+TypeHandle`  

