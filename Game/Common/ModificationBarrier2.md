# Game.Common.ModificationBarrier2

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class ModificationBarrier2 : Game.SafeCommandBufferSystem
{
    public ModificationBarrier2();

    protected virtual System.Void OnUpdate();
}
```


## Constructors

- `public ModificationBarrier2()`  

```csharp
[Preserve]
	public ModificationBarrier2()
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


