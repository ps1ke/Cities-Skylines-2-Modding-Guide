# Colossal.PSI.Common.DevelopmentAchievementsManager+DevelopmentAchievement

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievement`  

## Code

```csharp
public class DevelopmentAchievement : Colossal.PSI.Common.IAchievement
{
    private System.Boolean <achieved>k__BackingField;
    private System.Int32 <progress>k__BackingField;
    private readonly System.String <backendId>k__BackingField;
    private readonly System.String <internalName>k__BackingField;
    private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField;
    private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField;
    public readonly System.String statName;
    public readonly System.Int32 unlocksAt;

    public System.Boolean achieved { get; internal set; }
    public System.Int32 progress { get; internal set; }
    public System.String backendId { get; }
    public System.String internalName { get; }
    public Colossal.PSI.Common.AchievementId id { get; }
    public Colossal.PSI.Common.DlcId dlcId { get; }
    public System.Int32 maxProgress { get; }
    public System.Boolean isIncremental { get; }

    public DevelopmentAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId);

    public virtual System.String ToString();
}
```


## Fields

- `private System.Boolean <achieved>k__BackingField`  

```csharp
private System.Boolean <achieved>k__BackingField;
```

- `private System.Int32 <progress>k__BackingField`  

```csharp
private System.Int32 <progress>k__BackingField;
```

- `private readonly System.String <backendId>k__BackingField`  

```csharp
private readonly System.String <backendId>k__BackingField;
```

- `private readonly System.String <internalName>k__BackingField`  

```csharp
private readonly System.String <internalName>k__BackingField;
```

- `private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField`  

```csharp
private readonly Colossal.PSI.Common.AchievementId <id>k__BackingField;
```

- `private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField`  

```csharp
private readonly Colossal.PSI.Common.DlcId <dlcId>k__BackingField;
```

- `public readonly System.String statName`  

```csharp
public readonly System.String statName;
```

- `public readonly System.Int32 unlocksAt`  

```csharp
public readonly System.Int32 unlocksAt;
```


## Properties

- `public System.Boolean achieved { get; internal set }`  

```csharp
public System.Boolean achieved { get; internal set; }
```

- `public System.Int32 progress { get; internal set }`  

```csharp
public System.Int32 progress { get; internal set; }
```

- `public System.String backendId { get }`  

```csharp
public System.String backendId { get; }
```

- `public System.String internalName { get }`  

```csharp
public System.String internalName { get; }
```

- `public Colossal.PSI.Common.AchievementId id { get }`  

```csharp
public Colossal.PSI.Common.AchievementId id { get; }
```

- `public Colossal.PSI.Common.DlcId dlcId { get }`  

```csharp
public Colossal.PSI.Common.DlcId dlcId { get; }
```

- `public System.Int32 maxProgress { get }`  

```csharp
public System.Int32 maxProgress { get; }
```

- `public System.Boolean isIncremental { get }`  

```csharp
public System.Boolean isIncremental { get; }
```


## Constructors

- `public DevelopmentAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId)`  

```csharp
public DevelopmentAchievement(Colossal.PSI.Common.AchievementId id, System.String internalName, System.Int32 unlocksAt, Colossal.PSI.Common.DlcId dlcId);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


