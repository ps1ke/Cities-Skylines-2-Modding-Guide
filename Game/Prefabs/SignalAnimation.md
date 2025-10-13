# Game.Prefabs.SignalAnimation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SignalAnimation
{
    private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer;
    private System.Single m_LengthFactor;

    public SignalAnimation(Game.Prefabs.SignalGroupMask[] masks);

    public System.Single Evaluate(Game.Prefabs.SignalGroupMask signalGroupMask, System.Single time);
}
```


## Fields

- `private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer`  

```csharp
private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer;
```

- `private System.Single m_LengthFactor`  

```csharp
private System.Single m_LengthFactor;
```


## Constructors

- `public SignalAnimation(Game.Prefabs.SignalGroupMask[] masks)`  

```csharp
public SignalAnimation(SignalGroupMask[] masks)
	{
		m_Buffer = default(FixedList128Bytes<SignalGroupMask>);
		m_Buffer.Length = masks.Length;
		for (int i = 0; i < masks.Length; i++)
		{
			m_Buffer[i] = masks[i];
		}
		m_LengthFactor = m_Buffer.Length;
	}
```


## Methods

- `public Evaluate(Game.Prefabs.SignalGroupMask signalGroupMask, System.Single time) : System.Single`  

```csharp
public float Evaluate(SignalGroupMask signalGroupMask, float time)
	{
		int index = math.clamp((int)math.floor(time * m_LengthFactor), 0, m_Buffer.Length - 1);
		return math.select(0f, 1f, (m_Buffer[index] & signalGroupMask) != 0);
	}
```


