# Game.Simulation.WatercraftNavigationHelpers+LaneSignal

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LaneSignal
{
    public Unity.Entities.Entity m_Petitioner;
    public Unity.Entities.Entity m_Lane;
    public System.SByte m_Priority;

    public LaneSignal(Unity.Entities.Entity petitioner, Unity.Entities.Entity lane, System.Int32 priority);

}
```


## Fields

- `public Unity.Entities.Entity m_Petitioner`  

```csharp
public Unity.Entities.Entity m_Petitioner;
```

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public System.SByte m_Priority`  

```csharp
public System.SByte m_Priority;
```


## Constructors

- `public LaneSignal(Unity.Entities.Entity petitioner, Unity.Entities.Entity lane, System.Int32 priority)`  

```csharp
public LaneSignal(Unity.Entities.Entity petitioner, Unity.Entities.Entity lane, System.Int32 priority);
```


