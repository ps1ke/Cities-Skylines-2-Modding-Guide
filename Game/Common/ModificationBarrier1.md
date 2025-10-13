# Game.Common.ModificationBarrier1

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class ModificationBarrier1 : Game.SafeCommandBufferSystem
{
    public ModificationBarrier1();

    protected virtual System.Void OnUpdate();
}
```


## Constructors

- `public ModificationBarrier1()`  

```csharp
[Preserve]
	public ModificationBarrier1()
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


