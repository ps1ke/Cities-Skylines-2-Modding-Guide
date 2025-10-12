# Game.Simulation.DeathCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_DeathCheckQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  
- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  
- `private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kMaxAgeInGameYear`  

## Constructors

- `public DeathCheckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens) : System.Void`  

## Nested types

- `Game.Simulation.DeathCheckSystem+DeathCheckJob`  
- `Game.Simulation.DeathCheckSystem+TypeHandle`  

