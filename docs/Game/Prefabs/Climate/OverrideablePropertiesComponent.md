# Game.Prefabs.Climate.OverrideablePropertiesComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Climate`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

## Fields

- `public Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode m_InterpolationMode`  
- `public System.Single m_InterpolationTime`  
- `private System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> <parameters>k__BackingField`  

## Properties

- `public System.Boolean hasTimeBasedInterpolation { get }`  
- `public System.Collections.ObjectModel.ReadOnlyCollection<UnityEngine.Rendering.VolumeParameter> parameters { get; private set }`  

## Constructors

- `protected OverrideablePropertiesComponent()`  

## Methods

- `public Bind(UnityEngine.Rendering.Volume volume) : System.Void`  
- `public CollectVolumeParameters() : System.Void`  
- `private static FindParameters(System.Object o, System.Collections.Generic.List<UnityEngine.Rendering.VolumeParameter> parameters, System.Func<System.Reflection.FieldInfo, System.Boolean> filter = null) : System.Void`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetFieldsInfo() : System.Reflection.FieldInfo[]`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `protected abstract OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  
- `protected virtual OnEnable() : System.Void`  
- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent state, System.Single interpFactor = 1) : System.Void`  
- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent to, System.Single interpFactor = 1) : System.Void`  
- `public SetAllOverridesTo(System.Boolean state) : System.Void`  
- `private SetOverridesTo(System.Collections.Generic.IEnumerable<UnityEngine.Rendering.VolumeParameter> enumerable, System.Boolean state) : System.Void`  

## Nested types

- `Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode`  
- `Game.Prefabs.Climate.OverrideablePropertiesComponent+<>c`  

