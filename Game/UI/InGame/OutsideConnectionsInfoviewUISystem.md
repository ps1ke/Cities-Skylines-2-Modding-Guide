# Game.UI.InGame.OutsideConnectionsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class OutsideConnectionsInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ResourceQuery;
    private Colossal.UI.Binding.RawValueBinding m_TopImportNames;
    private Colossal.UI.Binding.RawValueBinding m_TopExportNames;
    private Colossal.UI.Binding.RawValueBinding m_TopImportColors;
    private Colossal.UI.Binding.RawValueBinding m_TopExportColors;
    private Colossal.UI.Binding.RawValueBinding m_TopImportData;
    private Colossal.UI.Binding.RawValueBinding m_TopExportData;
    private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports;
    private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public OutsideConnectionsInfoviewUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateCache();
    private System.Void UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateExportData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ResourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportNames`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportNames;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportNames`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportNames;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportColors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportColors;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportColors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportColors;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopImportData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopImportData;
```

- `private Colossal.UI.Binding.RawValueBinding m_TopExportData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TopExportData;
```

- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports;
```

- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public OutsideConnectionsInfoviewUISystem()`  

```csharp
public OutsideConnectionsInfoviewUISystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private UpdateCache() : System.Void`  

```csharp
private System.Void UpdateCache();
```

- `private UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateExportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateExportData(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateImportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateImportData(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder);
```


## Nested types

- `Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource`  

