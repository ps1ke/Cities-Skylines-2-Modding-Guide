# Game.UI.InGame.CargoSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CargoSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <cargo>k__BackingField;
    private System.Int32 <capacity>k__BackingField;
    private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
    private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;

    protected System.String group { protected get; }
    private System.Int32 cargo { private get; private set; }
    private System.Int32 capacity { private get; private set; }
    private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    public CargoSection();

    private System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target);
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

- `private System.Int32 <cargo>k__BackingField`  

```csharp
private System.Int32 <cargo>k__BackingField;
```

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField`  

```csharp
private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
```

- `private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

```csharp
private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 cargo { private get; private set }`  

```csharp
private System.Int32 cargo { private get; private set; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set }`  

```csharp
private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `public CargoSection()`  

```csharp
public CargoSection();
```


## Methods

- `private AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target) : System.Void`  

```csharp
private System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target);
```

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


## Nested types

- `Game.UI.InGame.CargoSection+CargoKey`  

