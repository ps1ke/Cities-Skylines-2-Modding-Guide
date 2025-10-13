# Game.Events.HotspotFrame

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct HotspotFrame : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Velocity;

    public HotspotFrame(Game.Events.WeatherPhenomenon weatherPhenomenon);

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Velocity`  

```csharp
public Unity.Mathematics.float3 m_Velocity;
```


## Constructors

- `public HotspotFrame(Game.Events.WeatherPhenomenon weatherPhenomenon)`  

```csharp
public HotspotFrame(WeatherPhenomenon weatherPhenomenon)
	{
		m_Position = weatherPhenomenon.m_HotspotPosition;
		m_Velocity = weatherPhenomenon.m_HotspotVelocity;
	}
```


