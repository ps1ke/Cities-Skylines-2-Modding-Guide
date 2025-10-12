# Game.Simulation.TransportBoardingHelpers+BoardingData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.TransportBoardingHelpers+BoardingItem> m_BoardingQueue`  

## Constructors

- `public BoardingData(Unity.Collections.Allocator allocator)`  

## Methods

- `public Dispose() : System.Void`  
- `public Dispose(Unity.Jobs.JobHandle inputDeps) : System.Void`  
- `public ScheduleBoarding(Unity.Entities.SystemBase system, Game.Simulation.CityStatisticsSystem statsSystem, Game.Achievements.AchievementTriggerSystem achievementTriggerSystem, Game.Simulation.TransportBoardingHelpers+BoardingLookupData lookupData, System.UInt32 simulationFrameIndex, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public ToConcurrent() : Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent`  

## Nested types

- `Game.Simulation.TransportBoardingHelpers+BoardingData+Concurrent`  

