# Game.Common.RandomLocalizationIndex

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public System.Int32 m_Index`  
- `public static readonly Game.Common.RandomLocalizationIndex kNone`  

## Constructors

- `public RandomLocalizationIndex(System.Int32 index)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public static EnsureValidRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random) : System.Void`  
- `public static GenerateRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

