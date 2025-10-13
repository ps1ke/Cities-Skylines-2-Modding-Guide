# PDX.SDK.Contracts.Service.Mods.Models.Mod

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Mods.Models.IMod`  

## Code

```csharp
public class Mod : PDX.SDK.Contracts.Service.Mods.Models.IMod
{
    private System.Int32 <Id>k__BackingField;
    private System.String <Name>k__BackingField;
    private System.String <DisplayName>k__BackingField;
    private System.String <Author>k__BackingField;
    private System.String <ShortDescription>k__BackingField;
    private System.String <LongDescription>k__BackingField;
    private System.String <RequiredGameVersion>k__BackingField;
    private System.String <UserModVersion>k__BackingField;
    private System.String <LatestVersion>k__BackingField;
    private System.String <Version>k__BackingField;
    private System.String <ThumbnailPath>k__BackingField;
    private System.UInt64 <Size>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> <Tags>k__BackingField;
    private System.Int32 <Rating>k__BackingField;
    private System.Int32 <RatingsTotal>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField;
    private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField;
    private System.Nullable<System.DateTime> <InstalledDate>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> <Playsets>k__BackingField;
    private System.Boolean <HasLiked>k__BackingField;
    private System.Nullable<System.DateTime> <CreationDate>k__BackingField;

    public System.Int32 Id { get; set; }
    public System.String Name { get; set; }
    public System.String DisplayName { get; set; }
    public System.String Author { get; set; }
    public System.String ShortDescription { get; set; }
    public System.String LongDescription { get; set; }
    public System.String RequiredGameVersion { get; set; }
    public System.String UserModVersion { get; set; }
    public System.String LatestVersion { get; set; }
    public System.String Version { get; set; }
    public System.String ThumbnailPath { get; set; }
    public System.UInt64 Size { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> Tags { get; set; }
    public System.Int32 Rating { get; set; }
    public System.Int32 RatingsTotal { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
    public System.Nullable<System.DateTime> LatestUpdate { get; set; }
    public System.Nullable<System.DateTime> InstalledDate { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> Playsets { get; set; }
    public System.Boolean HasLiked { get; set; }
    public System.Nullable<System.DateTime> CreationDate { get; set; }

    public Mod();

}
```


## Fields

- `private System.Int32 <Id>k__BackingField`  

```csharp
private System.Int32 <Id>k__BackingField;
```

- `private System.String <Name>k__BackingField`  

```csharp
private System.String <Name>k__BackingField;
```

- `private System.String <DisplayName>k__BackingField`  

```csharp
private System.String <DisplayName>k__BackingField;
```

- `private System.String <Author>k__BackingField`  

```csharp
private System.String <Author>k__BackingField;
```

- `private System.String <ShortDescription>k__BackingField`  

```csharp
private System.String <ShortDescription>k__BackingField;
```

- `private System.String <LongDescription>k__BackingField`  

```csharp
private System.String <LongDescription>k__BackingField;
```

- `private System.String <RequiredGameVersion>k__BackingField`  

```csharp
private System.String <RequiredGameVersion>k__BackingField;
```

- `private System.String <UserModVersion>k__BackingField`  

```csharp
private System.String <UserModVersion>k__BackingField;
```

- `private System.String <LatestVersion>k__BackingField`  

```csharp
private System.String <LatestVersion>k__BackingField;
```

- `private System.String <Version>k__BackingField`  

```csharp
private System.String <Version>k__BackingField;
```

- `private System.String <ThumbnailPath>k__BackingField`  

```csharp
private System.String <ThumbnailPath>k__BackingField;
```

- `private System.UInt64 <Size>k__BackingField`  

```csharp
private System.UInt64 <Size>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> <Tags>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> <Tags>k__BackingField;
```

- `private System.Int32 <Rating>k__BackingField`  

```csharp
private System.Int32 <Rating>k__BackingField;
```

- `private System.Int32 <RatingsTotal>k__BackingField`  

```csharp
private System.Int32 <RatingsTotal>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.LocalData <LocalData>k__BackingField;
```

- `private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField;
```

- `private System.Nullable<System.DateTime> <InstalledDate>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <InstalledDate>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> <Playsets>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> <Playsets>k__BackingField;
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

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String DisplayName { get; set }`  

```csharp
public System.String DisplayName { get; set; }
```

- `public System.String Author { get; set }`  

```csharp
public System.String Author { get; set; }
```

- `public System.String ShortDescription { get; set }`  

```csharp
public System.String ShortDescription { get; set; }
```

- `public System.String LongDescription { get; set }`  

```csharp
public System.String LongDescription { get; set; }
```

- `public System.String RequiredGameVersion { get; set }`  

```csharp
public System.String RequiredGameVersion { get; set; }
```

- `public System.String UserModVersion { get; set }`  

```csharp
public System.String UserModVersion { get; set; }
```

- `public System.String LatestVersion { get; set }`  

```csharp
public System.String LatestVersion { get; set; }
```

- `public System.String Version { get; set }`  

```csharp
public System.String Version { get; set; }
```

- `public System.String ThumbnailPath { get; set }`  

```csharp
public System.String ThumbnailPath { get; set; }
```

- `public System.UInt64 Size { get; set }`  

```csharp
public System.UInt64 Size { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> Tags { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> Tags { get; set; }
```

- `public System.Int32 Rating { get; set }`  

```csharp
public System.Int32 Rating { get; set; }
```

- `public System.Int32 RatingsTotal { get; set }`  

```csharp
public System.Int32 RatingsTotal { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
```

- `public System.Nullable<System.DateTime> LatestUpdate { get; set }`  

```csharp
public System.Nullable<System.DateTime> LatestUpdate { get; set; }
```

- `public System.Nullable<System.DateTime> InstalledDate { get; set }`  

```csharp
public System.Nullable<System.DateTime> InstalledDate { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> Playsets { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.PlaysetInMod> Playsets { get; set; }
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

- `public Mod()`  

```csharp
public Mod();
```


