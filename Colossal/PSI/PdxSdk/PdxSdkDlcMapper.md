# Colossal.PSI.PdxSdk.PdxSdkDlcMapper

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.DlcId, System.String[]>`  

## Code

```csharp
public abstract class PdxSdkDlcMapper : Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.DlcId, System.String[]>
{
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String[]> m_Mapping;

    public System.Int32 count { get; }

    protected PdxSdkDlcMapper();

    public System.Boolean Lookup(Colossal.PSI.Common.DlcId dlcId, System.String[]& items);
    protected System.Void Map(Colossal.PSI.Common.DlcId dlcId, System.String[] items);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String[]> m_Mapping`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String[]> m_Mapping;
```


## Properties

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `protected PdxSdkDlcMapper()`  

```csharp
protected PdxSdkDlcMapper();
```


## Methods

- `public Lookup(Colossal.PSI.Common.DlcId dlcId, System.String[]& items) : System.Boolean`  

```csharp
public System.Boolean Lookup(Colossal.PSI.Common.DlcId dlcId, System.String[]& items);
```

- `protected Map(Colossal.PSI.Common.DlcId dlcId, System.String[] items) : System.Void`  

```csharp
protected System.Void Map(Colossal.PSI.Common.DlcId dlcId, System.String[] items);
```


