# Colossal.PSI.Common.AchievementUpdatedEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public AchievementUpdatedEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.Common.IAchievementsSupport psi, Colossal.PSI.Common.AchievementId achievementId) : System.Void`  

