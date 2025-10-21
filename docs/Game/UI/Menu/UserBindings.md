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
public UserBindings();
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
public System.Void Dispose();
```

- `public getSwitchUserHintOverload() : System.String`  

```csharp
public System.String getSwitchUserHintOverload();
```

- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
private System.Void OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `private SwitchUser() : System.Void`  

```csharp
private System.Void SwitchUser();
```


