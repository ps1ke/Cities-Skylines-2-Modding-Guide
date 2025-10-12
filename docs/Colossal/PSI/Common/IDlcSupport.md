# Colossal.PSI.Common.IDlcSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Properties

- `public System.Int32 dlcCount { get }`  

## Methods

- `public abstract EnumerateDLCs() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  
- `public abstract GetDlcName(Colossal.PSI.Common.DlcId dlc) : System.String`  
- `public abstract GetDlcPaths() : System.Collections.Generic.List<System.ValueTuple<System.String, System.String>>`  
- `public virtual IsDlcOwned(Colossal.PSI.Common.IDlc dlc) : System.Boolean`  
- `public abstract IsDlcOwned(Colossal.PSI.Common.DlcId dlc) : System.Boolean`  

