# Game.UI.InGame.EfficiencySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EfficiencySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <efficiency>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 efficiency { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set; }

    public EfficiencySection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <efficiency>k__BackingField`  

```csharp
private System.Int32 <efficiency>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> <factors>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 efficiency { private get; private set }`  

```csharp
private System.Int32 efficiency { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.EfficiencySection+EfficiencyFactor> factors { private get; private set; }
```


## Constructors

- `public EfficiencySection()`  

```csharp
public EfficiencySection();
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

- `Game.UI.InGame.EfficiencySection+EfficiencyFactor`  

