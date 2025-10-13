# Game.Assets.MapInfo

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Game.Assets.IContentPrerequisite`, `System.IComparable<Game.Assets.MapInfo>`  

## Code

```csharp
public class MapInfo : Colossal.UI.Binding.IJsonWritable, Game.Assets.IContentPrerequisite, System.IComparable<Game.Assets.MapInfo>
{
    private System.String <id>k__BackingField;
    private System.String <displayName>k__BackingField;
    private Colossal.IO.AssetDatabase.TextureAsset <thumbnail>k__BackingField;
    private Colossal.IO.AssetDatabase.TextureAsset <preview>k__BackingField;
    private System.String <theme>k__BackingField;
    private Colossal.Mathematics.Bounds1 <temperatureRange>k__BackingField;
    private System.Single <cloudiness>k__BackingField;
    private System.Single <precipitation>k__BackingField;
    private System.Single <latitude>k__BackingField;
    private System.Single <longitude>k__BackingField;
    private System.Single <buildableLand>k__BackingField;
    private System.Single <area>k__BackingField;
    private System.Single <surfaceWaterAvailability>k__BackingField;
    private System.Single <groundWaterAvailability>k__BackingField;
    private Game.UI.MapMetadataSystem+Resources <resources>k__BackingField;
    private Game.UI.MapMetadataSystem+Connections <connections>k__BackingField;
    private System.String[] <contentPrerequisites>k__BackingField;
    private System.Boolean <nameAsCityName>k__BackingField;
    private System.Int32 <startingYear>k__BackingField;
    private Colossal.IO.AssetDatabase.MapData <mapData>k__BackingField;
    private Game.Assets.MapMetadata <metaData>k__BackingField;
    private System.Guid <sessionGuid>k__BackingField;
    private Colossal.IO.AssetDatabase.LocaleAsset[] <localeAssets>k__BackingField;
    private Colossal.IO.AssetDatabase.PrefabAsset <climate>k__BackingField;
    private System.Boolean <isReadonly>k__BackingField;
    private System.String <cloudTarget>k__BackingField;
    private System.Boolean <locked>k__BackingField;

    public System.String id { get; set; }
    public System.String displayName { get; set; }
    public Colossal.IO.AssetDatabase.TextureAsset thumbnail { get; set; }
    public Colossal.IO.AssetDatabase.TextureAsset preview { get; set; }
    public System.String theme { get; set; }
    public Colossal.Mathematics.Bounds1 temperatureRange { get; set; }
    public System.Single cloudiness { get; set; }
    public System.Single precipitation { get; set; }
    public System.Single latitude { get; set; }
    public System.Single longitude { get; set; }
    public System.Single buildableLand { get; set; }
    public System.Single area { get; set; }
    public System.Single surfaceWaterAvailability { get; set; }
    public System.Single groundWaterAvailability { get; set; }
    public Game.UI.MapMetadataSystem+Resources resources { get; set; }
    public Game.UI.MapMetadataSystem+Connections connections { get; set; }
    public System.String[] contentPrerequisites { get; set; }
    public System.Boolean nameAsCityName { get; set; }
    public System.Int32 startingYear { get; set; }
    public Colossal.IO.AssetDatabase.MapData mapData { get; set; }
    public Game.Assets.MapMetadata metaData { get; set; }
    public System.Guid sessionGuid { get; set; }
    public Colossal.IO.AssetDatabase.LocaleAsset[] localeAssets { get; set; }
    public Colossal.IO.AssetDatabase.PrefabAsset climate { get; set; }
    public System.Boolean isReadonly { get; set; }
    public System.String cloudTarget { get; set; }
    public System.Boolean locked { get; set; }

    public MapInfo();

    public System.Int32 CompareTo(Game.Assets.MapInfo other);
    public Game.Assets.MapInfo Copy();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.String <displayName>k__BackingField`  

```csharp
private System.String <displayName>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.TextureAsset <thumbnail>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.TextureAsset <thumbnail>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.TextureAsset <preview>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.TextureAsset <preview>k__BackingField;
```

- `private System.String <theme>k__BackingField`  

```csharp
private System.String <theme>k__BackingField;
```

- `private Colossal.Mathematics.Bounds1 <temperatureRange>k__BackingField`  

```csharp
private Colossal.Mathematics.Bounds1 <temperatureRange>k__BackingField;
```

- `private System.Single <cloudiness>k__BackingField`  

```csharp
private System.Single <cloudiness>k__BackingField;
```

- `private System.Single <precipitation>k__BackingField`  

```csharp
private System.Single <precipitation>k__BackingField;
```

- `private System.Single <latitude>k__BackingField`  

```csharp
private System.Single <latitude>k__BackingField;
```

- `private System.Single <longitude>k__BackingField`  

```csharp
private System.Single <longitude>k__BackingField;
```

- `private System.Single <buildableLand>k__BackingField`  

```csharp
private System.Single <buildableLand>k__BackingField;
```

- `private System.Single <area>k__BackingField`  

```csharp
private System.Single <area>k__BackingField;
```

- `private System.Single <surfaceWaterAvailability>k__BackingField`  

```csharp
private System.Single <surfaceWaterAvailability>k__BackingField;
```

- `private System.Single <groundWaterAvailability>k__BackingField`  

```csharp
private System.Single <groundWaterAvailability>k__BackingField;
```

- `private Game.UI.MapMetadataSystem+Resources <resources>k__BackingField`  

```csharp
private Game.UI.MapMetadataSystem+Resources <resources>k__BackingField;
```

- `private Game.UI.MapMetadataSystem+Connections <connections>k__BackingField`  

```csharp
private Game.UI.MapMetadataSystem+Connections <connections>k__BackingField;
```

- `private System.String[] <contentPrerequisites>k__BackingField`  

```csharp
private System.String[] <contentPrerequisites>k__BackingField;
```

- `private System.Boolean <nameAsCityName>k__BackingField`  

```csharp
private System.Boolean <nameAsCityName>k__BackingField;
```

- `private System.Int32 <startingYear>k__BackingField`  

```csharp
private System.Int32 <startingYear>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.MapData <mapData>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.MapData <mapData>k__BackingField;
```

- `private Game.Assets.MapMetadata <metaData>k__BackingField`  

```csharp
private Game.Assets.MapMetadata <metaData>k__BackingField;
```

- `private System.Guid <sessionGuid>k__BackingField`  

```csharp
private System.Guid <sessionGuid>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.LocaleAsset[] <localeAssets>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.LocaleAsset[] <localeAssets>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.PrefabAsset <climate>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.PrefabAsset <climate>k__BackingField;
```

- `private System.Boolean <isReadonly>k__BackingField`  

```csharp
private System.Boolean <isReadonly>k__BackingField;
```

- `private System.String <cloudTarget>k__BackingField`  

```csharp
private System.String <cloudTarget>k__BackingField;
```

- `private System.Boolean <locked>k__BackingField`  

```csharp
private System.Boolean <locked>k__BackingField;
```


## Properties

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.String displayName { get; set }`  

```csharp
public System.String displayName { get; set; }
```

- `public Colossal.IO.AssetDatabase.TextureAsset thumbnail { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.TextureAsset thumbnail { get; set; }
```

- `public Colossal.IO.AssetDatabase.TextureAsset preview { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.TextureAsset preview { get; set; }
```

- `public System.String theme { get; set }`  

```csharp
public System.String theme { get; set; }
```

- `public Colossal.Mathematics.Bounds1 temperatureRange { get; set }`  

```csharp
public Colossal.Mathematics.Bounds1 temperatureRange { get; set; }
```

- `public System.Single cloudiness { get; set }`  

```csharp
public System.Single cloudiness { get; set; }
```

- `public System.Single precipitation { get; set }`  

```csharp
public System.Single precipitation { get; set; }
```

- `public System.Single latitude { get; set }`  

```csharp
public System.Single latitude { get; set; }
```

- `public System.Single longitude { get; set }`  

```csharp
public System.Single longitude { get; set; }
```

- `public System.Single buildableLand { get; set }`  

```csharp
public System.Single buildableLand { get; set; }
```

- `public System.Single area { get; set }`  

```csharp
public System.Single area { get; set; }
```

- `public System.Single surfaceWaterAvailability { get; set }`  

```csharp
public System.Single surfaceWaterAvailability { get; set; }
```

- `public System.Single groundWaterAvailability { get; set }`  

```csharp
public System.Single groundWaterAvailability { get; set; }
```

- `public Game.UI.MapMetadataSystem+Resources resources { get; set }`  

```csharp
public Game.UI.MapMetadataSystem+Resources resources { get; set; }
```

- `public Game.UI.MapMetadataSystem+Connections connections { get; set }`  

```csharp
public Game.UI.MapMetadataSystem+Connections connections { get; set; }
```

- `public System.String[] contentPrerequisites { get; set }`  

```csharp
public System.String[] contentPrerequisites { get; set; }
```

- `public System.Boolean nameAsCityName { get; set }`  

```csharp
public System.Boolean nameAsCityName { get; set; }
```

- `public System.Int32 startingYear { get; set }`  

```csharp
public System.Int32 startingYear { get; set; }
```

- `public Colossal.IO.AssetDatabase.MapData mapData { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.MapData mapData { get; set; }
```

- `public Game.Assets.MapMetadata metaData { get; set }`  

```csharp
public Game.Assets.MapMetadata metaData { get; set; }
```

- `public System.Guid sessionGuid { get; set }`  

```csharp
public System.Guid sessionGuid { get; set; }
```

- `public Colossal.IO.AssetDatabase.LocaleAsset[] localeAssets { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.LocaleAsset[] localeAssets { get; set; }
```

- `public Colossal.IO.AssetDatabase.PrefabAsset climate { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.PrefabAsset climate { get; set; }
```

- `public System.Boolean isReadonly { get; set }`  

```csharp
public System.Boolean isReadonly { get; set; }
```

- `public System.String cloudTarget { get; set }`  

```csharp
public System.String cloudTarget { get; set; }
```

- `public System.Boolean locked { get; set }`  

```csharp
public System.Boolean locked { get; set; }
```


## Constructors

- `public MapInfo()`  

```csharp
public MapInfo();
```


## Methods

- `public CompareTo(Game.Assets.MapInfo other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Assets.MapInfo other);
```

- `public Copy() : Game.Assets.MapInfo`  

```csharp
public Game.Assets.MapInfo Copy();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


