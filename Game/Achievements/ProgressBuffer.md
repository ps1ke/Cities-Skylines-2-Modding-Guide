# Game.Achievements.AchievementTriggerSystem+ProgressBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ProgressBuffer
{
    private Colossal.PSI.Common.AchievementId m_Achievement;
    private System.Int32 m_IncrementStep;
    private Colossal.PSI.Common.IndicateType m_Type;
    public System.Int32 m_Progress;

    public ProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type);

    public System.Void AddProgress(System.Int32 progress);
}
```


## Fields

- `private Colossal.PSI.Common.AchievementId m_Achievement`  

```csharp
private Colossal.PSI.Common.AchievementId m_Achievement;
```

- `private System.Int32 m_IncrementStep`  

```csharp
private System.Int32 m_IncrementStep;
```

- `private Colossal.PSI.Common.IndicateType m_Type`  

```csharp
private Colossal.PSI.Common.IndicateType m_Type;
```

- `public System.Int32 m_Progress`  

```csharp
public System.Int32 m_Progress;
```


## Constructors

- `public ProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type)`  

```csharp
public ProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type);
```


## Methods

- `public AddProgress(System.Int32 progress) : System.Void`  

```csharp
public System.Void AddProgress(System.Int32 progress);
```


