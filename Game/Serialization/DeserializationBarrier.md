# Game.Serialization.DeserializationBarrier

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.SafeCommandBufferSystem`  

## Code

```csharp
public class DeserializationBarrier : Game.SafeCommandBufferSystem
{
    public DeserializationBarrier();

    protected virtual System.Void OnUpdate();
}
```


## Constructors

- `public DeserializationBarrier()`  

```csharp
[Preserve]
	public DeserializationBarrier()
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


