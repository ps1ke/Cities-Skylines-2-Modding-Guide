# Game.UI.InGame.CameraUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class CameraUISystem : Game.UI.UISystemBase
{
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding;
    private static const System.String kGroup;

    public CameraUISystem();

    private System.Void FocusEntity(Unity.Entities.Entity entity);
    private Unity.Entities.Entity GetFocusedEntity();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_FocusedEntityBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public CameraUISystem()`  

```csharp
[Preserve]
	public CameraUISystem()
	{
	}
```


## Methods

- `private FocusEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void FocusEntity(Entity entity)
	{
		if (entity != Entity.Null && m_CameraUpdateSystem.orbitCameraController != null && entity != m_CameraUpdateSystem.orbitCameraController.followedEntity)
		{
			m_CameraUpdateSystem.orbitCameraController.followedEntity = entity;
			m_CameraUpdateSystem.orbitCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.orbitCameraController;
		}
		if (entity == Entity.Null && m_CameraUpdateSystem.activeCameraController == m_CameraUpdateSystem.orbitCameraController)
		{
			m_CameraUpdateSystem.gamePlayController.TryMatchPosition(m_CameraUpdateSystem.orbitCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.gamePlayController;
		}
	}
```

- `private GetFocusedEntity() : Unity.Entities.Entity`  

```csharp
private Entity GetFocusedEntity()
	{
		if (!(m_CameraUpdateSystem.orbitCameraController != null))
		{
			return Entity.Null;
		}
		return m_CameraUpdateSystem.orbitCameraController.followedEntity;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(m_FocusedEntityBinding = new GetterValueBinding<Entity>("camera", "focusedEntity", GetFocusedEntity));
		AddBinding(new TriggerBinding<Entity>("camera", "focusEntity", FocusEntity));
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_FocusedEntityBinding.Update();
	}
```


