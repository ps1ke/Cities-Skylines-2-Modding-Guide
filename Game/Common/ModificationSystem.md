# Game.Common.ModificationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ModificationSystem : Game.GameSystemBase
{
    private Game.UpdateSystem m_UpdateSystem;

    public ModificationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```


## Constructors

- `public ModificationSystem()`  

```csharp
[Preserve]
	public ModificationSystem()
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
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_UpdateSystem.Update(SystemUpdatePhase.Modification1);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification2);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification2B);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification3);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification4);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification4B);
		m_UpdateSystem.Update(SystemUpdatePhase.Modification5);
		m_UpdateSystem.Update(SystemUpdatePhase.ModificationEnd);
	}
```


