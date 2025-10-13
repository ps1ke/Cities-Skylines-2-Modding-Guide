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
private UIUpdateState(World world, int updateInterval)
	{
		m_SimulationSystem = world.GetOrCreateSystemManaged<SimulationSystem>();
		m_UpdateInterval = (uint)updateInterval;
		m_ForceUpdate = true;
	}
```


## Methods

- `public Advance() : System.Boolean`  

```csharp
public bool Advance()
	{
		uint num = m_SimulationSystem.frameIndex - m_LastTickIndex;
		if (m_ForceUpdate || num >= m_UpdateInterval)
		{
			m_LastTickIndex = m_SimulationSystem.frameIndex;
			m_ForceUpdate = false;
			return true;
		}
		return false;
	}
```

- `public static Create(Unity.Entities.World world, System.Int32 updateInterval) : Game.UI.UIUpdateState`  

```csharp
public static UIUpdateState Create(World world, int updateInterval)
	{
		return new UIUpdateState(world, updateInterval);
	}
```

- `public ForceUpdate() : System.Void`  

```csharp
public void ForceUpdate()
	{
		m_ForceUpdate = true;
	}
```


