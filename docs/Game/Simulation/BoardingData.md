# Game.Simulation.TransportBoardingHelpers+BoardingData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct BoardingData
{
    private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue;

    public BoardingData(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
    public System.Void Dispose(Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle ScheduleBoarding(Unity.Entities.SystemBase system, Game.Simulation.CityStatisticsSystem statsSystem, Game.Achievements.AchievementTriggerSystem achievementTriggerSystem, Game.Simulation.TransportBoardingHelpers+BoardingLookupData lookupData, System.UInt32 simulationFrameIndex, Unity.Jobs.JobHandle inputDeps);
    public Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent ToConcurrent();
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue;
```


## Constructors

- `public BoardingData(Unity.Collections.Allocator allocator)`  

```csharp
public BoardingData(Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Dispose(Unity.Jobs.JobHandle inputDeps) : System.Void`  

```csharp
public System.Void Dispose(Unity.Jobs.JobHandle inputDeps);
```

- `public ScheduleBoarding(Unity.Entities.SystemBase system, Game.Simulation.CityStatisticsSystem statsSystem, Game.Achievements.AchievementTriggerSystem achievementTriggerSystem, Game.Simulation.TransportBoardingHelpers+BoardingLookupData lookupData, System.UInt32 simulationFrameIndex, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle ScheduleBoarding(Unity.Entities.SystemBase system, Game.Simulation.CityStatisticsSystem statsSystem, Game.Achievements.AchievementTriggerSystem achievementTriggerSystem, Game.Simulation.TransportBoardingHelpers+BoardingLookupData lookupData, System.UInt32 simulationFrameIndex, Unity.Jobs.JobHandle inputDeps);
```

- `public ToConcurrent() : Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent`  

```csharp
public Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent ToConcurrent();
```


## Nested types

- `Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent`  

