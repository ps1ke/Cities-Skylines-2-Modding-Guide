# Game.Prefabs.Bridge

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Bridge : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_SegmentLength;
    public System.Single m_Hanging;
    public System.Single m_ElevationOnWater;
    public System.Boolean m_CanCurve;
    public System.Boolean m_AllowMinimalLength;
    public Game.Prefabs.BridgeWaterFlow m_WaterFlow;
    public Game.Prefabs.BridgeBuildStyle m_BuildStyle;
    public Game.Prefabs.FixedNetSegmentInfo[] m_FixedSegments;

    public Bridge();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Single m_SegmentLength`  

```csharp
public System.Single m_SegmentLength;
```

- `public System.Single m_Hanging`  

```csharp
public System.Single m_Hanging;
```

- `public System.Single m_ElevationOnWater`  

```csharp
public System.Single m_ElevationOnWater;
```

- `public System.Boolean m_CanCurve`  

```csharp
public System.Boolean m_CanCurve;
```

- `public System.Boolean m_AllowMinimalLength`  

```csharp
public System.Boolean m_AllowMinimalLength;
```

- `public Game.Prefabs.BridgeWaterFlow m_WaterFlow`  

```csharp
public Game.Prefabs.BridgeWaterFlow m_WaterFlow;
```

- `public Game.Prefabs.BridgeBuildStyle m_BuildStyle`  

```csharp
public Game.Prefabs.BridgeBuildStyle m_BuildStyle;
```

- `public Game.Prefabs.FixedNetSegmentInfo[] m_FixedSegments`  

```csharp
public Game.Prefabs.FixedNetSegmentInfo[] m_FixedSegments;
```


## Constructors

- `public Bridge()`  

```csharp
public Bridge();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


