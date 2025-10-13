# Game.UI.Menu.UserBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class UserBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SwitchPromptVisible;
    private Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_UserIDBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SwitchUserHintOverload;
    private static System.Int32 s_AvatarVersion;
    private static const System.String kGroup;

    public UserBindings();

    private System.Void <.ctor>b__6_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    private System.Void <.ctor>b__6_1(Colossal.PSI.Common.IUserSupport psi, Colossal.PSI.Common.UserChangedFlags flags);
    public System.Void Dispose();
    public System.String getSwitchUserHintOverload();
    private System.Void OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    private System.Void SwitchUser();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SwitchPromptVisible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SwitchPromptVisible;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_UserIDBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_UserIDBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SwitchUserHintOverload`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SwitchUserHintOverload;
```

- `private static System.Int32 s_AvatarVersion`  

```csharp
private static System.Int32 s_AvatarVersion;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public UserBindings()`  

```csharp
public UserBindings()
	{
		GameManager.instance.onGameLoadingComplete += OnMainMenuReached;
		AddBinding(m_SwitchPromptVisible = new ValueBinding<bool>("user", "switchPromptVisible", !GameManager.instance.configuration.disableUserSection && (PlatformManager.instance.supportsUserSwitching || PlatformManager.instance.supportsUserSection)));
		string initialValue = string.Format("{0}/UserAvatar#{1}?size={2}", "useravatar://", s_AvatarVersion++, AvatarSize.Auto);
		AddBinding(m_AvatarBinding = new ValueBinding<string>("user", "avatar", initialValue, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_UserIDBinding = new ValueBinding<string>("user", "userID", PlatformManager.instance.userName, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_SwitchUserHintOverload = new ValueBinding<string>("user", "switchUserHintOverload", getSwitchUserHintOverload(), ValueWriters.Nullable(new StringWriter())));
		AddBinding(new TriggerBinding("user", "switchUser", SwitchUser));
		PlatformManager.instance.onStatusChanged += delegate(IPlatformServiceIntegration psi)
		{
			if (PlatformManager.instance.IsPrincipalOverlayIntegration(psi))
			{
				m_SwitchPromptVisible.Update(!GameManager.instance.configuration.disableUserSection && (PlatformManager.instance.supportsUserSwitching || PlatformManager.instance.supportsUserSection));
			}
		};
		PlatformManager.instance.onUserUpdated += delegate(IUserSupport psi, UserChangedFlags flags)
		{
			if (PlatformManager.instance.IsPrincipalUserIntegration(psi))
			{
				if (flags.HasChanged(UserChangedFlags.Name))
				{
					m_UserIDBinding.Update(PlatformManager.instance.userName);
				}
				if (flags.HasChanged(UserChangedFlags.Avatar))
				{
					m_AvatarBinding.Update(string.Format("{0}/UserAvatar#{1}?size={2}", "useravatar://", s_AvatarVersion++, AvatarSize.Auto));
				}
			}
		};
	}
```


## Methods

- `private <.ctor>b__6_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <.ctor>b__6_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `private <.ctor>b__6_1(Colossal.PSI.Common.IUserSupport psi, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  

```csharp
private System.Void <.ctor>b__6_1(Colossal.PSI.Common.IUserSupport psi, Colossal.PSI.Common.UserChangedFlags flags);
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		GameManager.instance.onGameLoadingComplete -= OnMainMenuReached;
	}
```

- `public getSwitchUserHintOverload() : System.String`  

```csharp
public string getSwitchUserHintOverload()
	{
		if (PlatformManager.instance.supportsUserSwitching)
		{
			return null;
		}
		return "Steam Overlay";
	}
```

- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private void OnMainMenuReached(Purpose purpose, GameMode mode)
	{
		if (mode == GameMode.MainMenu)
		{
			m_SwitchPromptVisible.Update(!GameManager.instance.configuration.disableUserSection && (PlatformManager.instance.supportsUserSwitching || PlatformManager.instance.supportsUserSection));
		}
	}
```

- `private SwitchUser() : System.Void`  

```csharp
private void SwitchUser()
	{
		if (m_SwitchPromptVisible.value)
		{
			PlatformManager instance = PlatformManager.instance;
			if (instance.supportsUserSwitching)
			{
				GameManager.instance.SetScreenActive<SwitchUserScreen>();
			}
			else if (instance.supportsUserSection)
			{
				instance.ShowOverlay(Page.Community);
			}
		}
	}
```


