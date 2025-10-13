# Game.UI.InGame.StatusSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StatusSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField;
    private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField;
    private Game.UI.ImageSystem m_ImageSystem;
    private System.Boolean m_Dead;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set; }
    private Game.UI.InGame.CitizenHappiness happiness { private get; private set; }

    public StatusSection();

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

- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField;
```

- `private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private System.Boolean m_Dead`  

```csharp
private System.Boolean m_Dead;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set; }
```

- `private Game.UI.InGame.CitizenHappiness happiness { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenHappiness happiness { private get; private set; }
```


## Constructors

- `public StatusSection()`  

```csharp
public StatusSection();
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


