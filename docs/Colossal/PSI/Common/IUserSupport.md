# Colossal.PSI.Common.IUserSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Properties

- `public System.Boolean requiresEngagement { get }`  
- `public System.Boolean isUserSignedIn { get }`  
- `public System.String userName { get }`  
- `public System.Boolean supportsUserSwitching { get }`  
- `public System.Boolean supportsUserSection { get }`  
- `public System.String userSpecificPath { get }`  
- `public System.Boolean hasUgcPrivilege { get }`  

## Methods

- `public abstract ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  
- `public abstract GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  
- `public abstract SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  

## Events

- `onUserUpdated` : `Colossal.PSI.Common.OnUserUpdatedEventHandler`  

