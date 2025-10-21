# Game.UI.InGame.InfoSectionBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class InfoSectionBase : Game.UI.UISystemBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Boolean <visible>k__BackingField;
    private System.Collections.Generic.List<System.String> <tooltipKeys>k__BackingField;
    private System.Collections.Generic.List<System.String> <tooltipTags>k__BackingField;
    protected System.Boolean m_Dirty;
    protected Game.UI.NameSystem m_NameSystem;
    protected Game.Prefabs.PrefabSystem m_PrefabSystem;
    protected Game.EndFrameBarrier m_EndFrameBarrier;
    protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem;

    public Game.GameMode gameMode { get; }
    public System.Boolean visible { get; protected set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    protected System.String group { protected get; }
    protected System.Collections.Generic.List<System.String> tooltipKeys { protected get; protected set; }
    protected System.Collections.Generic.List<System.String> tooltipTags { protected get; protected set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }
    protected System.Boolean Destroyed { protected get; }
    protected System.Boolean OutsideConnection { protected get; }
    protected System.Boolean UnderConstruction { protected get; }
    protected System.Boolean Upgrade { protected get; }

    protected InfoSectionBase();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnPreUpdate();
    protected abstract System.Void OnProcess();
    public abstract System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void PerformUpdate();
    public System.Void RequestUpdate();
    protected abstract System.Void Reset();
    protected System.Boolean TryGetComponentWithUpgrades<T>(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data);
    private System.Boolean Visible();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean <visible>k__BackingField`  

```csharp
private System.Boolean <visible>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <tooltipKeys>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <tooltipKeys>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <tooltipTags>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <tooltipTags>k__BackingField;
```

- `protected System.Boolean m_Dirty`  

```csharp
protected System.Boolean m_Dirty;
```

- `protected Game.UI.NameSystem m_NameSystem`  

```csharp
protected Game.UI.NameSystem m_NameSystem;
```

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
protected Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `protected Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
protected Game.EndFrameBarrier m_EndFrameBarrier;
```

- `protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem`  

```csharp
protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Boolean visible { get; protected set }`  

```csharp
public System.Boolean visible { get; protected set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Collections.Generic.List<System.String> tooltipKeys { protected get; protected set }`  

```csharp
protected System.Collections.Generic.List<System.String> tooltipKeys { protected get; protected set; }
```

- `protected System.Collections.Generic.List<System.String> tooltipTags { protected get; protected set }`  

```csharp
protected System.Collections.Generic.List<System.String> tooltipTags { protected get; protected set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```

- `protected System.Boolean Destroyed { protected get }`  

```csharp
protected System.Boolean Destroyed { protected get; }
```

- `protected System.Boolean OutsideConnection { protected get }`  

```csharp
protected System.Boolean OutsideConnection { protected get; }
```

- `protected System.Boolean UnderConstruction { protected get }`  

```csharp
protected System.Boolean UnderConstruction { protected get; }
```

- `protected System.Boolean Upgrade { protected get }`  

```csharp
protected System.Boolean Upgrade { protected get; }
```


## Constructors

- `protected InfoSectionBase()`  

```csharp
protected InfoSectionBase();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnPreUpdate() : System.Void`  

```csharp
protected virtual System.Void OnPreUpdate();
```

- `protected abstract OnProcess() : System.Void`  

```csharp
protected abstract System.Void OnProcess();
```

- `public abstract OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public abstract System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `public PerformUpdate() : System.Void`  

```csharp
public System.Void PerformUpdate();
```

- `public RequestUpdate() : System.Void`  

```csharp
public System.Void RequestUpdate();
```

- `protected abstract Reset() : System.Void`  

```csharp
protected abstract System.Void Reset();
```

- `protected TryGetComponentWithUpgrades<T>(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data) : System.Boolean`  

```csharp
protected System.Boolean TryGetComponentWithUpgrades<T>(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data);
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


