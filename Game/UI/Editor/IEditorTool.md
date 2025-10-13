# Game.UI.Editor.IEditorTool

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** interface abstract public  

**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface IEditorTool : Colossal.UI.Binding.IJsonWritable
{
    public System.String id { get; }
    public System.String icon { get; }
    public System.String uiTag { get; }
    public System.Boolean disabled { get; }
    public System.String shortcut { get; }
    public System.Boolean active { get; set; }

    private System.Void Colossal.UI.Binding.IJsonWritable.Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Properties

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.String uiTag { get }`  

```csharp
public System.String uiTag { get; }
```

- `public System.Boolean disabled { get }`  

```csharp
public System.Boolean disabled { get; }
```

- `public System.String shortcut { get }`  

```csharp
public System.String shortcut { get; }
```

- `public System.Boolean active { get; set }`  

```csharp
public System.Boolean active { get; set; }
```


## Methods

- `private Colossal.UI.Binding.IJsonWritable.Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void Colossal.UI.Binding.IJsonWritable.Write(Colossal.UI.Binding.IJsonWriter writer);
```


