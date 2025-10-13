# Game.Prefabs.MilestonePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class MilestonePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_Index;
    public System.Int32 m_Reward;
    public System.Int32 m_DevTreePoints;
    public System.Int32 m_MapTiles;
    public System.Int32 m_LoanLimit;
    public System.Int32 m_XpRequried;
    public System.Boolean m_Major;
    public System.String m_Image;
    public UnityEngine.Color m_BackgroundColor;
    public UnityEngine.Color m_AccentColor;
    public UnityEngine.Color m_TextColor;

    public MilestonePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```

- `public System.Int32 m_Reward`  

```csharp
public System.Int32 m_Reward;
```

- `public System.Int32 m_DevTreePoints`  

```csharp
public System.Int32 m_DevTreePoints;
```

- `public System.Int32 m_MapTiles`  

```csharp
public System.Int32 m_MapTiles;
```

- `public System.Int32 m_LoanLimit`  

```csharp
public System.Int32 m_LoanLimit;
```

- `public System.Int32 m_XpRequried`  

```csharp
public System.Int32 m_XpRequried;
```

- `public System.Boolean m_Major`  

```csharp
public System.Boolean m_Major;
```

- `public System.String m_Image`  

```csharp
public System.String m_Image;
```

- `public UnityEngine.Color m_BackgroundColor`  

```csharp
public UnityEngine.Color m_BackgroundColor;
```

- `public UnityEngine.Color m_AccentColor`  

```csharp
public UnityEngine.Color m_AccentColor;
```

- `public UnityEngine.Color m_TextColor`  

```csharp
public UnityEngine.Color m_TextColor;
```


## Constructors

- `public MilestonePrefab()`  

```csharp
public MilestonePrefab();
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

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


