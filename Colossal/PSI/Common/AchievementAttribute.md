# Colossal.PSI.Common.AchievementAttribute

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class AchievementAttribute : System.Attribute
{
    public Colossal.PSI.Common.DlcId dlcId;
    public System.String internalName;
    public readonly System.Int32 id;
    public readonly System.Int32 unlocksAt;

    public System.Boolean isDevelopment { get; }

    public AchievementAttribute(System.Int32 id, System.Int32 unlocksAt);
    public AchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt);

}
```


## Fields

- `public Colossal.PSI.Common.DlcId dlcId`  

```csharp
public Colossal.PSI.Common.DlcId dlcId;
```

- `public System.String internalName`  

```csharp
public System.String internalName;
```

- `public readonly System.Int32 id`  

```csharp
public readonly System.Int32 id;
```

- `public readonly System.Int32 unlocksAt`  

```csharp
public readonly System.Int32 unlocksAt;
```


## Properties

- `public System.Boolean isDevelopment { get }`  

```csharp
public System.Boolean isDevelopment { get; }
```


## Constructors

- `public AchievementAttribute(System.Int32 id, System.Int32 unlocksAt = -1)`  

```csharp
public AchievementAttribute(System.Int32 id, System.Int32 unlocksAt);
```

- `public AchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt = -1)`  

```csharp
public AchievementAttribute(System.Int32 id, System.Int32 dlcId, System.Int32 unlocksAt);
```


