# Colossal.PSI.MicrosoftGdk.GdkPlatform+GdkAchievement

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievement`  

## Code

```csharp
public class GdkAchievement : Colossal.PSI.Common.IAchievement
{
    private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField;
    private readonly System.String <internalName>k__BackingField;
    private readonly System.String <backendId>k__BackingField;
    private System.Int32 <progress>k__BackingField;
    private System.Int32 <backendPercentageProgress>k__BackingField;
    private System.Boolean <achieved>k__BackingField;
    public readonly System.Int32 unlocksAt;
    private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField;

    public Colossal.PSI.Common.AchievementId id { get; }
    public System.String internalName { get; }
    public System.String backendId { get; }
    public System.Int32 progress { get; set; }
    public System.Int32 backendPercentageProgress { get; set; }
    public System.Boolean achieved { get; set; }
    public System.Int32 maxProgress { get; }
    public System.Boolean isIncremental { get; }
    public Colossal.PSI.Common.DlcId dlcId { get; }

    public GdkAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 backendId, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId);

    public virtual System.String ToString();
}
```


## Fields

- `private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField`  

```csharp
private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField;
```

- `private readonly System.String <internalName>k__BackingField`  

```csharp
private readonly System.String <internalName>k__BackingField;
```

- `private readonly System.String <backendId>k__BackingField`  

```csharp
private readonly System.String <backendId>k__BackingField;
```

- `private System.Int32 <progress>k__BackingField`  

```csharp
private System.Int32 <progress>k__BackingField;
```

- `private System.Int32 <backendPercentageProgress>k__BackingField`  

```csharp
private System.Int32 <backendPercentageProgress>k__BackingField;
```

- `private System.Boolean <achieved>k__BackingField`  

```csharp
private System.Boolean <achieved>k__BackingField;
```

- `public readonly System.Int32 unlocksAt`  

```csharp
public readonly System.Int32 unlocksAt;
```

- `private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField`  

```csharp
private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField;
```


## Properties

- `public Colossal.PSI.Common.AchievementId id { get }`  

```csharp
public Colossal.PSI.Common.AchievementId id { get; }
```

- `public System.String internalName { get }`  

```csharp
public System.String internalName { get; }
```

- `public System.String backendId { get }`  

```csharp
public System.String backendId { get; }
```

- `public System.Int32 progress { get; set }`  

```csharp
public System.Int32 progress { get; set; }
```

- `public System.Int32 backendPercentageProgress { get; set }`  

```csharp
public System.Int32 backendPercentageProgress { get; set; }
```

- `public System.Boolean achieved { get; set }`  

```csharp
public System.Boolean achieved { get; set; }
```

- `public System.Int32 maxProgress { get }`  

```csharp
public System.Int32 maxProgress { get; }
```

- `public System.Boolean isIncremental { get }`  

```csharp
public System.Boolean isIncremental { get; }
```

- `public Colossal.PSI.Common.DlcId dlcId { get }`  

```csharp
public Colossal.PSI.Common.DlcId dlcId { get; }
```


## Constructors

- `public GdkAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 backendId, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId)`  

```csharp
public GdkAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 backendId, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


