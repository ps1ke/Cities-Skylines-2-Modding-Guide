# PDX.SDK.Contracts.Service.Account.Result.ThirdPartyResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Account.Result`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ThirdPartyResult
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ParadoxAccountLinks>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ThirdPartyAccountLinks>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ParadoxAccountLinks { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ThirdPartyAccountLinks { get; set; }

    public ThirdPartyResult();

    public System.Boolean IsLinkedTo(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider);
}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ParadoxAccountLinks>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ParadoxAccountLinks>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ThirdPartyAccountLinks>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> <ThirdPartyAccountLinks>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ParadoxAccountLinks { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ParadoxAccountLinks { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ThirdPartyAccountLinks { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.AccountLink> ThirdPartyAccountLinks { get; set; }
```


## Constructors

- `public ThirdPartyResult()`  

```csharp
public ThirdPartyResult();
```


## Methods

- `public IsLinkedTo(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider) : System.Boolean`  

```csharp
public System.Boolean IsLinkedTo(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider);
```


