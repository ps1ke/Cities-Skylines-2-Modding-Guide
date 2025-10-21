# Game.Prefabs.ColorProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ColorProperties : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations;
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding;
    public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups;
    public Unity.Mathematics.int3 m_VariationRanges;
    public Unity.Mathematics.int3 m_AlphaRanges;
    public Game.Rendering.ColorSourceType m_ExternalColorSource;

    public ColorProperties();

    public System.Boolean CanBeModifiedByExternal(System.SByte channel);
    public System.Int32 GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def);
    public System.Single GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public UnityEngine.Color GetColor(System.Int32 index, System.SByte channel);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Boolean SanityCheck(System.SByte channel);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations;
```

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding;
```

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups;
```

- `public Unity.Mathematics.int3 m_VariationRanges`  

```csharp
public Unity.Mathematics.int3 m_VariationRanges;
```

- `public Unity.Mathematics.int3 m_AlphaRanges`  

```csharp
public Unity.Mathematics.int3 m_AlphaRanges;
```

- `public Game.Rendering.ColorSourceType m_ExternalColorSource`  

```csharp
public Game.Rendering.ColorSourceType m_ExternalColorSource;
```


## Constructors

- `public ColorProperties()`  

```csharp
public ColorProperties();
```


## Methods

- `public CanBeModifiedByExternal(System.SByte channel) : System.Boolean`  

```csharp
public System.Boolean CanBeModifiedByExternal(System.SByte channel);
```

- `public GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def) : System.Int32`  

```csharp
public System.Int32 GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def);
```

- `public GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def) : System.Single`  

```csharp
public System.Single GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetColor(System.Int32 index, System.SByte channel) : UnityEngine.Color`  

```csharp
public UnityEngine.Color GetColor(System.Int32 index, System.SByte channel);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public SanityCheck(System.SByte channel) : System.Boolean`  

```csharp
public System.Boolean SanityCheck(System.SByte channel);
```


## Nested types

- `Game.Prefabs.ColorProperties+VariationSet`  
- `Game.Prefabs.ColorProperties+ColorChannelBinding`  
- `Game.Prefabs.ColorProperties+VariationGroup`  

