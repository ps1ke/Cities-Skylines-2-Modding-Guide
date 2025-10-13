# Game.Common.EnumValueAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

## Code

```csharp
public class EnumValueAttribute : UnityEngine.PropertyAttribute
{
    public System.String[] names;

    public EnumValueAttribute(System.Type type);

}
```


## Fields

- `public System.String[] names`  

```csharp
public System.String[] names;
```


## Constructors

- `public EnumValueAttribute(System.Type type)`  

```csharp
public EnumValueAttribute(Type type)
	{
		names = Enum.GetNames(type);
	}
```


