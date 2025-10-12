# Game.Events.AddMeetingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  
- `private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue`  
- `private Unity.Entities.EntityQuery m_LeisureSettingsQuery`  
- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Jobs.JobHandle m_Deps`  
- `private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AddMeetingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddWriter(Unity.Jobs.JobHandle reader) : System.Void`  
- `public GetMeetingQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Events.AddMeetingSystem+AddMeeting`  
- `Game.Events.AddMeetingSystem+TravelJob`  
- `Game.Events.AddMeetingSystem+TypeHandle`  

