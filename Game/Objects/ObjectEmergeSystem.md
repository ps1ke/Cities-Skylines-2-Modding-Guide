# Game.Objects.ObjectEmergeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectEmergeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedBuildingQuery;
    private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
    private Unity.Entities.EntityQuery m_EmergeObjectQuery;
    private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
    private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes;
    private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
    private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
    private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle;

    public ObjectEmergeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static Unity.Entities.Entity SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed);
    private static System.Boolean SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public static Unity.Entities.Entity SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed);
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_EmergeObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmergeObjectQuery;
```

- `private Unity.Entities.EntityQuery m_CreaturePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
```

- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
```

- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
```

- `private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectEmergeSystem()`  

```csharp
public ObjectEmergeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed);
```

- `private static SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  

```csharp
private static System.Boolean SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
```

- `public static SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed);
```


## Nested types

- `Game.Objects.ObjectEmergeSystem+FindObjectsInBuildingJob`  
- `Game.Objects.ObjectEmergeSystem+FindObjectsInVehiclesJob`  
- `Game.Objects.ObjectEmergeSystem+EmergeObjectsJob`  
- `Game.Objects.ObjectEmergeSystem+TypeHandle`  

