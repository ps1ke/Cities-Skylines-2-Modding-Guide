# PDX.SDK.Contracts.Credential.SteamCredential

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Credential`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Credential.ICredential`  

## Code

```csharp
public class SteamCredential : PDX.SDK.Contracts.Credential.ICredential
{
    private System.String <Ticket>k__BackingField;
    private System.UInt32 <AppId>k__BackingField;

    public System.String Ticket { get; set; }
    public System.UInt32 AppId { get; set; }

    public SteamCredential(System.String ticket, System.UInt32 appId);

}
```


## Fields

- `private System.String <Ticket>k__BackingField`  

```csharp
private System.String <Ticket>k__BackingField;
```

- `private System.UInt32 <AppId>k__BackingField`  

```csharp
private System.UInt32 <AppId>k__BackingField;
```


## Properties

- `public System.String Ticket { get; set }`  

```csharp
public System.String Ticket { get; set; }
```

- `public System.UInt32 AppId { get; set }`  

```csharp
public System.UInt32 AppId { get; set; }
```


## Constructors

- `public SteamCredential(System.String ticket, System.UInt32 appId)`  

```csharp
public SteamCredential(System.String ticket, System.UInt32 appId);
```


