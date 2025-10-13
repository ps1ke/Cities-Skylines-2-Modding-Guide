# Game.Simulation.TelecomCoverage

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TelecomCoverage : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_SignalStrength;
    public System.Byte m_NetworkLoad;

    public System.Int32 networkQuality { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public static System.Single SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Byte m_SignalStrength`  

```csharp
public System.Byte m_SignalStrength;
```

- `public System.Byte m_NetworkLoad`  

```csharp
public System.Byte m_NetworkLoad;
```


## Properties

- `public System.Int32 networkQuality { get }`  

```csharp
public System.Int32 networkQuality { get; }
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
		return 2;
	}
```

- `public static SampleNetworkQuality(Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> coverage, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static float SampleNetworkQuality(CellMapData<TelecomCoverage> coverage, float3 position)
	{
		float2 @float = position.xz / coverage.m_CellSize + (float2)coverage.m_TextureSize * 0.5f - 0.5f;
		int4 xyxy = ((int2)math.floor(@float)).xyxy;
		xyxy.zw += 1;
		xyxy = math.clamp(xyxy, 0, coverage.m_TextureSize.xyxy - 1);
		int4 @int = xyxy.xzxz + coverage.m_TextureSize.x * xyxy.yyww;
		TelecomCoverage telecomCoverage = coverage.m_Buffer[@int.x];
		TelecomCoverage telecomCoverage2 = coverage.m_Buffer[@int.y];
		TelecomCoverage telecomCoverage3 = coverage.m_Buffer[@int.z];
		TelecomCoverage telecomCoverage4 = coverage.m_Buffer[@int.w];
		float4 float2 = new float4((int)telecomCoverage.m_SignalStrength, (int)telecomCoverage2.m_SignalStrength, (int)telecomCoverage3.m_SignalStrength, (int)telecomCoverage4.m_SignalStrength);
		float4 float3 = math.min(y: float2 / (127.5f + new float4((int)telecomCoverage.m_NetworkLoad, (int)telecomCoverage2.m_NetworkLoad, (int)telecomCoverage3.m_NetworkLoad, (int)telecomCoverage4.m_NetworkLoad)), x: 1f);
		float2 float4 = math.saturate(@float - xyxy.xy);
		float2 float5 = math.lerp(float3.xz, float3.yw, float4.x);
		return math.lerp(float5.x, float5.y, float4.y);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


