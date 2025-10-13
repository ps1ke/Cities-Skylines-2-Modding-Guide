# Game.UI.InGame.DestroyedBuildingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DestroyedBuildingSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding;
    private Unity.Entities.EntityQuery m_FireStationQuery;
    private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
    private Unity.Entities.Entity <destroyer>k__BackingField;
    private System.Boolean <cleared>k__BackingField;
    private System.Single <progress>k__BackingField;
    private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity destroyer { private get; private set; }
    private System.Boolean cleared { private get; private set; }
    private System.Single progress { private get; private set; }
    private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DestroyedBuildingSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    private System.Void OnToggleRebuild();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean VehicleAtTarget(Unity.Entities.Entity vehicle);
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding;
```

- `private Unity.Entities.EntityQuery m_FireStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
```

- `private Unity.Entities.Entity <destroyer>k__BackingField`  

```csharp
private Unity.Entities.Entity <destroyer>k__BackingField;
```

- `private System.Boolean <cleared>k__BackingField`  

```csharp
private System.Boolean <cleared>k__BackingField;
```

- `private System.Single <progress>k__BackingField`  

```csharp
private System.Single <progress>k__BackingField;
```

- `private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField`  

```csharp
private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity destroyer { private get; private set }`  

```csharp
private Unity.Entities.Entity destroyer { private get; private set; }
```

- `private System.Boolean cleared { private get; private set }`  

```csharp
private System.Boolean cleared { private get; private set; }
```

- `private System.Single progress { private get; private set }`  

```csharp
private System.Single progress { private get; private set; }
```

- `private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set }`  

```csharp
private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public DestroyedBuildingSection()`  

```csharp
public DestroyedBuildingSection();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnToggleRebuild() : System.Void`  

```csharp
private System.Void OnToggleRebuild();
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
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

- `private VehicleAtTarget(Unity.Entities.Entity vehicle) : System.Boolean`  

```csharp
private System.Boolean VehicleAtTarget(Unity.Entities.Entity vehicle);
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


## Nested types

- `Game.UI.InGame.DestroyedBuildingSection+Status`  

