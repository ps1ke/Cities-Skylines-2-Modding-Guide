# Game.SafeCommandBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Unity.Entities.EntityCommandBufferSystem`  

## Code

```csharp
public class SafeCommandBufferSystem : Unity.Entities.EntityCommandBufferSystem
{
    private System.Boolean m_IsAllowed;

    public SafeCommandBufferSystem();

    public System.Void AllowUsage();
    public Unity.Entities.EntityCommandBuffer CreateCommandBuffer();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean m_IsAllowed`  

```csharp
private System.Boolean m_IsAllowed;
```


## Constructors

- `public SafeCommandBufferSystem()`  

```csharp
[Preserve]
	public SafeCommandBufferSystem()
	{
	}
```


## Methods

- `public AllowUsage() : System.Void`  

```csharp
public void AllowUsage()
	{
		m_IsAllowed = true;
	}
```

- `public CreateCommandBuffer() : Unity.Entities.EntityCommandBuffer`  

```csharp
public new EntityCommandBuffer CreateCommandBuffer()
	{
		if (m_IsAllowed)
		{
			return base.CreateCommandBuffer();
		}
		throw new Exception("Trying to create EntityCommandBuffer when it's not allowed!");
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_IsAllowed = false;
		base.OnUpdate();
	}
```


