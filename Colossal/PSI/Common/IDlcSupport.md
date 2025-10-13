# Colossal.PSI.Common.IDlcSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IDlcSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public System.Int32 dlcCount { get; }

    public abstract System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
    public abstract System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
    public abstract System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
    public virtual System.Boolean IsDlcOwned(Colossal.PSI.Common.IDlc dlc);
    public abstract System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
}
```


## Properties

- `public System.Int32 dlcCount { get }`  

```csharp
public System.Int32 dlcCount { get; }
```


## Methods

- `public abstract EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> EnumerateDLCs();
```

- `public abstract GetDlcName(Colossal.PSI.Common.DlcId dlc) : System.String`  

```csharp
public abstract System.String GetDlcName(Colossal.PSI.Common.DlcId dlc);
```

- `public abstract GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  

```csharp
public abstract System.Collections.Generic.List<System.ValueTuple<System.String, System.String>> GetDlcPaths();
```

- `public virtual IsDlcOwned(Colossal.PSI.Common.IDlc dlc) : System.Boolean`  

```csharp
public virtual System.Boolean IsDlcOwned(Colossal.PSI.Common.IDlc dlc);
```

- `public abstract IsDlcOwned(Colossal.PSI.Common.DlcId dlc) : System.Boolean`  

```csharp
public abstract System.Boolean IsDlcOwned(Colossal.PSI.Common.DlcId dlc);
```


