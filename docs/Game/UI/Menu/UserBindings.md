# Game.UI.Menu.UserBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SwitchPromptVisible`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_AvatarBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_UserIDBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_SwitchUserHintOverload`  
- `private static System.Int32 s_AvatarVersion`  
- `private static const System.String kGroup`  

## Constructors

- `public UserBindings()`  

## Methods

- `private <.ctor>b__6_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `private <.ctor>b__6_1(Colossal.PSI.Common.IUserSupport psi, Colossal.PSI.Common.UserChangedFlags flags) : System.Void`  
- `public Dispose() : System.Void`  
- `public getSwitchUserHintOverload() : System.String`  
- `private OnMainMenuReached(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `private SwitchUser() : System.Void`  

