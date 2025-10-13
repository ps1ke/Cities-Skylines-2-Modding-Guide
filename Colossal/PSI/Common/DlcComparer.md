# Colossal.PSI.Common.DlcComparer

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEqualityComparer<Colossal.PSI.Common.IDlc>`, `System.Collections.Generic.IComparer<Colossal.PSI.Common.IDlc>`  

## Code

```csharp
public class DlcComparer : System.Collections.Generic.IEqualityComparer<Colossal.PSI.Common.IDlc>, System.Collections.Generic.IComparer<Colossal.PSI.Common.IDlc>
{
    public static readonly Colossal.PSI.Common.DlcComparer Instance;

    public DlcComparer();

    public System.Int32 Compare(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y);
    public System.Boolean Equals(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y);
    public System.Int32 GetHashCode(Colossal.PSI.Common.IDlc obj);
}
```


## Fields

- `public static readonly Colossal.PSI.Common.DlcComparer Instance`  

```csharp
public static readonly Colossal.PSI.Common.DlcComparer Instance;
```


## Constructors

- `public DlcComparer()`  

```csharp
public DlcComparer();
```


## Methods

- `public Compare(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y) : System.Int32`  

```csharp
public System.Int32 Compare(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y);
```

- `public Equals(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.PSI.Common.IDlc x, Colossal.PSI.Common.IDlc y);
```

- `public GetHashCode(Colossal.PSI.Common.IDlc obj) : System.Int32`  

```csharp
public System.Int32 GetHashCode(Colossal.PSI.Common.IDlc obj);
```


