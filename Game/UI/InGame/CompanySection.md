# Game.UI.InGame.CompanySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity companyEntity;
    private Game.Economy.Resource <input1>k__BackingField;
    private Game.Economy.Resource <input2>k__BackingField;
    private Game.Economy.Resource <output>k__BackingField;
    private Game.Economy.Resource <sells>k__BackingField;
    private Game.Economy.Resource <stores>k__BackingField;
    private Unity.Mathematics.int2 <customers>k__BackingField;
    private System.Single <price>k__BackingField;
    private System.Boolean <isRentable>k__BackingField;

    protected System.String group { protected get; }
    private Game.Economy.Resource input1 { private get; private set; }
    private Game.Economy.Resource input2 { private get; private set; }
    private Game.Economy.Resource output { private get; private set; }
    private Game.Economy.Resource sells { private get; private set; }
    private Game.Economy.Resource stores { private get; private set; }
    private Unity.Mathematics.int2 customers { private get; private set; }
    private System.Single price { private get; private set; }
    private System.Boolean isRentable { private get; private set; }

    public CompanySection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity companyEntity`  

```csharp
private Unity.Entities.Entity companyEntity;
```

- `private Game.Economy.Resource <input1>k__BackingField`  

```csharp
private Game.Economy.Resource <input1>k__BackingField;
```

- `private Game.Economy.Resource <input2>k__BackingField`  

```csharp
private Game.Economy.Resource <input2>k__BackingField;
```

- `private Game.Economy.Resource <output>k__BackingField`  

```csharp
private Game.Economy.Resource <output>k__BackingField;
```

- `private Game.Economy.Resource <sells>k__BackingField`  

```csharp
private Game.Economy.Resource <sells>k__BackingField;
```

- `private Game.Economy.Resource <stores>k__BackingField`  

```csharp
private Game.Economy.Resource <stores>k__BackingField;
```

- `private Unity.Mathematics.int2 <customers>k__BackingField`  

```csharp
private Unity.Mathematics.int2 <customers>k__BackingField;
```

- `private System.Single <price>k__BackingField`  

```csharp
private System.Single <price>k__BackingField;
```

- `private System.Boolean <isRentable>k__BackingField`  

```csharp
private System.Boolean <isRentable>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.Economy.Resource input1 { private get; private set }`  

```csharp
private Game.Economy.Resource input1 { private get; private set; }
```

- `private Game.Economy.Resource input2 { private get; private set }`  

```csharp
private Game.Economy.Resource input2 { private get; private set; }
```

- `private Game.Economy.Resource output { private get; private set }`  

```csharp
private Game.Economy.Resource output { private get; private set; }
```

- `private Game.Economy.Resource sells { private get; private set }`  

```csharp
private Game.Economy.Resource sells { private get; private set; }
```

- `private Game.Economy.Resource stores { private get; private set }`  

```csharp
private Game.Economy.Resource stores { private get; private set; }
```

- `private Unity.Mathematics.int2 customers { private get; private set }`  

```csharp
private Unity.Mathematics.int2 customers { private get; private set; }
```

- `private System.Single price { private get; private set }`  

```csharp
private System.Single price { private get; private set; }
```

- `private System.Boolean isRentable { private get; private set }`  

```csharp
private System.Boolean isRentable { private get; private set; }
```


## Constructors

- `public CompanySection()`  

```csharp
public CompanySection();
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

- `Game.UI.InGame.CompanySection+ExtractedKey`  

