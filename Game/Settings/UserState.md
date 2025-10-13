# Game.Settings.UserState

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class UserState : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField;
    private Game.Assets.SaveGameMetadata <lastSaveGameMetadata>k__BackingField;
    private System.String <lastCloudTarget>k__BackingField;
    private System.Boolean <leftHandTraffic>k__BackingField;
    private System.Boolean <naturalDisasters>k__BackingField;
    private System.Boolean <unlockAll>k__BackingField;
    private System.Boolean <unlimitedMoney>k__BackingField;
    private System.Boolean <unlockMapTiles>k__BackingField;
    private System.Collections.Generic.List<System.String> <seenWhatsNew>k__BackingField;

    public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set; }
    public Game.Assets.SaveGameMetadata lastSaveGameMetadata { get; set; }
    public System.String lastCloudTarget { get; set; }
    public System.Boolean leftHandTraffic { get; set; }
    public System.Boolean naturalDisasters { get; set; }
    public System.Boolean unlockAll { get; set; }
    public System.Boolean unlimitedMoney { get; set; }
    public System.Boolean unlockMapTiles { get; set; }
    public System.Collections.Generic.List<System.String> seenWhatsNew { get; set; }

    public UserState();

    private System.String GetDefaultCloudTarget();
    public System.Void ResetTutorials();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField;
```

- `private Game.Assets.SaveGameMetadata <lastSaveGameMetadata>k__BackingField`  

```csharp
private Game.Assets.SaveGameMetadata <lastSaveGameMetadata>k__BackingField;
```

- `private System.String <lastCloudTarget>k__BackingField`  

```csharp
private System.String <lastCloudTarget>k__BackingField;
```

- `private System.Boolean <leftHandTraffic>k__BackingField`  

```csharp
private System.Boolean <leftHandTraffic>k__BackingField;
```

- `private System.Boolean <naturalDisasters>k__BackingField`  

```csharp
private System.Boolean <naturalDisasters>k__BackingField;
```

- `private System.Boolean <unlockAll>k__BackingField`  

```csharp
private System.Boolean <unlockAll>k__BackingField;
```

- `private System.Boolean <unlimitedMoney>k__BackingField`  

```csharp
private System.Boolean <unlimitedMoney>k__BackingField;
```

- `private System.Boolean <unlockMapTiles>k__BackingField`  

```csharp
private System.Boolean <unlockMapTiles>k__BackingField;
```

- `private System.Collections.Generic.List<System.String> <seenWhatsNew>k__BackingField`  

```csharp
private System.Collections.Generic.List<System.String> <seenWhatsNew>k__BackingField;
```


## Properties

- `public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set; }
```

- `public Game.Assets.SaveGameMetadata lastSaveGameMetadata { get; set }`  

```csharp
public Game.Assets.SaveGameMetadata lastSaveGameMetadata { get; set; }
```

- `public System.String lastCloudTarget { get; set }`  

```csharp
public System.String lastCloudTarget { get; set; }
```

- `public System.Boolean leftHandTraffic { get; set }`  

```csharp
public System.Boolean leftHandTraffic { get; set; }
```

- `public System.Boolean naturalDisasters { get; set }`  

```csharp
public System.Boolean naturalDisasters { get; set; }
```

- `public System.Boolean unlockAll { get; set }`  

```csharp
public System.Boolean unlockAll { get; set; }
```

- `public System.Boolean unlimitedMoney { get; set }`  

```csharp
public System.Boolean unlimitedMoney { get; set; }
```

- `public System.Boolean unlockMapTiles { get; set }`  

```csharp
public System.Boolean unlockMapTiles { get; set; }
```

- `public System.Collections.Generic.List<System.String> seenWhatsNew { get; set }`  

```csharp
public System.Collections.Generic.List<System.String> seenWhatsNew { get; set; }
```


## Constructors

- `public UserState()`  

```csharp
public UserState()
	{
		SetDefaults();
	}
```


## Methods

- `private GetDefaultCloudTarget() : System.String`  

```csharp
private string GetDefaultCloudTarget()
	{
		return "Local";
	}
```

- `public ResetTutorials() : System.Void`  

```csharp
public void ResetTutorials()
	{
		shownTutorials.Clear();
		ApplyAndSave();
		World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<TutorialSystem>().OnResetTutorials();
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		shownTutorials = new Dictionary<string, bool>();
		lastSaveGameMetadata = null;
		lastCloudTarget = GetDefaultCloudTarget();
		leftHandTraffic = false;
		naturalDisasters = true;
		unlockAll = false;
		unlimitedMoney = false;
		unlockMapTiles = false;
		seenWhatsNew = new List<string>();
	}
```


