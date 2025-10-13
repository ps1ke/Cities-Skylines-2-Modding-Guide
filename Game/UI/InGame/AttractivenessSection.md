# Game.UI.InGame.AttractivenessSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AttractivenessSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <baseAttractiveness>k__BackingField;
    private System.Single <attractiveness>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_SettingsQuery;

    protected System.String group { protected get; }
    private System.Single baseAttractiveness { private get; private set; }
    private System.Single attractiveness { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set; }

    public AttractivenessSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <baseAttractiveness>k__BackingField`  

```csharp
private System.Single <baseAttractiveness>k__BackingField;
```

- `private System.Single <attractiveness>k__BackingField`  

```csharp
private System.Single <attractiveness>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> <factors>k__BackingField;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single baseAttractiveness { private get; private set }`  

```csharp
private System.Single baseAttractiveness { private get; private set; }
```

- `private System.Single attractiveness { private get; private set }`  

```csharp
private System.Single attractiveness { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.AttractivenessSection+AttractivenessFactor> factors { private get; private set; }
```


## Constructors

- `public AttractivenessSection()`  

```csharp
public AttractivenessSection();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
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

- `Game.UI.InGame.AttractivenessSection+AttractivenessFactor`  

