# PDX.SDK.Contracts.Service.Mods.Models.IMod

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMod
{
    public System.Int32 Id { get; set; }
    public System.String Version { get; set; }
    public System.String Name { get; set; }
    public System.String DisplayName { get; set; }
    public System.String Author { get; set; }
    public System.String ShortDescription { get; set; }
    public System.String LongDescription { get; set; }
    public System.String RequiredGameVersion { get; set; }
    public System.String UserModVersion { get; set; }
    public System.String LatestVersion { get; set; }
    public System.String ThumbnailPath { get; set; }
    public System.UInt64 Size { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModTag> Tags { get; set; }
    public System.Int32 Rating { get; set; }
    public System.Int32 RatingsTotal { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
    public System.Nullable<System.DateTime> LatestUpdate { get; set; }
    public System.Nullable<System.DateTime> InstalledDate { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }

}
```


## Properties

- `public System.Int32 Id { get; set }`  

```csharp
public System.Int32 Id { get; set; }
```

- `public System.String Version { get; set }`  

```csharp
public System.String Version { get; set; }
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

- `public System.Nullable<System.DateTime> LatestUpdate { get; set }`  

```csharp
public System.Nullable<System.DateTime> LatestUpdate { get; set; }
```

- `public System.Nullable<System.DateTime> InstalledDate { get; set }`  

```csharp
public System.Nullable<System.DateTime> InstalledDate { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.LocalData LocalData { get; set; }
```


