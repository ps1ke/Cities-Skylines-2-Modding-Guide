# Game.Prefabs.TrafficSignData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TrafficSignData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.UInt32 m_TypeMask;
    public System.Int32 m_SpeedLimit;

    public static System.UInt32 GetTypeMask(Game.Prefabs.TrafficSignType type);
}
```


## Fields

- `public System.UInt32 m_TypeMask`  

```csharp
public System.UInt32 m_TypeMask;
```

- `public System.Int32 m_SpeedLimit`  

```csharp
public System.Int32 m_SpeedLimit;
```


## Methods

- `public static GetTypeMask(Game.Prefabs.TrafficSignType type) : System.UInt32`  

```csharp
public static uint GetTypeMask(TrafficSignType type)
	{
		if (type == TrafficSignType.None)
		{
			return 0u;
		}
		return (uint)(1 << (int)(17 - type));
	}
```


