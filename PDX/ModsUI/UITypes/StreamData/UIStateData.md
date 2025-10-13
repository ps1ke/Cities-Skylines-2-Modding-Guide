# PDX.ModsUI.UITypes.StreamData.UIStateData

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes.StreamData`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class UIStateData
{
    public PDX.ModsUI.UITypes.ModsScreen DefaultScreen;
    public System.String LogLevel;
    public System.Boolean IsLoggedIn;
    public System.Boolean IsOnline;
    public System.String Language;
    public System.String Platform;
    public System.String Environment;
    public System.String InputMode;
    public System.Int32 ScrollSpeedMultiplier;
    public System.Boolean HasFailed;
    public System.Int32 ActivePlaysetId;
    public PDX.ModsUI.UITypes.StreamData.Actions Actions;
    private PDX.ModsUI.UITypes.FeatureFlags <Features>k__BackingField;
    public System.Boolean HasCustomVirtualKeyboard;
    public System.Int64 TotalDiskSpace;
    public System.Int64 FreeDiskSpace;
    public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings;
    public System.Boolean HasOpenStoreFunc;

    public PDX.ModsUI.UITypes.FeatureFlags Features { get; set; }

    public UIStateData();

}
```


## Fields

- `public PDX.ModsUI.UITypes.ModsScreen DefaultScreen`  

```csharp
public PDX.ModsUI.UITypes.ModsScreen DefaultScreen;
```

- `public System.String LogLevel`  

```csharp
public System.String LogLevel;
```

- `public System.Boolean IsLoggedIn`  

```csharp
public System.Boolean IsLoggedIn;
```

- `public System.Boolean IsOnline`  

```csharp
public System.Boolean IsOnline;
```

- `public System.String Language`  

```csharp
public System.String Language;
```

- `public System.String Platform`  

```csharp
public System.String Platform;
```

- `public System.String Environment`  

```csharp
public System.String Environment;
```

- `public System.String InputMode`  

```csharp
public System.String InputMode;
```

- `public System.Int32 ScrollSpeedMultiplier`  

```csharp
public System.Int32 ScrollSpeedMultiplier;
```

- `public System.Boolean HasFailed`  

```csharp
public System.Boolean HasFailed;
```

- `public System.Int32 ActivePlaysetId`  

```csharp
public System.Int32 ActivePlaysetId;
```

- `public PDX.ModsUI.UITypes.StreamData.Actions Actions`  

```csharp
public PDX.ModsUI.UITypes.StreamData.Actions Actions;
```

- `private PDX.ModsUI.UITypes.FeatureFlags <Features>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.FeatureFlags <Features>k__BackingField;
```

- `public System.Boolean HasCustomVirtualKeyboard`  

```csharp
public System.Boolean HasCustomVirtualKeyboard;
```

- `public System.Int64 TotalDiskSpace`  

```csharp
public System.Int64 TotalDiskSpace;
```

- `public System.Int64 FreeDiskSpace`  

```csharp
public System.Int64 FreeDiskSpace;
```

- `public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings`  

```csharp
public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings;
```

- `public System.Boolean HasOpenStoreFunc`  

```csharp
public System.Boolean HasOpenStoreFunc;
```


## Properties

- `public PDX.ModsUI.UITypes.FeatureFlags Features { get; set }`  

```csharp
public PDX.ModsUI.UITypes.FeatureFlags Features { get; set; }
```


## Constructors

- `public UIStateData()`  

```csharp
public UIStateData();
```


