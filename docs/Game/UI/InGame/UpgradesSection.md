# Game.UI.InGame.UpgradesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_SoundQuery;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set; }

    public UpgradesSection();

    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    private System.Void OnDelete(Unity.Entities.Entity entity);
    protected virtual System.Void OnDestroy();
    private System.Void OnFocus(Unity.Entities.Entity entity);
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnRelocate(Unity.Entities.Entity entity);
    private System.Void OnToggle(Unity.Entities.Entity entity);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  

```csharp
private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set; }
```


## Constructors

- `public UpgradesSection()`  

```csharp
public UpgradesSection();
```


## Methods

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `private OnDelete(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnDelete(Unity.Entities.Entity entity);
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnFocus(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnFocus(Unity.Entities.Entity entity);
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnRelocate(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnRelocate(Unity.Entities.Entity entity);
```

- `private OnToggle(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void OnToggle(Unity.Entities.Entity entity);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


