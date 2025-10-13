# Game.UI.InGame.MailSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MailSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <sortingRate>k__BackingField;
    private System.Int32 <sortingCapacity>k__BackingField;
    private System.Int32 <localAmount>k__BackingField;
    private System.Int32 <unsortedAmount>k__BackingField;
    private System.Int32 <outgoingAmount>k__BackingField;
    private System.Int32 <storedAmount>k__BackingField;
    private System.Int32 <storageCapacity>k__BackingField;
    private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField;
    private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField;
    private Game.UI.InGame.MailSection+Type <type>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 sortingRate { private get; private set; }
    private System.Int32 sortingCapacity { private get; private set; }
    private System.Int32 localAmount { private get; private set; }
    private System.Int32 unsortedAmount { private get; private set; }
    private System.Int32 outgoingAmount { private get; private set; }
    private System.Int32 storedAmount { private get; private set; }
    private System.Int32 storageCapacity { private get; private set; }
    private Game.UI.InGame.MailSection+MailKey localKey { private get; private set; }
    private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set; }
    private Game.UI.InGame.MailSection+Type type { private get; private set; }

    public MailSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <sortingRate>k__BackingField`  

```csharp
private System.Int32 <sortingRate>k__BackingField;
```

- `private System.Int32 <sortingCapacity>k__BackingField`  

```csharp
private System.Int32 <sortingCapacity>k__BackingField;
```

- `private System.Int32 <localAmount>k__BackingField`  

```csharp
private System.Int32 <localAmount>k__BackingField;
```

- `private System.Int32 <unsortedAmount>k__BackingField`  

```csharp
private System.Int32 <unsortedAmount>k__BackingField;
```

- `private System.Int32 <outgoingAmount>k__BackingField`  

```csharp
private System.Int32 <outgoingAmount>k__BackingField;
```

- `private System.Int32 <storedAmount>k__BackingField`  

```csharp
private System.Int32 <storedAmount>k__BackingField;
```

- `private System.Int32 <storageCapacity>k__BackingField`  

```csharp
private System.Int32 <storageCapacity>k__BackingField;
```

- `private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+MailKey <localKey>k__BackingField;
```

- `private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+MailKey <unsortedKey>k__BackingField;
```

- `private Game.UI.InGame.MailSection+Type <type>k__BackingField`  

```csharp
private Game.UI.InGame.MailSection+Type <type>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 sortingRate { private get; private set }`  

```csharp
private System.Int32 sortingRate { private get; private set; }
```

- `private System.Int32 sortingCapacity { private get; private set }`  

```csharp
private System.Int32 sortingCapacity { private get; private set; }
```

- `private System.Int32 localAmount { private get; private set }`  

```csharp
private System.Int32 localAmount { private get; private set; }
```

- `private System.Int32 unsortedAmount { private get; private set }`  

```csharp
private System.Int32 unsortedAmount { private get; private set; }
```

- `private System.Int32 outgoingAmount { private get; private set }`  

```csharp
private System.Int32 outgoingAmount { private get; private set; }
```

- `private System.Int32 storedAmount { private get; private set }`  

```csharp
private System.Int32 storedAmount { private get; private set; }
```

- `private System.Int32 storageCapacity { private get; private set }`  

```csharp
private System.Int32 storageCapacity { private get; private set; }
```

- `private Game.UI.InGame.MailSection+MailKey localKey { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+MailKey localKey { private get; private set; }
```

- `private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+MailKey unsortedKey { private get; private set; }
```

- `private Game.UI.InGame.MailSection+Type type { private get; private set }`  

```csharp
private Game.UI.InGame.MailSection+Type type { private get; private set; }
```


## Constructors

- `public MailSection()`  

```csharp
public MailSection();
```


## Methods

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

- `Game.UI.InGame.MailSection+MailKey`  
- `Game.UI.InGame.MailSection+Type`  

