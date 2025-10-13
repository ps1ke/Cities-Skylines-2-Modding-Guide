# Colossal.PSI.Common.AchievementUpdatedEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class AchievementUpdatedEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public AchievementUpdatedEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId);
}
```


## Constructors

- `public AchievementUpdatedEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public AchievementUpdatedEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId);
```


