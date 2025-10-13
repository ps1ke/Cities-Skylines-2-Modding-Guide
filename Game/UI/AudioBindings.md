# Game.UI.AudioBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Code

```csharp
public class AudioBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup
{
    private Game.UISoundCollection m_SoundCollection;
    private static const System.String kGroup;

    public AudioBindings();

    private System.Void PlayUISound(System.String soundName, System.Single volume);
}
```


## Fields

- `private Game.UISoundCollection m_SoundCollection`  

```csharp
private Game.UISoundCollection m_SoundCollection;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public AudioBindings()`  

```csharp
public AudioBindings();
```


## Methods

- `private PlayUISound(System.String soundName, System.Single volume) : System.Void`  

```csharp
private System.Void PlayUISound(System.String soundName, System.Single volume);
```


