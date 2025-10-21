# Game.UI.InGame.ColorSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ColorSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private UnityEngine.Color32 <color>k__BackingField;
    private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;

    protected System.String group { protected get; }
    private UnityEngine.Color32 color { private get; private set; }

    public ColorSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    private System.Void OnSetColor(UnityEngine.Color uiColor);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  

```csharp
private UnityEngine.Color32 <color>k__BackingField;
```

- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private UnityEngine.Color32 color { private get; private set }`  

```csharp
private UnityEngine.Color32 color { private get; private set; }
```


## Constructors

- `public ColorSection()`  

```csharp
public ColorSection();
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

- `private OnSetColor(UnityEngine.Color uiColor) : System.Void`  

```csharp
private System.Void OnSetColor(UnityEngine.Color uiColor);
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


