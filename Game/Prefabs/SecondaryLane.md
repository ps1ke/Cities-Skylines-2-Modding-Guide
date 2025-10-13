# Game.Prefabs.SecondaryLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SecondaryLane : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.SecondaryLaneInfo[] m_LeftLanes;
    public Game.Prefabs.SecondaryLaneInfo[] m_RightLanes;
    public Game.Prefabs.SecondaryLaneInfo2[] m_CrossingLanes;
    public System.Boolean m_CanFlipSides;
    public System.Boolean m_DuplicateSides;
    public System.Boolean m_RequireParallel;
    public System.Boolean m_RequireOpposite;
    public System.Boolean m_SkipSafePedestrianOverlap;
    public System.Boolean m_SkipSafeCarOverlap;
    public System.Boolean m_SkipUnsafeCarOverlap;
    public System.Boolean m_SkipTrackOverlap;
    public System.Boolean m_SkipMergeOverlap;
    public System.Boolean m_FitToParkingSpaces;
    public System.Boolean m_EvenSpacing;
    public Unity.Mathematics.float3 m_PositionOffset;
    public Unity.Mathematics.float2 m_LengthOffset;
    public System.Single m_CutMargin;
    public System.Single m_CutOffset;
    public System.Single m_CutOverlap;
    public System.Single m_Spacing;

    public SecondaryLane();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Prefabs.SecondaryLaneInfo[] m_LeftLanes`  

```csharp
public Game.Prefabs.SecondaryLaneInfo[] m_LeftLanes;
```

- `public Game.Prefabs.SecondaryLaneInfo[] m_RightLanes`  

```csharp
public Game.Prefabs.SecondaryLaneInfo[] m_RightLanes;
```

- `public Game.Prefabs.SecondaryLaneInfo2[] m_CrossingLanes`  

```csharp
public Game.Prefabs.SecondaryLaneInfo2[] m_CrossingLanes;
```

- `public System.Boolean m_CanFlipSides`  

```csharp
public System.Boolean m_CanFlipSides;
```

- `public System.Boolean m_DuplicateSides`  

```csharp
public System.Boolean m_DuplicateSides;
```

- `public System.Boolean m_RequireParallel`  

```csharp
public System.Boolean m_RequireParallel;
```

- `public System.Boolean m_RequireOpposite`  

```csharp
public System.Boolean m_RequireOpposite;
```

- `public System.Boolean m_SkipSafePedestrianOverlap`  

```csharp
public System.Boolean m_SkipSafePedestrianOverlap;
```

- `public System.Boolean m_SkipSafeCarOverlap`  

```csharp
public System.Boolean m_SkipSafeCarOverlap;
```

- `public System.Boolean m_SkipUnsafeCarOverlap`  

```csharp
public System.Boolean m_SkipUnsafeCarOverlap;
```

- `public System.Boolean m_SkipTrackOverlap`  

```csharp
public System.Boolean m_SkipTrackOverlap;
```

- `public System.Boolean m_SkipMergeOverlap`  

```csharp
public System.Boolean m_SkipMergeOverlap;
```

- `public System.Boolean m_FitToParkingSpaces`  

```csharp
public System.Boolean m_FitToParkingSpaces;
```

- `public System.Boolean m_EvenSpacing`  

```csharp
public System.Boolean m_EvenSpacing;
```

- `public Unity.Mathematics.float3 m_PositionOffset`  

```csharp
public Unity.Mathematics.float3 m_PositionOffset;
```

- `public Unity.Mathematics.float2 m_LengthOffset`  

```csharp
public Unity.Mathematics.float2 m_LengthOffset;
```

- `public System.Single m_CutMargin`  

```csharp
public System.Single m_CutMargin;
```

- `public System.Single m_CutOffset`  

```csharp
public System.Single m_CutOffset;
```

- `public System.Single m_CutOverlap`  

```csharp
public System.Single m_CutOverlap;
```

- `public System.Single m_Spacing`  

```csharp
public System.Single m_Spacing;
```


## Constructors

- `public SecondaryLane()`  

```csharp
public SecondaryLane();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


