# PDX.SDK.Contracts.Service.Mods.Models.PlaysetSubscribedMod

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod`  

## Code

```csharp
public class PlaysetSubscribedMod : PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod
{
    private System.Int32 <Id>k__BackingField;
    private System.String <ShortDescription>k__BackingField;
    private System.String <RequiredGameVersion>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
    private System.Boolean <IsEnabled>k__BackingField;
    private System.String <DisplayName>k__BackingField;
    private System.String <Version>k__BackingField;
    private System.Int32 <LoadOrder>k__BackingField;
    private System.UInt64 <Size>k__BackingField;
    private System.Nullable<System.DateTime> <Updated>k__BackingField;
    private PDX.SDK.Contracts.Service.Generic.ITag[] <Tags>k__BackingField;
    private System.String <DisplayImagePath>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField;
    private System.String <UserModVersion>k__BackingField;
    private System.Int32 <RatingsTotal>k__BackingField;
    private System.String <Author>k__BackingField;
    private System.Boolean <HasLiked>k__BackingField;
    private System.Nullable<System.DateTime> <CreationDate>k__BackingField;

    public System.Int32 Id { get; set; }
    public System.String ShortDescription { get; set; }
    public System.String RequiredGameVersion { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
    public System.Boolean IsEnabled { get; set; }
    public System.String DisplayName { get; set; }
    public System.String Version { get; set; }
    public System.Int32 LoadOrder { get; set; }
    public System.UInt64 Size { get; set; }
    public System.Nullable<System.DateTime> Updated { get; set; }
    public PDX.SDK.Contracts.Service.Generic.ITag[] Tags { get; set; }
    public System.String DisplayImagePath { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set; }
    public System.String UserModVersion { get; set; }
    public System.Int32 RatingsTotal { get; set; }
    public System.String Author { get; set; }
    public System.Boolean HasLiked { get; set; }
    public System.Nullable<System.DateTime> CreationDate { get; set; }

    public PlaysetSubscribedMod();

}
```


## Fields

- `private System.Int32 <Id>k__BackingField`  

```csharp
private System.Int32 <Id>k__BackingField;
```

- `private System.String <ShortDescription>k__BackingField`  

```csharp
private System.String <ShortDescription>k__BackingField;
```

- `private System.String <RequiredGameVersion>k__BackingField`  

```csharp
private System.String <RequiredGameVersion>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
```

- `private System.Boolean <IsEnabled>k__BackingField`  

```csharp
private System.Boolean <IsEnabled>k__BackingField;
```

- `private System.String <DisplayName>k__BackingField`  

```csharp
private System.String <DisplayName>k__BackingField;
```

- `private System.String <Version>k__BackingField`  

```csharp
private System.String <Version>k__BackingField;
```

- `private System.Int32 <LoadOrder>k__BackingField`  

```csharp
private System.Int32 <LoadOrder>k__BackingField;
```

- `private System.UInt64 <Size>k__BackingField`  

```csharp
private System.UInt64 <Size>k__BackingField;
```

- `private System.Nullable<System.DateTime> <Updated>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <Updated>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Generic.ITag[] <Tags>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Generic.ITag[] <Tags>k__BackingField;
```

- `private System.String <DisplayImagePath>k__BackingField`  

```csharp
private System.String <DisplayImagePath>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField;
```

- `private System.String <UserModVersion>k__BackingField`  

```csharp
private System.String <UserModVersion>k__BackingField;
```

- `private System.Int32 <RatingsTotal>k__BackingField`  

```csharp
private System.Int32 <RatingsTotal>k__BackingField;
```

- `private System.String <Author>k__BackingField`  

```csharp
private System.String <Author>k__BackingField;
```

- `private System.Boolean <HasLiked>k__BackingField`  

```csharp
private System.Boolean <HasLiked>k__BackingField;
```

- `private System.Nullable<System.DateTime> <CreationDate>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <CreationDate>k__BackingField;
```


## Properties

- `public System.Int32 Id { get; set }`  

```csharp
public System.Int32 Id { get; set; }
```

- `public System.String ShortDescription { get; set }`  

```csharp
public System.String ShortDescription { get; set; }
```

- `public System.String RequiredGameVersion { get; set }`  

```csharp
public System.String RequiredGameVersion { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
```

- `public System.Boolean IsEnabled { get; set }`  

```csharp
public System.Boolean IsEnabled { get; set; }
```

- `public System.String DisplayName { get; set }`  

```csharp
public System.String DisplayName { get; set; }
```

- `public System.String Version { get; set }`  

```csharp
public System.String Version { get; set; }
```

- `public System.Int32 LoadOrder { get; set }`  

```csharp
public System.Int32 LoadOrder { get; set; }
```

- `public System.UInt64 Size { get; set }`  

```csharp
public System.UInt64 Size { get; set; }
```

- `public System.Nullable<System.DateTime> Updated { get; set }`  

```csharp
public System.Nullable<System.DateTime> Updated { get; set; }
```

- `public PDX.SDK.Contracts.Service.Generic.ITag[] Tags { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Generic.ITag[] Tags { get; set; }
```

- `public System.String DisplayImagePath { get; set }`  

```csharp
public System.String DisplayImagePath { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set; }
```

- `public System.String UserModVersion { get; set }`  

```csharp
public System.String UserModVersion { get; set; }
```

- `public System.Int32 RatingsTotal { get; set }`  

```csharp
public System.Int32 RatingsTotal { get; set; }
```

- `public System.String Author { get; set }`  

```csharp
public System.String Author { get; set; }
```

- `public System.Boolean HasLiked { get; set }`  

```csharp
public System.Boolean HasLiked { get; set; }
```

- `public System.Nullable<System.DateTime> CreationDate { get; set }`  

```csharp
public System.Nullable<System.DateTime> CreationDate { get; set; }
```


## Constructors

- `public PlaysetSubscribedMod()`  

```csharp
public PlaysetSubscribedMod();
```


