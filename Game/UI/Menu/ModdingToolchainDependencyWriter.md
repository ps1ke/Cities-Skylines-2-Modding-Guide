# Game.UI.Menu.ModdingToolchainDependencyWriter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IWriter<Game.Modding.Toolchain.IToolchainDependency>`  

## Code

```csharp
public class ModdingToolchainDependencyWriter : Colossal.UI.Binding.IWriter<Game.Modding.Toolchain.IToolchainDependency>
{
    public ModdingToolchainDependencyWriter();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, Game.Modding.Toolchain.IToolchainDependency value);
}
```


## Constructors

- `public ModdingToolchainDependencyWriter()`  

```csharp
public ModdingToolchainDependencyWriter();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer, Game.Modding.Toolchain.IToolchainDependency value) : System.Void`  

```csharp
public void Write(IJsonWriter writer, IToolchainDependency value)
	{
		if (value != null)
		{
			writer.TypeBegin(value.GetType().FullName);
			writer.PropertyName("name");
			writer.Write(value.localizedName);
			writer.PropertyName("state");
			writer.Write((int)value.state.m_State);
			writer.PropertyName("progress");
			writer.Write(value.state.m_Progress ?? (-1));
			writer.PropertyName("details");
			writer.Write(value.GetLocalizedState(includeProgress: false));
			writer.PropertyName("version");
			writer.Write(value.GetLocalizedVersion());
			writer.PropertyName("icon");
			writer.Write(value.icon);
			writer.TypeEnd();
			return;
		}
		writer.WriteNull();
		throw new ArgumentNullException("value", "Null passed to non-nullable value writer");
	}
```


