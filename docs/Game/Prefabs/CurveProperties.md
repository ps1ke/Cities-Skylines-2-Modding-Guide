# Game.Prefabs.CurveProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CurveProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_TilingCount;
    public System.Single m_OverrideLength;
    public System.Single m_SmoothingDistance;
    public System.Boolean m_GeometryTiling;
    public System.Boolean m_StraightTiling;
    public System.Boolean m_InvertCurve;
    public System.Boolean m_SubFlow;
    public System.Boolean m_HangingSwaying;

    public CurveProperties();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_TilingCount`  

```csharp
public System.Int32 m_TilingCount;
```

- `public System.Single m_OverrideLength`  

```csharp
public System.Single m_OverrideLength;
```

- `public System.Single m_SmoothingDistance`  

```csharp
public System.Single m_SmoothingDistance;
```

- `public System.Boolean m_GeometryTiling`  

```csharp
public System.Boolean m_GeometryTiling;
```

- `public System.Boolean m_StraightTiling`  

```csharp
public System.Boolean m_StraightTiling;
```

- `public System.Boolean m_InvertCurve`  

```csharp
public System.Boolean m_InvertCurve;
```

- `public System.Boolean m_SubFlow`  

```csharp
public System.Boolean m_SubFlow;
```

- `public System.Boolean m_HangingSwaying`  

```csharp
public System.Boolean m_HangingSwaying;
```


## Constructors

- `public CurveProperties()`  

```csharp
public CurveProperties();
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


