# Game.Simulation.WatercraftNavigationHelpers+LaneEffects

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneEffects
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float3 m_SideEffects;
    public System.Single m_RelativeSpeed;

    public LaneEffects(Unity.Entities.Entity lane, Unity.Mathematics.float3 sideEffects, System.Single relativeSpeed);

}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float3 m_SideEffects`  

```csharp
public Unity.Mathematics.float3 m_SideEffects;
```

- `public System.Single m_RelativeSpeed`  

```csharp
public System.Single m_RelativeSpeed;
```


## Constructors

- `public LaneEffects(Unity.Entities.Entity lane, Unity.Mathematics.float3 sideEffects, System.Single relativeSpeed)`  

```csharp
public LaneEffects(Unity.Entities.Entity lane, Unity.Mathematics.float3 sideEffects, System.Single relativeSpeed);
```


