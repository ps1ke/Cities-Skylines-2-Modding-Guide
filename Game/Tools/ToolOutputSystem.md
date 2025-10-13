# Game.Tools.ToolOutputSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ToolOutputSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UpdateSystem m_UpdateSystem;

    public ToolOutputSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```


## Constructors

- `public ToolOutputSystem()`  

```csharp
[Preserve]
	public ToolOutputSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		switch (m_ToolSystem.applyMode)
		{
		case ApplyMode.Clear:
			m_UpdateSystem.Update(SystemUpdatePhase.ClearTool);
			break;
		case ApplyMode.Apply:
			m_UpdateSystem.Update(SystemUpdatePhase.ApplyTool);
			break;
		}
	}
```


