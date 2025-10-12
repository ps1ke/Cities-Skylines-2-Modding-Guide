# Game.UI.Menu.ParadoxBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Fields

- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_RequestActiveBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_LoggedInBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<Colossal.PSI.Common.AccountLinkProvider> m_AccountLinkProviderBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_AccountLinkStateBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_UserNameBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_EmailBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_HasInternetConnection`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Boolean> m_IsPDXSDKEnabled`  
- `private readonly Colossal.UI.Binding.StackBinding<Game.UI.Menu.ParadoxBindings+ParadoxDialog> m_ActiveDialogsBinding`  
- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform`  
- `private static readonly System.String kTermsOfUse`  
- `private static readonly System.String kPrivacyPolicy`  
- `private static const System.String kGroup`  

## Constructors

- `public ParadoxBindings()`  

## Methods

- `private <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private CloseActiveDialog() : System.Void`  
- `private ConfirmAccountLink() : System.Void`  
- `private ConfirmAccountLinkOverwrite() : System.Void`  
- `private GetAccountLinkProviderIcon() : System.String`  
- `private GetCountryCodes() : System.Collections.Generic.List<System.String>`  
- `private LinkAccount() : System.Void`  
- `private Logout() : System.Void`  
- `private MarkLegalDocumentAsViewed() : System.Void`  
- `private OnAccountLinkChanged(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider) : System.Void`  
- `private OnInternetConnectionStatusChanged(System.Boolean connected) : System.Void`  
- `private OnLegalDocumentStatusChanged(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remainingCount) : System.Void`  
- `private OnOptionSelected(System.Int32 index) : System.Void`  
- `public OnPSModsUIClosed(System.Action onKeepMods, System.Action onDisableMods, System.Action onBack) : System.Void`  
- `public OnPSModsUIOpened(System.Action onContinue) : System.Void`  
- `private OnStatusChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private OnUserLoggedIn(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime) : System.Void`  
- `private OnUserLoggedOut(System.String id) : System.Void`  
- `public PushDialog(Game.UI.Menu.ParadoxBindings+ParadoxDialog dialog) : System.Void`  
- `private RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task) : System.Threading.Tasks.Task<T>`  
- `private ShowLink(System.String link) : System.Void`  
- `public ShowLoginForm() : System.Void`  
- `private ShowPrivacyPolicy() : System.Void`  
- `private ShowRegistrationForm() : System.Void`  
- `private ShowTermsOfUse() : System.Void`  
- `private SubmitLoginForm(Game.UI.Menu.ParadoxBindings+LoginFormData data) : System.Void`  
- `private SubmitPasswordReset(System.String email) : System.Void`  
- `private SubmitRegistrationForm(Game.UI.Menu.ParadoxBindings+RegistrationFormData data) : System.Void`  
- `private UnlinkAccount() : System.Void`  

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

