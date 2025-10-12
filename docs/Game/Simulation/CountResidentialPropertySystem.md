# Game.Simulation.CountResidentialPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData`  
- `private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData`  
- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  
- `private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle`  

## Properties

- `public Unity.Mathematics.int3 FreeProperties { get }`  
- `public Unity.Mathematics.int3 TotalProperties { get }`  
- `public System.Int32 FreeShelterCapacity { get }`  
- `public System.Int32 TotalShelterCapacity { get }`  

## Constructors

- `public CountResidentialPropertySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetResidentialPropertyData() : Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  
- `Game.Simulation.CountResidentialPropertySystem+CountResidentialPropertyJob`  
- `Game.Simulation.CountResidentialPropertySystem+TypeHandle`  

