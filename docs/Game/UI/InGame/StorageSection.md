# Game.UI.InGame.StorageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity m_CompanyEntity;
    private System.Int32 <stored>k__BackingField;
    private System.Int32 <capacity>k__BackingField;
    private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField;
    private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
    private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;

    protected System.String group { protected get; }
    private System.Int32 stored { private get; private set; }
    private System.Int32 capacity { private get; private set; }
    private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set; }
    private Game.UI.InGame.UIResource+StorageType storageType { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }

    public StorageSection();

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

- `private Unity.Entities.Entity m_CompanyEntity`  

```csharp
private Unity.Entities.Entity m_CompanyEntity;
```

- `private System.Int32 <stored>k__BackingField`  

```csharp
private System.Int32 <stored>k__BackingField;
```

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField`  

```csharp
private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField;
```

- `private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField`  

```csharp
private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField;
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

- `private System.Int32 stored { private get; private set }`  

```csharp
private System.Int32 stored { private get; private set; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set }`  

```csharp
private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set; }
```

- `private Game.UI.InGame.UIResource+StorageType storageType { private get; private set }`  

```csharp
private Game.UI.InGame.UIResource+StorageType storageType { private get; private set; }
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


## Constructors

- `public StorageSection()`  

```csharp
public StorageSection();
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


## Nested types

- `Game.UI.InGame.StorageSection+StorageStatus`  

