# Game.Prefabs.Climate.OverrideablePropertiesComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

## Code

```csharp
public abstract class OverrideablePropertiesComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode m_InterpolationMode;
    public System.Single m_InterpolationTime;
    private System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> <parameters>k__BackingField;

    public System.Boolean hasTimeBasedInterpolation { get; }
    public System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> parameters { get; private set; }

    protected OverrideablePropertiesComponent();

    public System.Void Bind(UnityEngine.Rendering.Volume volume);
    public System.Void CollectVolumeParameters();
    private static System.Void FindParameters(System.Object o, System.Collections.Generic.List<UnityEngine.Rendering.VolumeParameter> parameters, System.Func<System.Reflection.FieldInfo, System.Boolean> filter);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Reflection.FieldInfo[] GetFieldsInfo();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected abstract System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
    protected virtual System.Void OnEnable();
    public virtual System.Void Override(Game.Prefabs.Climate.OverrideablePropertiesComponent state, System.Single interpFactor);
    public virtual System.Void Override(Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent to, System.Single interpFactor);
    public System.Void SetAllOverridesTo(System.Boolean state);
    private System.Void SetOverridesTo(System.Collections.Generic.IEnumerable<UnityEngine.Rendering.VolumeParameter> enumerable, System.Boolean state);
}
```


## Fields

- `public Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode m_InterpolationMode`  

```csharp
public Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode m_InterpolationMode;
```

- `public System.Single m_InterpolationTime`  

```csharp
public System.Single m_InterpolationTime;
```

- `private System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> <parameters>k__BackingField`  

```csharp
private System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> <parameters>k__BackingField;
```


## Properties

- `public System.Boolean hasTimeBasedInterpolation { get }`  

```csharp
public System.Boolean hasTimeBasedInterpolation { get; }
```

- `public System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> parameters { get; private set }`  

```csharp
public System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> parameters { get; private set; }
```


## Constructors

- `protected OverrideablePropertiesComponent()`  

```csharp
protected OverrideablePropertiesComponent();
```


## Methods

- `public Bind(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
public System.Void Bind(UnityEngine.Rendering.Volume volume);
```

- `public CollectVolumeParameters() : System.Void`  

```csharp
public System.Void CollectVolumeParameters();
```

- `private static FindParameters(System.Object o, System.Collections.Generic.List<UnityEngine.Rendering.VolumeParameter> parameters, System.Func<System.Reflection.FieldInfo, System.Boolean> filter = null) : System.Void`  

```csharp
private static System.Void FindParameters(System.Object o, System.Collections.Generic.List<UnityEngine.Rendering.VolumeParameter> parameters, System.Func<System.Reflection.FieldInfo, System.Boolean> filter);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetFieldsInfo() : System.Reflection.FieldInfo[]`  

```csharp
public System.Reflection.FieldInfo[] GetFieldsInfo();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `protected abstract OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected abstract System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual System.Void OnEnable();
```

- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent state, System.Single interpFactor = 1) : System.Void`  

```csharp
public virtual System.Void Override(Game.Prefabs.Climate.OverrideablePropertiesComponent state, System.Single interpFactor);
```

- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent to, System.Single interpFactor = 1) : System.Void`  

```csharp
public virtual System.Void Override(Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent to, System.Single interpFactor);
```

- `public SetAllOverridesTo(System.Boolean state) : System.Void`  

```csharp
public System.Void SetAllOverridesTo(System.Boolean state);
```

- `private SetOverridesTo(System.Collections.Generic.IEnumerable<UnityEngine.Rendering.VolumeParameter> enumerable, System.Boolean state) : System.Void`  

```csharp
private System.Void SetOverridesTo(System.Collections.Generic.IEnumerable<UnityEngine.Rendering.VolumeParameter> enumerable, System.Boolean state);
```


## Nested types

- `Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode`  
- `Game.Prefabs.Climate.OverrideablePropertiesComponent+<>c`  

