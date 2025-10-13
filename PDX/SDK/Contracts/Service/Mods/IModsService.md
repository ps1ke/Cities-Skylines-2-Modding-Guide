# PDX.SDK.Contracts.Service.Mods.IModsService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods`  

**Type:** interface abstract public  


**Attributes:** `Preserve`  

## Code

```csharp
public abstract interface IModsService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ActivatePlayset(System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CleanupAllPDXMods();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CleanupReportedMods();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult> ClonePlayset(System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreateForumPostResult> CreateForumPost(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.String message);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult> CreatePlayset(System.String playsetName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeactivateActivePlayset();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeletePlayset(System.Int32 playsetId, System.Boolean abortOnLocalFailure);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Disable(System.Int32 modId, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Disable(System.String modName, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Enable(System.Int32 modId, System.Int32 playsetId, System.Boolean enableOnBackend);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Enable(System.String modName, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> FollowModCreator(System.String userName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetActivePlaysetResult> GetActivePlayset();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult> GetActivePlaysetEnabledMods();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult> GetAllDependencies(System.Collections.Generic.List<System.Int32> mods, System.Nullable<System.Int32> playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult> GetDependencyCandidates(System.Int32 modId, System.String searchQuery, System.Nullable<System.Int32> amount);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(System.Int32 modId, System.String version, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(PDX.SDK.Contracts.Service.Mods.Models.IMod mod, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(System.String modName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListOfFeaturedModsResult> GetFeaturedModsLists(System.Nullable<System.Int32> page, System.Nullable<System.Int32> limit);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetFollowedModCreatorsResult> GetFollowedModCreators(System.Nullable<System.Int32> limit, System.Nullable<System.Int32> page);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetForumThreadResult> GetForumThread(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.Int32 page, System.Int32 limit);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetGameDataResult> GetGameData();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModCreatorsProfileResult> GetModCreatorProfile(System.String userName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependantsResult> GetModDependants(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModInstallSizeResult> GetRequiredInstallSize(PDX.SDK.Contracts.Service.Mods.Models.ModDetails modDetails, System.String versionToInstall);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[]> GetSyncConflicts();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetThirdPartyProfilesResult> GetThirdPartyProfiles(System.Collections.Generic.IEnumerable<System.String> userIds);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetUserRatingResult> GetUserRating(System.Int32 modId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModVersionsResult> GetVersions(System.Int32 modId);
    public abstract System.Boolean HasLocalChanges();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult> List(System.String searchQuery, PDX.SDK.Contracts.Service.Mods.Enums.InstalledModsSortMethod sortMethod, System.Collections.Generic.List<System.String> filterTags);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListAllPlaysetsResult> ListAllPlaysets(System.Boolean includeOnline);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListModsInPlaysetResult> ListModsInPlayset(System.Int32 playsetId, System.Nullable<System.Int32> limit, System.Nullable<System.Int32> page, System.Boolean includeOnline);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult> PublishNewModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishNewVersionData);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishResult> PublishWIP(PDX.SDK.Contracts.Service.Mods.Models.PublishWipData publishWipData);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RateResult> Rate(System.Int32 modId, System.Int32 rating);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> RefreshUnmanagedMods();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> RegisterExistingWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData wipData, System.String path, System.Nullable<System.Int32> modId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> RegisterWIP(System.String displayName, System.String shortDescription, System.String longDescription, System.UInt64 size);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RenamePlaysetResult> RenamePlayset(System.Int32 playsetId, System.String playsetName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Report(System.Int32 modId, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reason, System.String description);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ReportModCreatorResult> ReportModCreator(System.String userName, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reportReason, System.String description);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> ResetLoadOrder(System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModSearchResult> Search(PDX.SDK.Contracts.Service.Mods.Models.SearchData searchData);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> SetLoadOrder(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModLoadOrder> modLoadOrderList, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> SetLoadOrder(PDX.SDK.Contracts.Service.Mods.Enums.SearchOrder orderBy, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> Subscribe(System.Int32 modId, System.Nullable<System.Int32> playsetId, System.String version);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> Subscribe(System.String modName, System.Nullable<System.Int32> playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> SubscribeBulk(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.Int32, System.String>> mods, System.Nullable<System.Int32> playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> SubscribeBulk(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.IMod> mods, System.Nullable<System.Int32> playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Sync(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
    public abstract System.Boolean SyncOngoing();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SyncPlayset(System.Int32 playsetId, PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> SyncWIPMod(System.Int32 modId, System.String version);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnfollowModCreator(System.String userName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unpublish(System.Int32 modId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnregisterWIP(System.String guid);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.Int32 modId, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.Int32 modId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.String modName, System.Int32 playsetId);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.String modName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult> UpdatePublishedModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishUpdateData, System.String version);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UpdateWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData updateWipData);
}
```


## Methods

- `public abstract ActivatePlayset(System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ActivatePlayset(System.Int32 playsetId);
```

- `public abstract CleanupAllPDXMods() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CleanupAllPDXMods();
```

- `public abstract CleanupReportedMods() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CleanupReportedMods();
```

- `public abstract ClonePlayset(System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult> ClonePlayset(System.Int32 playsetId);
```

- `public abstract CreateForumPost(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.String message) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreateForumPostResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreateForumPostResult> CreateForumPost(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.String message);
```

- `public abstract CreatePlayset(System.String playsetName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.CreatePlaysetResult> CreatePlayset(System.String playsetName);
```

- `public abstract DeactivateActivePlayset() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeactivateActivePlayset();
```

- `public abstract DeletePlayset(System.Int32 playsetId, System.Boolean abortOnLocalFailure = True) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeletePlayset(System.Int32 playsetId, System.Boolean abortOnLocalFailure);
```

- `public abstract Disable(System.Int32 modId, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Disable(System.Int32 modId, System.Int32 playsetId);
```

- `public abstract Disable(System.String modName, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Disable(System.String modName, System.Int32 playsetId);
```

- `public abstract DisableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
```

- `public abstract DisableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId);
```

- `public abstract DisableBulk(System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> DisableBulk(System.Int32 playsetId);
```

- `public abstract Enable(System.Int32 modId, System.Int32 playsetId, System.Boolean enableOnBackend = True) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Enable(System.Int32 modId, System.Int32 playsetId, System.Boolean enableOnBackend);
```

- `public abstract Enable(System.String modName, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Enable(System.String modName, System.Int32 playsetId);
```

- `public abstract EnableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Collections.Generic.List<System.String> modNames, System.Int32 playsetId);
```

- `public abstract EnableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
```

- `public abstract EnableBulk(System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.BulkResult> EnableBulk(System.Int32 playsetId);
```

- `public abstract FollowModCreator(System.String userName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> FollowModCreator(System.String userName);
```

- `public abstract GetActivePlayset() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetActivePlaysetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetActivePlaysetResult> GetActivePlayset();
```

- `public abstract GetActivePlaysetEnabledMods() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult> GetActivePlaysetEnabledMods();
```

- `public abstract GetAllDependencies(System.Collections.Generic.List<System.Int32> mods, System.Nullable<System.Int32> playsetId = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult> GetAllDependencies(System.Collections.Generic.List<System.Int32> mods, System.Nullable<System.Int32> playsetId);
```

- `public abstract GetDependencyCandidates(System.Int32 modId, System.String searchQuery = null, System.Nullable<System.Int32> amount = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependenciesResult> GetDependencyCandidates(System.Int32 modId, System.String searchQuery, System.Nullable<System.Int32> amount);
```

- `public abstract GetDetails(System.Int32 modId, System.String version = null, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(System.Int32 modId, System.String version, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os);
```

- `public abstract GetDetails(PDX.SDK.Contracts.Service.Mods.Models.IMod mod, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(PDX.SDK.Contracts.Service.Mods.Models.IMod mod, System.Nullable<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform> os);
```

- `public abstract GetDetails(System.String modName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetDetailsResult> GetDetails(System.String modName);
```

- `public abstract GetFeaturedModsLists(System.Nullable<System.Int32> page = null, System.Nullable<System.Int32> limit = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListOfFeaturedModsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListOfFeaturedModsResult> GetFeaturedModsLists(System.Nullable<System.Int32> page, System.Nullable<System.Int32> limit);
```

- `public abstract GetFollowedModCreators(System.Nullable<System.Int32> limit = 20, System.Nullable<System.Int32> page = 1) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetFollowedModCreatorsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetFollowedModCreatorsResult> GetFollowedModCreators(System.Nullable<System.Int32> limit, System.Nullable<System.Int32> page);
```

- `public abstract GetForumThread(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.Int32 page, System.Int32 limit) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetForumThreadResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetForumThreadResult> GetForumThread(System.Int32 modId, System.String modVersion, System.Int32 threadId, System.Int32 page, System.Int32 limit);
```

- `public abstract GetGameData() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetGameDataResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetGameDataResult> GetGameData();
```

- `public abstract GetModCreatorProfile(System.String userName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModCreatorsProfileResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModCreatorsProfileResult> GetModCreatorProfile(System.String userName);
```

- `public abstract GetModDependants(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId = 0) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependantsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModDependantsResult> GetModDependants(System.Collections.Generic.List<System.Int32> modIds, System.Int32 playsetId);
```

- `public abstract GetRequiredInstallSize(PDX.SDK.Contracts.Service.Mods.Models.ModDetails modDetails, System.String versionToInstall) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModInstallSizeResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModInstallSizeResult> GetRequiredInstallSize(PDX.SDK.Contracts.Service.Mods.Models.ModDetails modDetails, System.String versionToInstall);
```

- `public abstract GetSyncConflicts() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[]>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[]> GetSyncConflicts();
```

- `public abstract GetThirdPartyProfiles(System.Collections.Generic.IEnumerable<System.String> userIds) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetThirdPartyProfilesResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetThirdPartyProfilesResult> GetThirdPartyProfiles(System.Collections.Generic.IEnumerable<System.String> userIds);
```

- `public abstract GetUserRating(System.Int32 modId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetUserRatingResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetUserRatingResult> GetUserRating(System.Int32 modId);
```

- `public abstract GetVersions(System.Int32 modId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModVersionsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.GetModVersionsResult> GetVersions(System.Int32 modId);
```

- `public abstract HasLocalChanges() : System.Boolean`  

```csharp
public abstract System.Boolean HasLocalChanges();
```

- `public abstract List(System.String searchQuery = null, PDX.SDK.Contracts.Service.Mods.Enums.InstalledModsSortMethod sortMethod = RecentFirst, System.Collections.Generic.List<System.String> filterTags = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModListResult> List(System.String searchQuery, PDX.SDK.Contracts.Service.Mods.Enums.InstalledModsSortMethod sortMethod, System.Collections.Generic.List<System.String> filterTags);
```

- `public abstract ListAllPlaysets(System.Boolean includeOnline = False) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListAllPlaysetsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListAllPlaysetsResult> ListAllPlaysets(System.Boolean includeOnline);
```

- `public abstract ListModsInPlayset(System.Int32 playsetId, System.Nullable<System.Int32> limit = null, System.Nullable<System.Int32> page = null, System.Boolean includeOnline = False) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListModsInPlaysetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ListModsInPlaysetResult> ListModsInPlayset(System.Int32 playsetId, System.Nullable<System.Int32> limit, System.Nullable<System.Int32> page, System.Boolean includeOnline);
```

- `public abstract PublishNewModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishNewVersionData) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult> PublishNewModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishNewVersionData);
```

- `public abstract PublishWIP(PDX.SDK.Contracts.Service.Mods.Models.PublishWipData publishWipData) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishResult> PublishWIP(PDX.SDK.Contracts.Service.Mods.Models.PublishWipData publishWipData);
```

- `public abstract Rate(System.Int32 modId, System.Int32 rating) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RateResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RateResult> Rate(System.Int32 modId, System.Int32 rating);
```

- `public abstract RefreshUnmanagedMods() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> RefreshUnmanagedMods();
```

- `public abstract RegisterExistingWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData wipData, System.String path, System.Nullable<System.Int32> modId = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> RegisterExistingWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData wipData, System.String path, System.Nullable<System.Int32> modId);
```

- `public abstract RegisterWIP(System.String displayName, System.String shortDescription = null, System.String longDescription = null, System.UInt64 size = 0) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> RegisterWIP(System.String displayName, System.String shortDescription, System.String longDescription, System.UInt64 size);
```

- `public abstract RenamePlayset(System.Int32 playsetId, System.String playsetName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RenamePlaysetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RenamePlaysetResult> RenamePlayset(System.Int32 playsetId, System.String playsetName);
```

- `public abstract Report(System.Int32 modId, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reason, System.String description = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Report(System.Int32 modId, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reason, System.String description);
```

- `public abstract ReportModCreator(System.String userName, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reportReason, System.String description) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ReportModCreatorResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ReportModCreatorResult> ReportModCreator(System.String userName, PDX.SDK.Contracts.Service.Mods.Enums.ReportReason reportReason, System.String description);
```

- `public abstract ResetLoadOrder(System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> ResetLoadOrder(System.Int32 playsetId);
```

- `public abstract Search(PDX.SDK.Contracts.Service.Mods.Models.SearchData searchData) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModSearchResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.ModSearchResult> Search(PDX.SDK.Contracts.Service.Mods.Models.SearchData searchData);
```

- `public abstract SetLoadOrder(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModLoadOrder> modLoadOrderList, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> SetLoadOrder(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModLoadOrder> modLoadOrderList, System.Int32 playsetId);
```

- `public abstract SetLoadOrder(PDX.SDK.Contracts.Service.Mods.Enums.SearchOrder orderBy, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.LoadOrderResult> SetLoadOrder(PDX.SDK.Contracts.Service.Mods.Enums.SearchOrder orderBy, System.Int32 playsetId);
```

- `public abstract Subscribe(System.Int32 modId, System.Nullable<System.Int32> playsetId = null, System.String version = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> Subscribe(System.Int32 modId, System.Nullable<System.Int32> playsetId, System.String version);
```

- `public abstract Subscribe(System.String modName, System.Nullable<System.Int32> playsetId = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> Subscribe(System.String modName, System.Nullable<System.Int32> playsetId);
```

- `public abstract SubscribeBulk(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.Int32, System.String>> mods, System.Nullable<System.Int32> playsetId = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> SubscribeBulk(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.Int32, System.String>> mods, System.Nullable<System.Int32> playsetId);
```

- `public abstract SubscribeBulk(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.IMod> mods, System.Nullable<System.Int32> playsetId = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult> SubscribeBulk(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.Mods.Models.IMod> mods, System.Nullable<System.Int32> playsetId);
```

- `public abstract Sync(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection = Default) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Sync(PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
```

- `public abstract SyncOngoing() : System.Boolean`  

```csharp
public abstract System.Boolean SyncOngoing();
```

- `public abstract SyncPlayset(System.Int32 playsetId, PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SyncPlayset(System.Int32 playsetId, PDX.SDK.Contracts.Service.Mods.Enums.SyncDirection syncDirection);
```

- `public abstract SyncWIPMod(System.Int32 modId, System.String version = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.RegisterResult> SyncWIPMod(System.Int32 modId, System.String version);
```

- `public abstract UnfollowModCreator(System.String userName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnfollowModCreator(System.String userName);
```

- `public abstract Unpublish(System.Int32 modId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unpublish(System.Int32 modId);
```

- `public abstract UnregisterWIP(System.String guid) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UnregisterWIP(System.String guid);
```

- `public abstract Unsubscribe(System.Int32 modId, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.Int32 modId, System.Int32 playsetId);
```

- `public abstract Unsubscribe(System.Int32 modId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.Int32 modId);
```

- `public abstract Unsubscribe(System.String modName, System.Int32 playsetId) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.String modName, System.Int32 playsetId);
```

- `public abstract Unsubscribe(System.String modName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unsubscribe(System.String modName);
```

- `public abstract UpdatePublishedModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishUpdateData, System.String version = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Mods.Result.PublishUpdateResult> UpdatePublishedModVersion(PDX.SDK.Contracts.Service.Mods.Models.PublishUpdateData publishUpdateData, System.String version);
```

- `public abstract UpdateWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData updateWipData) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UpdateWIP(PDX.SDK.Contracts.Service.Mods.Models.UpdateWipData updateWipData);
```


