# Game.Creatures.ResetTrip

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ResetTrip : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Creature;
    public Unity.Entities.Entity m_Source;
    public Unity.Entities.Entity m_Target;
    public Unity.Entities.Entity m_DivertTarget;
    public Unity.Entities.Entity m_NextTarget;
    public Unity.Entities.Entity m_Arrived;
    public Game.Economy.Resource m_TravelResource;
    public Game.Economy.Resource m_DivertResource;
    public Game.Economy.Resource m_NextResource;
    public Game.Creatures.ResidentFlags m_ResidentFlags;
    public System.Int32 m_TravelData;
    public System.Int32 m_DivertData;
    public System.Int32 m_NextData;
    public System.UInt32 m_Delay;
    public Game.Citizens.Purpose m_TravelPurpose;
    public Game.Citizens.Purpose m_DivertPurpose;
    public Game.Citizens.Purpose m_NextPurpose;
    public System.Boolean m_HasDivertPath;

}
```


## Fields

- `public Unity.Entities.Entity m_Creature`  

```csharp
public Unity.Entities.Entity m_Creature;
```

- `public Unity.Entities.Entity m_Source`  

```csharp
public Unity.Entities.Entity m_Source;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Entities.Entity m_DivertTarget`  

```csharp
public Unity.Entities.Entity m_DivertTarget;
```

- `public Unity.Entities.Entity m_NextTarget`  

```csharp
public Unity.Entities.Entity m_NextTarget;
```

- `public Unity.Entities.Entity m_Arrived`  

```csharp
public Unity.Entities.Entity m_Arrived;
```

- `public Game.Economy.Resource m_TravelResource`  

```csharp
public Game.Economy.Resource m_TravelResource;
```

- `public Game.Economy.Resource m_DivertResource`  

```csharp
public Game.Economy.Resource m_DivertResource;
```

- `public Game.Economy.Resource m_NextResource`  

```csharp
public Game.Economy.Resource m_NextResource;
```

- `public Game.Creatures.ResidentFlags m_ResidentFlags`  

```csharp
public Game.Creatures.ResidentFlags m_ResidentFlags;
```

- `public System.Int32 m_TravelData`  

```csharp
public System.Int32 m_TravelData;
```

- `public System.Int32 m_DivertData`  

```csharp
public System.Int32 m_DivertData;
```

- `public System.Int32 m_NextData`  

```csharp
public System.Int32 m_NextData;
```

- `public System.UInt32 m_Delay`  

```csharp
public System.UInt32 m_Delay;
```

- `public Game.Citizens.Purpose m_TravelPurpose`  

```csharp
public Game.Citizens.Purpose m_TravelPurpose;
```

- `public Game.Citizens.Purpose m_DivertPurpose`  

```csharp
public Game.Citizens.Purpose m_DivertPurpose;
```

- `public Game.Citizens.Purpose m_NextPurpose`  

```csharp
public Game.Citizens.Purpose m_NextPurpose;
```

- `public System.Boolean m_HasDivertPath`  

```csharp
public System.Boolean m_HasDivertPath;
```


