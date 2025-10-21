# Game.UI.InGame.DescriptionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DescriptionSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private System.String <localeId>k__BackingField;
    private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas;
    private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas;
    private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas;

    protected System.String group { protected get; }
    private System.String localeId { private get; private set; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DescriptionSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private System.String <localeId>k__BackingField`  

```csharp
private System.String <localeId>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas;
```

- `private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas;
```

- `private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.String localeId { private get; private set }`  

```csharp
private System.String localeId { private get; private set; }
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


## Constructors

- `public DescriptionSection()`  

```csharp
public DescriptionSection();
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


