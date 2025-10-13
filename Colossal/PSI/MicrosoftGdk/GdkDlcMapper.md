# Colossal.PSI.MicrosoftGdk.GdkDlcMapper

**Assembly:** `Colossal.PSI.MicrosoftGdk`  
**Namespace:** `Colossal.PSI.MicrosoftGdk`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.DlcId, System.String>`  

## Code

```csharp
public abstract class GdkDlcMapper : Colossal.PSI.Common.IAchievementsMapper<Colossal.PSI.Common.DlcId, System.String>
{
    private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String> m_Mapping;

    public System.Int32 count { get; }

    protected GdkDlcMapper();

    public System.Boolean Lookup(Colossal.PSI.Common.DlcId dlcId, System.String& id);
    protected System.Void Map(Colossal.PSI.Common.DlcId dlcId, System.String id);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String> m_Mapping`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, System.String> m_Mapping;
```


## Properties

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `protected GdkDlcMapper()`  

```csharp
protected GdkDlcMapper();
```


## Methods

- `public Lookup(Colossal.PSI.Common.DlcId dlcId, System.String& id) : System.Boolean`  

```csharp
public System.Boolean Lookup(Colossal.PSI.Common.DlcId dlcId, System.String& id);
```

- `protected Map(Colossal.PSI.Common.DlcId dlcId, System.String id) : System.Void`  

```csharp
protected System.Void Map(Colossal.PSI.Common.DlcId dlcId, System.String id);
```


