# Game.Simulation.Wind

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Wind : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float2 m_Wind;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public static Unity.Mathematics.float2 SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_Wind`  

```csharp
public Unity.Mathematics.float2 m_Wind;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return UnsafeUtility.SizeOf<float2>();
	}
```

- `public static SampleWind(Game.Simulation.CellMapData<Game.Simulation.Wind> wind, Unity.Mathematics.float3 position) : Unity.Mathematics.float2`  

```csharp
public static float2 SampleWind(CellMapData<Wind> wind, float3 position)
	{
		float2 @float = position.xz / wind.m_CellSize + (float2)wind.m_TextureSize * 0.5f - 0.5f;
		int4 xyxy = ((int2)math.floor(@float)).xyxy;
		xyxy.zw += 1;
		xyxy = math.clamp(xyxy, 0, wind.m_TextureSize.xyxy - 1);
		int4 @int = xyxy.xzxz + wind.m_TextureSize.x * xyxy.yyww;
		float4 start = new float4(wind.m_Buffer[@int.x].m_Wind, wind.m_Buffer[@int.z].m_Wind);
		float4 end = new float4(wind.m_Buffer[@int.y].m_Wind, wind.m_Buffer[@int.w].m_Wind);
		float2 float2 = math.saturate(@float - xyxy.xy);
		float4 float3 = math.lerp(start, end, float2.x);
		return math.lerp(float3.xy, float3.zw, float2.y);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


