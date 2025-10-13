# Game.Prefabs.Modes.ModePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class ModePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> <modeDebugUILogs>k__BackingField;

    public System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> modeDebugUILogs { get; private set; }

    protected ModePrefab();

    public System.Void ClearLog();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected System.Void RecordLog<T>(Unity.Entities.Entity entity, T& value);
    protected System.Void RecordLog<T>(Unity.Entities.Entity entity, DynamicBuffer`1& value);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> <modeDebugUILogs>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> <modeDebugUILogs>k__BackingField;
```


## Properties

- `public System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> modeDebugUILogs { get; private set }`  

```csharp
public System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo>> modeDebugUILogs { get; private set; }
```


## Constructors

- `protected ModePrefab()`  

```csharp
protected ModePrefab();
```


## Methods

- `public ClearLog() : System.Void`  

```csharp
public void ClearLog()
	{
		modeDebugUILogs?.Clear();
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<GameModeComponent>());
	}
```

- `protected RecordLog<T>(Unity.Entities.Entity entity, T& value) : System.Void`  

```csharp
protected System.Void RecordLog<T>(Unity.Entities.Entity entity, T& value);
```

- `protected RecordLog<T>(Unity.Entities.Entity entity, DynamicBuffer`1& value) : System.Void`  

```csharp
protected System.Void RecordLog<T>(Unity.Entities.Entity entity, DynamicBuffer`1& value);
```


## Nested types

- `Game.Prefabs.Modes.ModePrefab+ModeDebugUILogInfo`  
- `Game.Prefabs.Modes.ModePrefab+<>c__DisplayClass7_0<T>`  
- `Game.Prefabs.Modes.ModePrefab+<>c__DisplayClass8_0<T>`  

