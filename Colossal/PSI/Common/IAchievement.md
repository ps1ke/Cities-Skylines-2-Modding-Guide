# Colossal.PSI.Common.IAchievement

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IAchievement
{
    public Colossal.PSI.Common.AchievementId id { get; }
    public System.String internalName { get; }
    public System.String backendId { get; }
    public System.Int32 progress { get; }
    public System.Boolean achieved { get; }
    public System.Int32 maxProgress { get; }
    public System.Boolean isIncremental { get; }
    public Colossal.PSI.Common.DlcId dlcId { get; }

}
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

- `public System.Int32 progress { get }`  

```csharp
public System.Int32 progress { get; }
```

- `public System.Boolean achieved { get }`  

```csharp
public System.Boolean achieved { get; }
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


