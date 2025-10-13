# Game.UI.UIUpdateState

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class UIUpdateState
{
    private readonly Game.Simulation.SimulationSystem m_SimulationSystem;
    private readonly System.UInt32 m_UpdateInterval;
    private System.Boolean m_ForceUpdate;
    private System.UInt32 m_LastTickIndex;

    private UIUpdateState(Unity.Entities.World world, System.Int32 updateInterval);

    public System.Boolean Advance();
    public static Game.UI.UIUpdateState Create(Unity.Entities.World world, System.Int32 updateInterval);
    public System.Void ForceUpdate();
}
```


## Fields

- `private readonly Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private readonly Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private readonly System.UInt32 m_UpdateInterval`  

```csharp
private readonly System.UInt32 m_UpdateInterval;
```

- `private System.Boolean m_ForceUpdate`  

```csharp
private System.Boolean m_ForceUpdate;
```

- `private System.UInt32 m_LastTickIndex`  

```csharp
private System.UInt32 m_LastTickIndex;
```


## Constructors

- `private UIUpdateState(Unity.Entities.World world, System.Int32 updateInterval)`  

```csharp
private UIUpdateState(Unity.Entities.World world, System.Int32 updateInterval);
```


## Methods

- `public Advance() : System.Boolean`  

```csharp
public System.Boolean Advance();
```

- `public static Create(Unity.Entities.World world, System.Int32 updateInterval) : Game.UI.UIUpdateState`  

```csharp
public static Game.UI.UIUpdateState Create(Unity.Entities.World world, System.Int32 updateInterval);
```

- `public ForceUpdate() : System.Void`  

```csharp
public System.Void ForceUpdate();
```


