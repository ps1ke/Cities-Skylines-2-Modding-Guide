# Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SaveGamePreviewSettings
{
    private System.Boolean <stylized>k__BackingField;
    private System.Single <stylizedRadius>k__BackingField;
    private Colossal.IO.AssetDatabase.TextureAsset <overlayImage>k__BackingField;

    public System.Boolean stylized { get; set; }
    public System.Single stylizedRadius { get; set; }
    public Colossal.IO.AssetDatabase.TextureAsset overlayImage { get; set; }

    public SaveGamePreviewSettings();

    public System.Void FromUri(Colossal.UI.UrlQuery query);
    public System.Void SetDefaults();
    public System.String ToUri();
}
```


## Fields

- `private System.Boolean <stylized>k__BackingField`  

```csharp
private System.Boolean <stylized>k__BackingField;
```

- `private System.Single <stylizedRadius>k__BackingField`  

```csharp
private System.Single <stylizedRadius>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.TextureAsset <overlayImage>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.TextureAsset <overlayImage>k__BackingField;
```


## Properties

- `public System.Boolean stylized { get; set }`  

```csharp
public System.Boolean stylized { get; set; }
```

- `public System.Single stylizedRadius { get; set }`  

```csharp
public System.Single stylizedRadius { get; set; }
```

- `public Colossal.IO.AssetDatabase.TextureAsset overlayImage { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.TextureAsset overlayImage { get; set; }
```


## Constructors

- `public SaveGamePreviewSettings()`  

```csharp
public SaveGamePreviewSettings();
```


## Methods

- `public FromUri(Colossal.UI.UrlQuery query) : System.Void`  

```csharp
public System.Void FromUri(Colossal.UI.UrlQuery query);
```

- `public SetDefaults() : System.Void`  

```csharp
public System.Void SetDefaults();
```

- `public ToUri() : System.String`  

```csharp
public System.String ToUri();
```


