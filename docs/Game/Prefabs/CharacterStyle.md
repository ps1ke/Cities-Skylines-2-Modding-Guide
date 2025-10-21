# Game.Prefabs.CharacterStyle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class CharacterStyle : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_ShapeCount;
    public System.Int32 m_BoneCount;
    public Game.Prefabs.GenderMask m_Gender;
    public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations;

    public System.Boolean ignoreUnlockDependencies { get; }

    public CharacterStyle();

    public System.Void CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex);
    public Colossal.IO.AssetDatabase.AnimationAsset GetAnimation(System.Int32 index);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.Int32 m_ShapeCount`  

```csharp
public System.Int32 m_ShapeCount;
```

- `public System.Int32 m_BoneCount`  

```csharp
public System.Int32 m_BoneCount;
```

- `public Game.Prefabs.GenderMask m_Gender`  

```csharp
public Game.Prefabs.GenderMask m_Gender;
```

- `public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations`  

```csharp
public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public CharacterStyle()`  

```csharp
public CharacterStyle();
```


## Methods

- `public CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex) : System.Void`  

```csharp
public System.Void CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex);
```

- `public GetAnimation(System.Int32 index) : Colossal.IO.AssetDatabase.AnimationAsset`  

```csharp
public Colossal.IO.AssetDatabase.AnimationAsset GetAnimation(System.Int32 index);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


## Nested types

- `Game.Prefabs.CharacterStyle+AnimationMotion`  
- `Game.Prefabs.CharacterStyle+AnimationInfo`  

