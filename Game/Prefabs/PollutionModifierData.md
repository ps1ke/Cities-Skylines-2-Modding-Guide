# Game.Prefabs.PollutionModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PollutionModifierData>`  

## Code

```csharp
public sealed struct PollutionModifierData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PollutionModifierData>
{
    public System.Single m_GroundPollutionMultiplier;
    public System.Single m_AirPollutionMultiplier;
    public System.Single m_NoisePollutionMultiplier;

    public System.Void Combine(Game.Prefabs.PollutionModifierData otherData);
}
```


## Fields

- `public System.Single m_GroundPollutionMultiplier`  

```csharp
public System.Single m_GroundPollutionMultiplier;
```

- `public System.Single m_AirPollutionMultiplier`  

```csharp
public System.Single m_AirPollutionMultiplier;
```

- `public System.Single m_NoisePollutionMultiplier`  

```csharp
public System.Single m_NoisePollutionMultiplier;
```


## Methods

- `public Combine(Game.Prefabs.PollutionModifierData otherData) : System.Void`  

```csharp
public void Combine(PollutionModifierData otherData)
	{
		m_GroundPollutionMultiplier += otherData.m_GroundPollutionMultiplier;
		m_AirPollutionMultiplier += otherData.m_AirPollutionMultiplier;
		m_NoisePollutionMultiplier += otherData.m_NoisePollutionMultiplier;
	}
```


