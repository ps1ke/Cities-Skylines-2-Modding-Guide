# Game.UI.InGame.DistrictsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DistrictsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_DistrictQuery;
    private Unity.Entities.EntityQuery m_DistrictPrefabQuery;
    private Unity.Entities.EntityQuery m_DistrictModifiedQuery;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField;
    private System.Boolean <districtMissing>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set; }
    private System.Boolean districtMissing { private get; private set; }

    public DistrictsSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnPreUpdate();
    protected virtual System.Void OnProcess();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void RemoveServiceDistrict(Unity.Entities.Entity district);
    protected virtual System.Void Reset();
    private System.Void ToggleDistrictTool();
    private System.Void ToggleSelectionTool();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictModifiedQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField;
```

- `private System.Boolean <districtMissing>k__BackingField`  

```csharp
private System.Boolean <districtMissing>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set; }
```

- `private System.Boolean districtMissing { private get; private set }`  

```csharp
private System.Boolean districtMissing { private get; private set; }
```


## Constructors

- `public DistrictsSection()`  

```csharp
public DistrictsSection();
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

- `protected virtual OnPreUpdate() : System.Void`  

```csharp
protected virtual System.Void OnPreUpdate();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
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

- `public RemoveServiceDistrict(Unity.Entities.Entity district) : System.Void`  

```csharp
public System.Void RemoveServiceDistrict(Unity.Entities.Entity district);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private ToggleDistrictTool() : System.Void`  

```csharp
private System.Void ToggleDistrictTool();
```

- `private ToggleSelectionTool() : System.Void`  

```csharp
private System.Void ToggleSelectionTool();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


