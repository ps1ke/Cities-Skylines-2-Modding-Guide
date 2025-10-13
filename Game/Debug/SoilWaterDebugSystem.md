# Game.Debug.SoilWaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class SoilWaterDebugSystem : Game.GameSystemBase
{
    private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
    private Colossal.GizmosSystem m_GizmosSystem;

    public SoilWaterDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SoilWaterSystem m_SoilWaterSystem`  

```csharp
private Game.Simulation.SoilWaterSystem m_SoilWaterSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```


## Constructors

- `public SoilWaterDebugSystem()`  

```csharp
public SoilWaterDebugSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.SoilWaterDebugSystem+SoilWaterGizmoJob`  

