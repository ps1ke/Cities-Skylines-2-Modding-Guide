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
public void Bind(Volume volume)
	{
		OnBindVolumeProperties(volume);
		CollectVolumeParameters();
	}
```

- `public CollectVolumeParameters() : System.Void`  

```csharp
public void CollectVolumeParameters()
	{
		List<VolumeParameter> list = new List<VolumeParameter>();
		FindParameters(this, list);
		parameters = list.AsReadOnly();
	}
```

- `private static FindParameters(System.Object o, System.Collections.Generic.List<UnityEngine.Rendering.VolumeParameter> parameters, System.Func<System.Reflection.FieldInfo, System.Boolean> filter = null) : System.Void`  

```csharp
private static void FindParameters(object o, List<VolumeParameter> parameters, Func<FieldInfo, bool> filter = null)
	{
		if (o == null)
		{
			return;
		}
		foreach (FieldInfo item2 in from t in o.GetType().GetFields(BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic)
			orderby t.MetadataToken
			select t)
		{
			if (item2.FieldType.IsSubclassOf(typeof(VolumeParameter)))
			{
				if (filter == null || filter(item2))
				{
					VolumeParameter item = (VolumeParameter)item2.GetValue(o);
					parameters.Add(item);
				}
			}
			else if (!item2.FieldType.IsArray && item2.FieldType.IsClass)
			{
				FindParameters(item2.GetValue(o), parameters, filter);
			}
		}
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public GetFieldsInfo() : System.Reflection.FieldInfo[]`  

```csharp
public FieldInfo[] GetFieldsInfo()
	{
		return (from x in GetType().GetFields(BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic)
			orderby x.MetadataToken
			where x.FieldType.IsSubclassOf(typeof(VolumeParameter))
			select x).ToArray();
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
	}
```

- `protected abstract OnBindVolumeProperties(UnityEngine.Rendering.Volume volume) : System.Void`  

```csharp
protected abstract System.Void OnBindVolumeProperties(UnityEngine.Rendering.Volume volume);
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected override void OnEnable()
	{
		CollectVolumeParameters();
		foreach (VolumeParameter parameter in parameters)
		{
			if (parameter != null)
			{
				parameter.OnEnable();
			}
			else
			{
				UnityEngine.Debug.LogWarning("OverrideablePropertiesComponent " + GetType().Name + " contains a null parameter");
			}
		}
	}
```

- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent state, System.Single interpFactor = 1) : System.Void`  

```csharp
public virtual void Override(OverrideablePropertiesComponent previous, OverrideablePropertiesComponent to, float interpFactor = 1f)
	{
		int count = parameters.Count;
		m_InterpolationMode = to.m_InterpolationMode;
		m_InterpolationTime = to.m_InterpolationTime;
		for (int i = 0; i < count; i++)
		{
			VolumeParameter volumeParameter = previous.parameters[i];
			VolumeParameter volumeParameter2 = to.parameters[i];
			if (volumeParameter2.overrideState)
			{
				parameters[i].overrideState = volumeParameter2.overrideState;
				parameters[i].Interp(volumeParameter, volumeParameter2, interpFactor);
			}
		}
	}
```

- `public virtual Override(Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent to, System.Single interpFactor = 1) : System.Void`  

```csharp
public virtual void Override(OverrideablePropertiesComponent previous, OverrideablePropertiesComponent to, float interpFactor = 1f)
	{
		int count = parameters.Count;
		m_InterpolationMode = to.m_InterpolationMode;
		m_InterpolationTime = to.m_InterpolationTime;
		for (int i = 0; i < count; i++)
		{
			VolumeParameter volumeParameter = previous.parameters[i];
			VolumeParameter volumeParameter2 = to.parameters[i];
			if (volumeParameter2.overrideState)
			{
				parameters[i].overrideState = volumeParameter2.overrideState;
				parameters[i].Interp(volumeParameter, volumeParameter2, interpFactor);
			}
		}
	}
```

- `public SetAllOverridesTo(System.Boolean state) : System.Void`  

```csharp
public void SetAllOverridesTo(bool state)
	{
		SetOverridesTo(parameters, state);
	}
```

- `private SetOverridesTo(System.Collections.Generic.IEnumerable<UnityEngine.Rendering.VolumeParameter> enumerable, System.Boolean state) : System.Void`  

```csharp
private void SetOverridesTo(IEnumerable<VolumeParameter> enumerable, bool state)
	{
		foreach (VolumeParameter item in enumerable)
		{
			item.overrideState = state;
			Type type = item.GetType();
			if (VolumeParameter.IsObjectParameter(type))
			{
				ReadOnlyCollection<VolumeParameter> readOnlyCollection = (ReadOnlyCollection<VolumeParameter>)type.GetProperty("parameters", BindingFlags.Instance | BindingFlags.NonPublic).GetValue(item, null);
				if (readOnlyCollection != null)
				{
					SetOverridesTo(readOnlyCollection, state);
				}
			}
		}
	}
```


## Nested types

- `Game.Prefabs.Climate.OverrideablePropertiesComponent+InterpolationMode`  
- `Game.Prefabs.Climate.OverrideablePropertiesComponent+<>c`  

