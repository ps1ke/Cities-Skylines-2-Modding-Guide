# Game.UI.InGame.LevelSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LevelSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
    private Unity.Entities.EntityQuery m_CityQuery;
    private System.Int32 <level>k__BackingField;
    private System.Int32 <maxLevel>k__BackingField;
    private System.Boolean <isUnderConstruction>k__BackingField;
    private System.Single <progress>k__BackingField;
    private Unity.Entities.Entity <zone>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Result;
    private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Int32 level { private get; private set; }
    private System.Int32 maxLevel { private get; private set; }
    private System.Boolean isUnderConstruction { private get; private set; }
    private System.Single progress { private get; private set; }
    private Unity.Entities.Entity zone { private get; private set; }
    protected System.Boolean displayForUnderConstruction { protected get; }

    public LevelSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_CityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityQuery;
```

- `private System.Int32 <level>k__BackingField`  

```csharp
private System.Int32 <level>k__BackingField;
```

- `private System.Int32 <maxLevel>k__BackingField`  

```csharp
private System.Int32 <maxLevel>k__BackingField;
```

- `private System.Boolean <isUnderConstruction>k__BackingField`  

```csharp
private System.Boolean <isUnderConstruction>k__BackingField;
```

- `private System.Single <progress>k__BackingField`  

```csharp
private System.Single <progress>k__BackingField;
```

- `private Unity.Entities.Entity <zone>k__BackingField`  

```csharp
private Unity.Entities.Entity <zone>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Result`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Result;
```

- `private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 level { private get; private set }`  

```csharp
private System.Int32 level { private get; private set; }
```

- `private System.Int32 maxLevel { private get; private set }`  

```csharp
private System.Int32 maxLevel { private get; private set; }
```

- `private System.Boolean isUnderConstruction { private get; private set }`  

```csharp
private System.Boolean isUnderConstruction { private get; private set; }
```

- `private System.Single progress { private get; private set }`  

```csharp
private System.Single progress { private get; private set; }
```

- `private Unity.Entities.Entity zone { private get; private set }`  

```csharp
private Unity.Entities.Entity zone { private get; private set; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```


## Constructors

- `public LevelSection()`  

```csharp
public LevelSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
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

- `Game.UI.InGame.LevelSection+CalculateMaxLevelJob`  
- `Game.UI.InGame.LevelSection+TypeHandle`  

