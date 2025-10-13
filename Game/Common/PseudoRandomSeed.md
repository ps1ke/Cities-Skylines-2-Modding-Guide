# Game.Common.PseudoRandomSeed

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PseudoRandomSeed : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt16 m_Seed;
    public static readonly System.UInt16 kEffectCondition;
    public static readonly System.UInt16 kSubObject;
    public static readonly System.UInt16 kSecondaryObject;
    public static readonly System.UInt16 kSplitEdge;
    public static readonly System.UInt16 kEdgeNodes;
    public static readonly System.UInt16 kColorVariation;
    public static readonly System.UInt16 kBuildingState;
    public static readonly System.UInt16 kSubLane;
    public static readonly System.UInt16 kDummyPassengers;
    public static readonly System.UInt16 kLightState;
    public static readonly System.UInt16 kBrightnessLimit;
    public static readonly System.UInt16 kDrivingStyle;
    public static readonly System.UInt16 kFlowOffset;
    public static readonly System.UInt16 kMeshGroup;
    public static readonly System.UInt16 kCollapse;
    public static readonly System.UInt16 kDummyName;
    public static readonly System.UInt16 kTemperatureLimit;
    public static readonly System.UInt16 kAreaBorder;
    public static readonly System.UInt16 kParkedCars;

    public PseudoRandomSeed(System.UInt16 seed);
    public PseudoRandomSeed(Unity.Mathematics.Random& random);

    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Mathematics.Random GetRandom(System.UInt32 reason);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt16 m_Seed`  

```csharp
public System.UInt16 m_Seed;
```

- `public static readonly System.UInt16 kEffectCondition`  

```csharp
public static readonly System.UInt16 kEffectCondition;
```

- `public static readonly System.UInt16 kSubObject`  

```csharp
public static readonly System.UInt16 kSubObject;
```

- `public static readonly System.UInt16 kSecondaryObject`  

```csharp
public static readonly System.UInt16 kSecondaryObject;
```

- `public static readonly System.UInt16 kSplitEdge`  

```csharp
public static readonly System.UInt16 kSplitEdge;
```

- `public static readonly System.UInt16 kEdgeNodes`  

```csharp
public static readonly System.UInt16 kEdgeNodes;
```

- `public static readonly System.UInt16 kColorVariation`  

```csharp
public static readonly System.UInt16 kColorVariation;
```

- `public static readonly System.UInt16 kBuildingState`  

```csharp
public static readonly System.UInt16 kBuildingState;
```

- `public static readonly System.UInt16 kSubLane`  

```csharp
public static readonly System.UInt16 kSubLane;
```

- `public static readonly System.UInt16 kDummyPassengers`  

```csharp
public static readonly System.UInt16 kDummyPassengers;
```

- `public static readonly System.UInt16 kLightState`  

```csharp
public static readonly System.UInt16 kLightState;
```

- `public static readonly System.UInt16 kBrightnessLimit`  

```csharp
public static readonly System.UInt16 kBrightnessLimit;
```

- `public static readonly System.UInt16 kDrivingStyle`  

```csharp
public static readonly System.UInt16 kDrivingStyle;
```

- `public static readonly System.UInt16 kFlowOffset`  

```csharp
public static readonly System.UInt16 kFlowOffset;
```

- `public static readonly System.UInt16 kMeshGroup`  

```csharp
public static readonly System.UInt16 kMeshGroup;
```

- `public static readonly System.UInt16 kCollapse`  

```csharp
public static readonly System.UInt16 kCollapse;
```

- `public static readonly System.UInt16 kDummyName`  

```csharp
public static readonly System.UInt16 kDummyName;
```

- `public static readonly System.UInt16 kTemperatureLimit`  

```csharp
public static readonly System.UInt16 kTemperatureLimit;
```

- `public static readonly System.UInt16 kAreaBorder`  

```csharp
public static readonly System.UInt16 kAreaBorder;
```

- `public static readonly System.UInt16 kParkedCars`  

```csharp
public static readonly System.UInt16 kParkedCars;
```


## Constructors

- `public PseudoRandomSeed(System.UInt16 seed)`  

```csharp
public PseudoRandomSeed(System.UInt16 seed);
```

- `public PseudoRandomSeed(Unity.Mathematics.Random& random)`  

```csharp
public PseudoRandomSeed(Unity.Mathematics.Random& random);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetRandom(System.UInt32 reason) : Unity.Mathematics.Random`  

```csharp
public Unity.Mathematics.Random GetRandom(System.UInt32 reason);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


