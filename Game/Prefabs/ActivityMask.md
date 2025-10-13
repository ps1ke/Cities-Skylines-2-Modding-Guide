# Game.Prefabs.ActivityMask

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ActivityMask
{
    public System.UInt32 m_Mask;

    public ActivityMask(Game.Prefabs.ActivityType type);

}
```


## Fields

- `public System.UInt32 m_Mask`  

```csharp
public System.UInt32 m_Mask;
```


## Constructors

- `public ActivityMask(Game.Prefabs.ActivityType type)`  

```csharp
public ActivityMask(ActivityType type)
	{
		if (type == ActivityType.None)
		{
			m_Mask = 0u;
		}
		else
		{
			m_Mask = (uint)(1 << (int)(type - 1));
		}
	}
```


