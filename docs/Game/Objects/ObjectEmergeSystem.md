# Game.Objects.ObjectEmergeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_DeletedBuildingQuery`  
- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  
- `private Unity.Entities.EntityQuery m_EmergeObjectQuery`  
- `private Unity.Entities.EntityQuery m_CreaturePrefabQuery`  
- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  
- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  
- `private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectEmergeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  
- `private static SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  
- `public static SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  

## Nested types

- `Game.Objects.ObjectEmergeSystem+FindObjectsInBuildingJob`  
- `Game.Objects.ObjectEmergeSystem+FindObjectsInVehiclesJob`  
- `Game.Objects.ObjectEmergeSystem+EmergeObjectsJob`  
- `Game.Objects.ObjectEmergeSystem+TypeHandle`  

