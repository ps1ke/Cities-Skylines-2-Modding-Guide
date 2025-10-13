# Game.UI.InGame.ISubsectionProvider

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** interface abstract public  

**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface ISubsectionProvider : Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; }

}
```


## Properties

- `public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; }
```


