# Game.Common.PseudoRandomSeed

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.UInt16 m_Seed`  
- `public static readonly System.UInt16 kEffectCondition`  
- `public static readonly System.UInt16 kSubObject`  
- `public static readonly System.UInt16 kSecondaryObject`  
- `public static readonly System.UInt16 kSplitEdge`  
- `public static readonly System.UInt16 kEdgeNodes`  
- `public static readonly System.UInt16 kColorVariation`  
- `public static readonly System.UInt16 kBuildingState`  
- `public static readonly System.UInt16 kSubLane`  
- `public static readonly System.UInt16 kDummyPassengers`  
- `public static readonly System.UInt16 kLightState`  
- `public static readonly System.UInt16 kBrightnessLimit`  
- `public static readonly System.UInt16 kDrivingStyle`  
- `public static readonly System.UInt16 kFlowOffset`  
- `public static readonly System.UInt16 kMeshGroup`  
- `public static readonly System.UInt16 kCollapse`  
- `public static readonly System.UInt16 kDummyName`  
- `public static readonly System.UInt16 kTemperatureLimit`  
- `public static readonly System.UInt16 kAreaBorder`  
- `public static readonly System.UInt16 kParkedCars`  

## Constructors

- `public PseudoRandomSeed(System.UInt16 seed)`  
- `public PseudoRandomSeed(Unity.Mathematics.Random& random)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetRandom(System.UInt32 reason) : Unity.Mathematics.Random`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

