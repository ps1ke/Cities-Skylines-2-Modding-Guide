# Colossal.PSI.PdxSdk.IPdxModsUI

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IPdxModsUI : System.IDisposable
{
    public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get; }
    public PDX.ModsUI.Services.ILogService logger { get; }
    public System.String locale { get; }

    public abstract PDX.ModsUI.InputMode GetInputMode();
}
```


## Properties

- `public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get }`  

```csharp
public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get; }
```

- `public PDX.ModsUI.Services.ILogService logger { get }`  

```csharp
public PDX.ModsUI.Services.ILogService logger { get; }
```

- `public System.String locale { get }`  

```csharp
public System.String locale { get; }
```


## Methods

- `public abstract GetInputMode() : PDX.ModsUI.InputMode`  

```csharp
public abstract PDX.ModsUI.InputMode GetInputMode();
```


