# Game.Prefabs.Modes.GameModeInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class GameModeInfo : Colossal.UI.Binding.IJsonWritable
{
    private System.String <id>k__BackingField;
    private System.String <image>k__BackingField;
    private System.String <decorateImage>k__BackingField;
    private Game.UI.Localization.LocalizedString[] <descriptions>k__BackingField;

    public System.String id { get; set; }
    public System.String image { get; set; }
    public System.String decorateImage { get; set; }
    public Game.UI.Localization.LocalizedString[] descriptions { get; set; }

    public GameModeInfo();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.String <image>k__BackingField`  

```csharp
private System.String <image>k__BackingField;
```

- `private System.String <decorateImage>k__BackingField`  

```csharp
private System.String <decorateImage>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString[] <descriptions>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString[] <descriptions>k__BackingField;
```


## Properties

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.String image { get; set }`  

```csharp
public System.String image { get; set; }
```

- `public System.String decorateImage { get; set }`  

```csharp
public System.String decorateImage { get; set; }
```

- `public Game.UI.Localization.LocalizedString[] descriptions { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString[] descriptions { get; set; }
```


## Constructors

- `public GameModeInfo()`  

```csharp
public GameModeInfo();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(GameModeInfo).FullName);
		writer.PropertyName("id");
		writer.Write(id);
		writer.PropertyName("image");
		writer.Write(image);
		writer.PropertyName("decorateImage");
		writer.Write(decorateImage);
		writer.PropertyName("descriptions");
		writer.Write((IList<LocalizedString>)descriptions);
		writer.TypeEnd();
	}
```


