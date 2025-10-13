# Game.Prefabs.WeatherAudioPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class WeatherAudioPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EffectPrefab m_WaterAmbientAudio;
    public System.Single m_WaterAudioIntensity;
    public System.Single m_WaterFadeSpeed;
    public System.Int32 m_WaterAudioEnabledZoom;
    public System.Int32 m_WaterAudioNearDistance;
    public System.Single m_LightningSoundSpeed;
    public Game.Prefabs.EffectPrefab m_LightningAudio;

    public WeatherAudioPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EffectPrefab m_WaterAmbientAudio`  

```csharp
public Game.Prefabs.EffectPrefab m_WaterAmbientAudio;
```

- `public System.Single m_WaterAudioIntensity`  

```csharp
public System.Single m_WaterAudioIntensity;
```

- `public System.Single m_WaterFadeSpeed`  

```csharp
public System.Single m_WaterFadeSpeed;
```

- `public System.Int32 m_WaterAudioEnabledZoom`  

```csharp
public System.Int32 m_WaterAudioEnabledZoom;
```

- `public System.Int32 m_WaterAudioNearDistance`  

```csharp
public System.Int32 m_WaterAudioNearDistance;
```

- `public System.Single m_LightningSoundSpeed`  

```csharp
public System.Single m_LightningSoundSpeed;
```

- `public Game.Prefabs.EffectPrefab m_LightningAudio`  

```csharp
public Game.Prefabs.EffectPrefab m_LightningAudio;
```


## Constructors

- `public WeatherAudioPrefab()`  

```csharp
public WeatherAudioPrefab();
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

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


