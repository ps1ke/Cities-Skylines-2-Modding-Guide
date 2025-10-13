# PDX.ModsUI.UITypes.UIStatus

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class UIStatus
{
    public PDX.ModsUI.UITypes.ModsScreen DefaultScreen;
    public System.String LogLevel;
    public System.Boolean IsLoggedIn;
    public System.Boolean IsOnline;
    public System.String Language;
    public System.String Platform;
    public System.String InputMode;
    public System.Boolean HasFailed;
    public System.Int32 ActivePlaysetId;
    public PDX.ModsUI.UITypes.Actions Actions;

    internal static PDX.ModsUI.UITypes.UIStatus Fallback { internal get; }

    public UIStatus();

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

- `public System.String InputMode`  

```csharp
public System.String InputMode;
```

- `public System.Boolean HasFailed`  

```csharp
public System.Boolean HasFailed;
```

- `public System.Int32 ActivePlaysetId`  

```csharp
public System.Int32 ActivePlaysetId;
```

- `public PDX.ModsUI.UITypes.Actions Actions`  

```csharp
public PDX.ModsUI.UITypes.Actions Actions;
```


## Properties

- `internal static PDX.ModsUI.UITypes.UIStatus Fallback { internal get }`  

```csharp
internal static PDX.ModsUI.UITypes.UIStatus Fallback { internal get; }
```


## Constructors

- `public UIStatus()`  

```csharp
public UIStatus();
```


