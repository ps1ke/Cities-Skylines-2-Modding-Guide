# Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.Achievements.AchievementTriggerSystem+ProgressBuffer`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UserDataProgressBuffer : Game.Achievements.AchievementTriggerSystem+ProgressBuffer, System.IDisposable
{
    private System.String m_ID;
    private static System.Byte[] sBuffer;

    public UserDataProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type, System.String id);

    public System.Void Dispose();
    private System.Void Store();
    private System.Void Sync();
}
```


## Fields

- `private System.String m_ID`  

```csharp
private System.String m_ID;
```

- `private static System.Byte[] sBuffer`  

```csharp
private static System.Byte[] sBuffer;
```


## Constructors

- `public UserDataProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type, System.String id)`  

```csharp
public UserDataProgressBuffer(Colossal.PSI.Common.AchievementId achievement, System.Int32 incrementStep, Colossal.PSI.Common.IndicateType type, System.String id);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private Store() : System.Void`  

```csharp
private System.Void Store();
```

- `private Sync() : System.Void`  

```csharp
private System.Void Sync();
```


