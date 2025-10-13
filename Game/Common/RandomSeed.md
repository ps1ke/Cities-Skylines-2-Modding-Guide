# Game.Common.RandomSeed

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RandomSeed
{
    private System.UInt32 m_Seed;
    private static Unity.Mathematics.Random m_Random;

    public Unity.Mathematics.Random GetRandom(System.Int32 index);
    public static Game.Common.RandomSeed Next();
}
```


## Fields

- `private System.UInt32 m_Seed`  

```csharp
private System.UInt32 m_Seed;
```

- `private static Unity.Mathematics.Random m_Random`  

```csharp
private static Unity.Mathematics.Random m_Random;
```


## Methods

- `public GetRandom(System.Int32 index) : Unity.Mathematics.Random`  

```csharp
public Unity.Mathematics.Random GetRandom(int index)
	{
		uint num = m_Seed ^ (uint)(370248451 * index);
		return new Unity.Mathematics.Random(math.select(num, 1851936439u, num == 0));
	}
```

- `public static Next() : Game.Common.RandomSeed`  

```csharp
public static RandomSeed Next()
	{
		return new RandomSeed
		{
			m_Seed = m_Random.NextUInt()
		};
	}
```


