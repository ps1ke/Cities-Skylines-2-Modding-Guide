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
public ParadoxBindings()
	{
		AddBinding(m_RequestActiveBinding = new ValueBinding<bool>("paradox", "requestActive", initialValue: false));
		AddBinding(m_LoggedInBinding = new ValueBinding<bool>("paradox", "loggedIn", initialValue: false));
		AddBinding(m_AccountLinkProviderBinding = new ValueBinding<AccountLinkProvider>("paradox", "accountLinkProvider", AccountLinkProvider.Unknown, new EnumNameWriter<AccountLinkProvider>()));
		AddBinding(m_AccountLinkStateBinding = new ValueBinding<int>("paradox", "accountLinkState", 0));
		AddBinding(m_UserNameBinding = new ValueBinding<string>("paradox", "userName", null, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_EmailBinding = new ValueBinding<string>("paradox", "email", null, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_AvatarBinding = new ValueBinding<string>("paradox", "avatar", null, ValueWriters.Nullable(new StringWriter())));
		AddBinding(new TriggerBinding("paradox", "linkAccount", LinkAccount));
		AddBinding(new TriggerBinding("paradox", "unlinkAccount", UnlinkAccount));
		AddBinding(new TriggerBinding("paradox", "logout", Logout));
		AddBinding(m_ActiveDialogsBinding = new StackBinding<ParadoxDialog>("paradox", "activeDialogs", new ValueWriter<ParadoxDialog>()));
		AddBinding(new TriggerBinding("paradox", "closeActiveDialog", CloseActiveDialog));
		AddBinding(new TriggerBinding("paradox", "showLoginForm", ShowLoginForm));
		AddBinding(new TriggerBinding<string>("paradox", "submitPasswordReset", SubmitPasswordReset));
		AddBinding(new TriggerBinding<LoginFormData>("paradox", "submitLoginForm", SubmitLoginForm, new ValueReader<LoginFormData>()));
		AddBinding(m_HasInternetConnection = new ValueBinding<bool>("paradox", "hasInternetConnection", PlatformManager.instance.hasConnectivity));
		AddBinding(new GetterValueBinding<List<string>>("paradox", "countryCodes", GetCountryCodes, new ListWriter<string>(new StringWriter())));
		AddBinding(new TriggerBinding("paradox", "showRegistrationForm", ShowRegistrationForm));
		AddBinding(new TriggerBinding<string>("paradox", "showLink", ShowLink));
		AddBinding(new TriggerBinding<RegistrationFormData>("paradox", "submitRegistrationForm", SubmitRegistrationForm, new ValueReader<RegistrationFormData>()));
		AddBinding(new TriggerBinding("paradox", "confirmAccountLink", ConfirmAccountLink));
		AddBinding(new TriggerBinding("paradox", "confirmAccountLinkOverwrite", ConfirmAccountLinkOverwrite));
		AddBinding(new TriggerBinding("paradox", "markLegalDocumentAsViewed", MarkLegalDocumentAsViewed));
		AddBinding(new TriggerBinding("paradox", "showTermsOfUse", ShowTermsOfUse));
		AddBinding(new TriggerBinding("paradox", "showPrivacyPolicy", ShowPrivacyPolicy));
		AddBinding(new TriggerBinding<int>("paradox", "onOptionSelected", OnOptionSelected));
		AddBinding(m_IsPDXSDKEnabled = new ValueBinding<bool>("paradox", "pdxSDKEnabled", initialValue: false));
		m_PdxPlatform = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		PlatformManager.instance.onPlatformRegistered += delegate(IPlatformServiceIntegration psi)
		{
			if (psi is PdxSdkPlatform pdxPlatform)
			{
				m_PdxPlatform = pdxPlatform;
				m_PdxPlatform.onLoggedIn += OnUserLoggedIn;
				m_PdxPlatform.onLoggedOut += OnUserLoggedOut;
				m_PdxPlatform.onAccountLinkChanged += OnAccountLinkChanged;
				m_PdxPlatform.onLegalDocumentStatusChanged += OnLegalDocumentStatusChanged;
				m_PdxPlatform.onStatusChanged += OnStatusChanged;
			}
		};
		PlatformManager.instance.onConnectivityStatusChanged += OnInternetConnectionStatusChanged;
	}
```


## Methods

- `private <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <.ctor>b__17_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private CloseActiveDialog() : System.Void`  

```csharp
private void CloseActiveDialog()
	{
		if (!m_RequestActiveBinding.value && !(m_ActiveDialogsBinding.Peek() is LegalDocumentDialog { agreementRequired: not false }))
		{
			m_ActiveDialogsBinding.Pop();
			if (m_ActiveDialogsBinding.count == 0)
			{
				PlatformManager.instance.EnableSharing();
			}
		}
	}
```

- `private ConfirmAccountLink() : System.Void`  

```csharp
private async void ConfirmAccountLink()
	{
		if (m_RequestActiveBinding.value)
		{
			return;
		}
		if (m_PdxPlatform.AccountLinkMismatch == AccountLinkMismatch.None)
		{
			PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.LinkAccount());
			if (requestReport == null)
			{
				m_AccountLinkStateBinding.Update(2);
				m_ActiveDialogsBinding.ClearAndPush(new ConfirmationDialog(GetAccountLinkProviderIcon(), "Paradox.ACCOUNT_LINK_PROMPT_TITLE", $"Paradox.ACCOUNT_LINK_CONFIRMATION_TEXT[{m_PdxPlatform.accountLinkProvider:G}]", null));
			}
			else
			{
				m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
			}
		}
		else
		{
			string messageId = m_PdxPlatform.AccountLinkMismatch switch
			{
				AccountLinkMismatch.Paradox => $"Paradox.PDX_ACCOUNT_LINK_OVERWRITE_PROMPT_TEXT[{m_PdxPlatform.accountLinkProvider:G}]", 
				AccountLinkMismatch.ThirdParty => $"Paradox.PLATFORM_ACCOUNT_LINK_OVERWRITE_PROMPT_TEXT[{m_PdxPlatform.accountLinkProvider:G}]", 
				AccountLinkMismatch.Both => $"Paradox.PDX_PLATFORM_ACCOUNT_LINK_OVERWRITE_PROMPT_TEXT[{m_PdxPlatform.accountLinkProvider:G}]", 
				_ => null, 
			};
			m_ActiveDialogsBinding.Push(new AccountLinkOverwriteDialog(GetAccountLinkProviderIcon(), messageId));
		}
	}
```

- `private ConfirmAccountLinkOverwrite() : System.Void`  

```csharp
private async void ConfirmAccountLinkOverwrite()
	{
		if (!m_RequestActiveBinding.value)
		{
			PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.OverwriteAccountLinks());
			if (requestReport == null)
			{
				m_AccountLinkStateBinding.Update(2);
				m_ActiveDialogsBinding.ClearAndPush(new ConfirmationDialog(GetAccountLinkProviderIcon(), "Paradox.ACCOUNT_LINK_PROMPT_TITLE", $"Paradox.ACCOUNT_LINK_CONFIRMATION_TEXT[{m_PdxPlatform.accountLinkProvider:G}]", null));
			}
			else
			{
				m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
			}
		}
	}
```

- `private GetAccountLinkProviderIcon() : System.String`  

```csharp
private string GetAccountLinkProviderIcon()
	{
		return $"Media/Menu/Platforms/{m_PdxPlatform.accountLinkProvider:G}.svg";
	}
```

- `private GetCountryCodes() : System.Collections.Generic.List<System.String>`  

```csharp
private List<string> GetCountryCodes()
	{
		List<string> list = new List<string>(Enum.GetNames(typeof(Country)));
		list.Remove(Country.Undefined.ToString());
		return list;
	}
```

- `private LinkAccount() : System.Void`  

```csharp
private void LinkAccount()
	{
		m_ActiveDialogsBinding.Push(new AccountLinkDialog(GetAccountLinkProviderIcon(), $"Paradox.ACCOUNT_LINK_PROMPT_TEXT[{m_PdxPlatform.accountLinkProvider:G}]"));
	}
```

- `private Logout() : System.Void`  

```csharp
private async void Logout()
	{
		await m_PdxPlatform.Logout();
	}
```

- `private MarkLegalDocumentAsViewed() : System.Void`  

```csharp
private async void MarkLegalDocumentAsViewed()
	{
		if (m_ActiveDialogsBinding.Peek() is LegalDocumentDialog { document: var document })
		{
			await RunForegroundRequest(m_PdxPlatform.MarkLegalDocumentAsViewed(document));
		}
	}
```

- `private OnAccountLinkChanged(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider) : System.Void`  

```csharp
private void OnAccountLinkChanged(AccountLinkState state, AccountLinkProvider provider)
	{
		m_AccountLinkProviderBinding.Update(provider);
		m_AccountLinkStateBinding.Update((int)state);
	}
```

- `private OnInternetConnectionStatusChanged(System.Boolean connected) : System.Void`  

```csharp
private void OnInternetConnectionStatusChanged(bool connected)
	{
		m_HasInternetConnection.Update(connected);
	}
```

- `private OnLegalDocumentStatusChanged(Colossal.PSI.PdxSdk.LegalDocument doc, System.Int32 remainingCount) : System.Void`  

```csharp
private void OnLegalDocumentStatusChanged(LegalDocument doc, int remainingCount)
	{
		if (m_ActiveDialogsBinding.Peek() is LegalDocumentDialog)
		{
			m_ActiveDialogsBinding.Pop();
		}
		if (doc != null)
		{
			m_ActiveDialogsBinding.Push(new LegalDocumentDialog(doc));
		}
	}
```

- `private OnOptionSelected(System.Int32 index) : System.Void`  

```csharp
private void OnOptionSelected(int index)
	{
		if (m_ActiveDialogsBinding.Peek() is MultiOptionDialog multiOptionDialog)
		{
			m_ActiveDialogsBinding.Pop();
			multiOptionDialog.m_Options[index].m_OnSelect?.Invoke();
		}
	}
```

- `public OnPSModsUIClosed(System.Action onKeepMods, System.Action onDisableMods, System.Action onBack) : System.Void`  

```csharp
public void OnPSModsUIClosed(Action onKeepMods, Action onDisableMods, Action onBack)
	{
		m_ActiveDialogsBinding.Push(new MultiOptionDialog("Menu.PDX_MODS", "Paradox.PS_MODS_EXIT_DISCLAIMER", new MultiOptionDialog.Option
		{
			m_Id = "Paradox.PS_MODS_EXIT_KEEP_MODS",
			m_OnSelect = onKeepMods
		}, new MultiOptionDialog.Option
		{
			m_Id = "Paradox.PS_MODS_EXIT_DISABLE_MODS",
			m_OnSelect = onDisableMods
		}, new MultiOptionDialog.Option
		{
			m_Id = "Paradox.PS_MODS_EXIT_GO_BACK",
			m_OnSelect = onBack
		}));
	}
```

- `public OnPSModsUIOpened(System.Action onContinue) : System.Void`  

```csharp
public void OnPSModsUIOpened(Action onContinue)
	{
		m_ActiveDialogsBinding.Push(new MultiOptionDialog("Menu.PDX_MODS", "Paradox.PS_MODS_DISCLAIMER", new MultiOptionDialog.Option
		{
			m_Id = "Common.OK",
			m_OnSelect = onContinue
		}));
	}
```

- `private OnStatusChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private void OnStatusChanged(IPlatformServiceIntegration psi)
	{
		if (psi == m_PdxPlatform)
		{
			m_IsPDXSDKEnabled.Update(m_PdxPlatform.isInitialized);
			m_AccountLinkProviderBinding.Update(m_PdxPlatform.accountLinkProvider);
			m_AccountLinkStateBinding.Update((int)m_PdxPlatform.accountLinkState);
		}
	}
```

- `private OnUserLoggedIn(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime) : System.Void`  

```csharp
private async void OnUserLoggedIn(string firstName, string lastName, string email, AccountLinkState accountLinkState, bool firstTime)
	{
		m_LoggedInBinding.Update(newValue: true);
		m_AccountLinkStateBinding.Update((int)accountLinkState);
		m_EmailBinding.Update(email);
		ModCreator modCreator = await m_PdxPlatform.GetCreatorProfile();
		if (modCreator != null)
		{
			m_UserNameBinding.Update(modCreator.Username);
			m_AvatarBinding.Update(modCreator.Avatar.Url);
		}
	}
```

- `private OnUserLoggedOut(System.String id) : System.Void`  

```csharp
private void OnUserLoggedOut(string id)
	{
		m_UserNameBinding.Update(null);
		m_EmailBinding.Update(null);
		m_AvatarBinding.Update(null);
		m_LoggedInBinding.Update(newValue: false);
	}
```

- `public PushDialog(Game.UI.Menu.ParadoxBindings+ParadoxDialog dialog) : System.Void`  

```csharp
public void PushDialog(ParadoxDialog dialog)
	{
		m_ActiveDialogsBinding.Push(dialog);
	}
```

- `private RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task) : System.Threading.Tasks.Task<T>`  

```csharp
private System.Threading.Tasks.Task<T> RunForegroundRequest<T>(System.Threading.Tasks.Task<T> task);
```

- `private ShowLink(System.String link) : System.Void`  

```csharp
private async void ShowLink(string link)
	{
		if (link == kTermsOfUse)
		{
			LegalDocument legalDocument = await RunForegroundRequest(m_PdxPlatform.ShowTermsOfUse());
			if (legalDocument != null)
			{
				m_ActiveDialogsBinding.Push(new LegalDocumentDialog(legalDocument, agreementRequired: false));
			}
		}
		else if (link == kPrivacyPolicy)
		{
			LegalDocument legalDocument2 = await RunForegroundRequest(m_PdxPlatform.ShowPrivacyPolicy());
			if (legalDocument2 != null)
			{
				m_ActiveDialogsBinding.Push(new LegalDocumentDialog(legalDocument2, agreementRequired: false));
			}
		}
		else
		{
			Application.OpenURL(link);
		}
	}
```

- `public ShowLoginForm() : System.Void`  

```csharp
public void ShowLoginForm()
	{
		if (Connectivity.hasConnectivity)
		{
			PlatformManager.instance.DisableSharing();
			m_ActiveDialogsBinding.ClearAndPush(new LoginDialog());
		}
		else
		{
			m_ActiveDialogsBinding.Push(new ErrorDialog("Failed to connect", "Please check your internet connection"));
		}
	}
```

- `private ShowPrivacyPolicy() : System.Void`  

```csharp
private void ShowPrivacyPolicy()
	{
		ShowLink(kPrivacyPolicy);
	}
```

- `private ShowRegistrationForm() : System.Void`  

```csharp
private void ShowRegistrationForm()
	{
		m_ActiveDialogsBinding.ClearAndPush(new RegistrationDialog());
	}
```

- `private ShowTermsOfUse() : System.Void`  

```csharp
private void ShowTermsOfUse()
	{
		ShowLink(kTermsOfUse);
	}
```

- `private SubmitLoginForm(Game.UI.Menu.ParadoxBindings+LoginFormData data) : System.Void`  

```csharp
private async void SubmitLoginForm(LoginFormData data)
	{
		if (m_RequestActiveBinding.value)
		{
			return;
		}
		PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.Login(data.email, data.password, CancellationToken.None));
		if (requestReport == null)
		{
			m_ActiveDialogsBinding.Clear();
			if (m_PdxPlatform.accountLinkProvider != AccountLinkProvider.Unknown && m_PdxPlatform.accountLinkState == AccountLinkState.Unlinked)
			{
				LinkAccount();
			}
		}
		else
		{
			m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
		}
	}
```

- `private SubmitPasswordReset(System.String email) : System.Void`  

```csharp
private async void SubmitPasswordReset(string email)
	{
		if (!m_RequestActiveBinding.value)
		{
			PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.ResetPassword(email));
			if (requestReport == null)
			{
				m_ActiveDialogsBinding.Push(new ConfirmationDialog(null, null, "Paradox.PASSWORD_RESET_CONFIRMATION_TEXT", new Dictionary<string, string> { { "EMAIL", email } }));
			}
			else
			{
				m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
			}
		}
	}
```

- `private SubmitRegistrationForm(Game.UI.Menu.ParadoxBindings+RegistrationFormData data) : System.Void`  

```csharp
private async void SubmitRegistrationForm(RegistrationFormData data)
	{
		if (m_RequestActiveBinding.value)
		{
			return;
		}
		if (Enum.TryParse<Country>(data.country, out var result) && DateTime.TryParseExact(data.dateOfBirth, "yyyy-MM-dd", CultureInfo.InvariantCulture, DateTimeStyles.None, out var result2))
		{
			PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.CreateParadoxAccount(data.email, data.password, Language.en, result, result2, data.marketingPermission));
			if (requestReport == null)
			{
				m_ActiveDialogsBinding.Clear();
				if (m_PdxPlatform.accountLinkProvider != AccountLinkProvider.Unknown && m_PdxPlatform.accountLinkState == AccountLinkState.Unlinked)
				{
					LinkAccount();
				}
				m_ActiveDialogsBinding.Push(new ConfirmationDialog(null, "Paradox.REGISTRATION_CONFIRMATION_TITLE", "Paradox.REGISTRATION_CONFIRMATION_TEXT", null));
			}
			else
			{
				m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
			}
		}
		else
		{
			m_ActiveDialogsBinding.Push(new ErrorDialog(null, "Internal error: Invalid Country Code string or Invalid date string"));
		}
	}
```

- `private UnlinkAccount() : System.Void`  

```csharp
private async void UnlinkAccount()
	{
		if (!m_RequestActiveBinding.value)
		{
			PdxSdkPlatform.RequestReport requestReport = await RunForegroundRequest(m_PdxPlatform.UnlinkThirdPartyAccount());
			if (requestReport == null)
			{
				m_AccountLinkStateBinding.Update(1);
			}
			else
			{
				m_ActiveDialogsBinding.Push(new ErrorDialog(requestReport.messageId, requestReport.message));
			}
		}
	}
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

