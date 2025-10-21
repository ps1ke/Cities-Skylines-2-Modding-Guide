# Game.UI.Menu.ParadoxBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Code

```csharp
public class ParadoxBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup
{
    private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_RequestActiveBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_LoggedInBinding;
    private readonly Colossal.UI.Binding.ValueBinding<Colossal.PSI.Common.AccountLinkProvider> m_AccountLinkProviderBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_AccountLinkStateBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.String> m_UserNameBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.String> m_EmailBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_HasInternetConnection;
    private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_IsPDXSDKEnabled;
    private readonly Colossal.UI.Binding.StackBinding<Game.UI.Menu.ParadoxBindings+ParadoxDialog> m_ActiveDialogsBinding;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
    private static readonly System.String kTermsOfUse;
    private static readonly System.String kPrivacyPolicy;
    private static const System.String kGroup;

    public ParadoxBindings();

    private System.Void <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Void CloseActiveDialog();
    private System.Void ConfirmAccountLink();
    private System.Void ConfirmAccountLinkOverwrite();
    private System.String GetAccountLinkProviderIcon();
    private System.Collections.Generic.List<System.String> GetCountryCodes();
    private System.Void LinkAccount();
    private System.Void Logout();
    private System.Void MarkLegalDocumentAsViewed();
    private System.Void OnAccountLinkChanged(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider);
    private System.Void OnInternetConnectionStatusChanged(System.Boolean connected);
    private System.Void OnLegalDocumentStatusChanged(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remainingCount);
    private System.Void OnOptionSelected(System.Int32 index);
    public System.Void OnPSModsUIClosed(System.Action onKeepMods, System.Action onDisableMods, System.Action onBack);
    public System.Void OnPSModsUIOpened(System.Action onContinue);
    private System.Void OnStatusChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Void OnUserLoggedIn(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime);
    private System.Void OnUserLoggedOut(System.String id);
    public System.Void PushDialog(Game.UI.Menu.ParadoxBindings+ParadoxDialog dialog);
    private System.Threading.Tasks.Task<T> RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task);
    private System.Void ShowLink(System.String link);
    public System.Void ShowLoginForm();
    private System.Void ShowPrivacyPolicy();
    private System.Void ShowRegistrationForm();
    private System.Void ShowTermsOfUse();
    private System.Void SubmitLoginForm(Game.UI.Menu.ParadoxBindings+LoginFormData data);
    private System.Void SubmitPasswordReset(System.String email);
    private System.Void SubmitRegistrationForm(Game.UI.Menu.ParadoxBindings+RegistrationFormData data);
    private System.Void UnlinkAccount();
}
```


## Fields

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_RequestActiveBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_RequestActiveBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_LoggedInBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_LoggedInBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<Colossal.PSI.Common.AccountLinkProvider> m_AccountLinkProviderBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<Colossal.PSI.Common.AccountLinkProvider> m_AccountLinkProviderBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_AccountLinkStateBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_AccountLinkStateBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_UserNameBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.String> m_UserNameBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_EmailBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.String> m_EmailBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_HasInternetConnection`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_HasInternetConnection;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_IsPDXSDKEnabled`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_IsPDXSDKEnabled;
```

- `private readonly Colossal.UI.Binding.StackBinding<Game.UI.Menu.ParadoxBindings+ParadoxDialog> m_ActiveDialogsBinding`  

```csharp
private readonly Colossal.UI.Binding.StackBinding<Game.UI.Menu.ParadoxBindings+ParadoxDialog> m_ActiveDialogsBinding;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
```

- `private static readonly System.String kTermsOfUse`  

```csharp
private static readonly System.String kTermsOfUse;
```

- `private static readonly System.String kPrivacyPolicy`  

```csharp
private static readonly System.String kPrivacyPolicy;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ParadoxBindings()`  

```csharp
public ParadoxBindings();
```


## Methods

- `private <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private CloseActiveDialog() : System.Void`  

```csharp
private System.Void CloseActiveDialog();
```

- `private ConfirmAccountLink() : System.Void`  

```csharp
private System.Void ConfirmAccountLink();
```

- `private ConfirmAccountLinkOverwrite() : System.Void`  

```csharp
private System.Void ConfirmAccountLinkOverwrite();
```

- `private GetAccountLinkProviderIcon() : System.String`  

```csharp
private System.String GetAccountLinkProviderIcon();
```

- `private GetCountryCodes() : System.Collections.Generic.List<System.String>`  

```csharp
private System.Collections.Generic.List<System.String> GetCountryCodes();
```

- `private LinkAccount() : System.Void`  

```csharp
private System.Void LinkAccount();
```

- `private Logout() : System.Void`  

```csharp
private System.Void Logout();
```

- `private MarkLegalDocumentAsViewed() : System.Void`  

```csharp
private System.Void MarkLegalDocumentAsViewed();
```

- `private OnAccountLinkChanged(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider) : System.Void`  

```csharp
private System.Void OnAccountLinkChanged(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider);
```

- `private OnInternetConnectionStatusChanged(System.Boolean connected) : System.Void`  

```csharp
private System.Void OnInternetConnectionStatusChanged(System.Boolean connected);
```

- `private OnLegalDocumentStatusChanged(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remainingCount) : System.Void`  

```csharp
private System.Void OnLegalDocumentStatusChanged(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remainingCount);
```

- `private OnOptionSelected(System.Int32 index) : System.Void`  

```csharp
private System.Void OnOptionSelected(System.Int32 index);
```

- `public OnPSModsUIClosed(System.Action onKeepMods, System.Action onDisableMods, System.Action onBack) : System.Void`  

```csharp
public System.Void OnPSModsUIClosed(System.Action onKeepMods, System.Action onDisableMods, System.Action onBack);
```

- `public OnPSModsUIOpened(System.Action onContinue) : System.Void`  

```csharp
public System.Void OnPSModsUIOpened(System.Action onContinue);
```

- `private OnStatusChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void OnStatusChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private OnUserLoggedIn(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime) : System.Void`  

```csharp
private System.Void OnUserLoggedIn(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime);
```

- `private OnUserLoggedOut(System.String id) : System.Void`  

```csharp
private System.Void OnUserLoggedOut(System.String id);
```

- `public PushDialog(Game.UI.Menu.ParadoxBindings+ParadoxDialog dialog) : System.Void`  

```csharp
public System.Void PushDialog(Game.UI.Menu.ParadoxBindings+ParadoxDialog dialog);
```

- `private RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task) : System.Threading.Tasks.Task<T>`  

```csharp
private System.Threading.Tasks.Task<T> RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task);
```

- `private ShowLink(System.String link) : System.Void`  

```csharp
private System.Void ShowLink(System.String link);
```

- `public ShowLoginForm() : System.Void`  

```csharp
public System.Void ShowLoginForm();
```

- `private ShowPrivacyPolicy() : System.Void`  

```csharp
private System.Void ShowPrivacyPolicy();
```

- `private ShowRegistrationForm() : System.Void`  

```csharp
private System.Void ShowRegistrationForm();
```

- `private ShowTermsOfUse() : System.Void`  

```csharp
private System.Void ShowTermsOfUse();
```

- `private SubmitLoginForm(Game.UI.Menu.ParadoxBindings+LoginFormData data) : System.Void`  

```csharp
private System.Void SubmitLoginForm(Game.UI.Menu.ParadoxBindings+LoginFormData data);
```

- `private SubmitPasswordReset(System.String email) : System.Void`  

```csharp
private System.Void SubmitPasswordReset(System.String email);
```

- `private SubmitRegistrationForm(Game.UI.Menu.ParadoxBindings+RegistrationFormData data) : System.Void`  

```csharp
private System.Void SubmitRegistrationForm(Game.UI.Menu.ParadoxBindings+RegistrationFormData data);
```

- `private UnlinkAccount() : System.Void`  

```csharp
private System.Void UnlinkAccount();
```


## Nested types

- `Game.UI.Menu.ParadoxBindings+ParadoxDialog`  
- `Game.UI.Menu.ParadoxBindings+LoginFormData`  
- `Game.UI.Menu.ParadoxBindings+RegistrationFormData`  
- `Game.UI.Menu.ParadoxBindings+MessageDialog`  
- `Game.UI.Menu.ParadoxBindings+LoginDialog`  
- `Game.UI.Menu.ParadoxBindings+RegistrationDialog`  
- `Game.UI.Menu.ParadoxBindings+AccountLinkDialog`  
- `Game.UI.Menu.ParadoxBindings+AccountLinkOverwriteDialog`  
- `Game.UI.Menu.ParadoxBindings+LegalDocumentDialog`  
- `Game.UI.Menu.ParadoxBindings+ConfirmationDialog`  
- `Game.UI.Menu.ParadoxBindings+ErrorDialog`  
- `Game.UI.Menu.ParadoxBindings+MultiOptionDialog`  
- `Game.UI.Menu.ParadoxBindings+<ConfirmAccountLink>d__37`  
- `Game.UI.Menu.ParadoxBindings+<ConfirmAccountLinkOverwrite>d__38`  
- `Game.UI.Menu.ParadoxBindings+<Logout>d__23`  
- `Game.UI.Menu.ParadoxBindings+<MarkLegalDocumentAsViewed>d__44`  
- `Game.UI.Menu.ParadoxBindings+<OnUserLoggedIn>d__27`  
- `Game.UI.Menu.ParadoxBindings+<RunForegroundRequest>d__45<T>`  
- `Game.UI.Menu.ParadoxBindings+<ShowLink>d__35`  
- `Game.UI.Menu.ParadoxBindings+<SubmitLoginForm>d__32`  
- `Game.UI.Menu.ParadoxBindings+<SubmitPasswordReset>d__33`  
- `Game.UI.Menu.ParadoxBindings+<SubmitRegistrationForm>d__36`  
- `Game.UI.Menu.ParadoxBindings+<UnlinkAccount>d__40`  

