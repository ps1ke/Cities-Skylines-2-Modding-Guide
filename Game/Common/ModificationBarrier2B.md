# Game.Common.ModificationBarrier2B

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class ModificationBarrier2B : Game.SafeCommandBufferSystem
{
    public ModificationBarrier2B();

    protected virtual System.Void OnUpdate();
}
```


## Constructors

- `public ModificationBarrier2B()`  

```csharp
[Preserve]
	public ModificationBarrier2B()
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


