# Colossal.PSI.Common.IOverlaySupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IOverlaySupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public System.Boolean isOverlaySupported { get; }

    public abstract System.Void SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset, System.Int32 verticalInset);
    public abstract System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
}
```


## Properties

- `public System.Boolean isOverlaySupported { get }`  

```csharp
public System.Boolean isOverlaySupported { get; }
```


## Methods

- `public abstract SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset = 0, System.Int32 verticalInset = 0) : System.Void`  

```csharp
public abstract System.Void SetNotificationPosition(Colossal.PSI.Common.NotificationPosition position, System.Int32 horizontalInset, System.Int32 verticalInset);
```

- `public abstract ShowOverlay(Colossal.PSI.Common.Page page, System.String extra = null) : System.Void`  

```csharp
public abstract System.Void ShowOverlay(Colossal.PSI.Common.Page page, System.String extra);
```


## Events

- `onOverlayStateChanged` : `Colossal.PSI.Common.OnOverlayStateChanged`  

```csharp
public event Colossal.PSI.Common.OnOverlayStateChanged onOverlayStateChanged;
```


