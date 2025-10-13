# Game.Common.ModificationEndBarrier

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class ModificationEndBarrier : Game.SafeCommandBufferSystem
{
    public ModificationEndBarrier();

    protected virtual System.Void OnUpdate();
}
```


## Constructors

- `public ModificationEndBarrier()`  

```csharp
[Preserve]
	public ModificationEndBarrier()
	{
	}
```


## Methods

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
	}
```


