# Game.Common.AllowAudioEndBarrier

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class AllowAudioEndBarrier : Game.GameSystemBase
{
    private Game.Common.AudioEndBarrier m_AudioEndBarrier;

    public AllowAudioEndBarrier();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.AudioEndBarrier m_AudioEndBarrier`  

```csharp
private Game.Common.AudioEndBarrier m_AudioEndBarrier;
```


## Constructors

- `public AllowAudioEndBarrier()`  

```csharp
[Preserve]
	public AllowAudioEndBarrier()
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
		m_AudioEndBarrier = base.World.GetOrCreateSystemManaged<AudioEndBarrier>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_AudioEndBarrier.AllowUsage();
	}
```


