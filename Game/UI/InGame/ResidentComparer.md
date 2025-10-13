# Game.UI.InGame.HouseholdSidebarSection+ResidentComparer

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IComparer<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>`  

## Code

```csharp
public class ResidentComparer : System.Collections.Generic.IComparer<Game.UI.InGame.HouseholdSidebarSection+ResidentResult>
{
    private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+ResidentResult, Game.UI.InGame.HouseholdSidebarSection+ResidentResult, System.Int32> m_Compare;

    public ResidentComparer(Game.UI.InGame.HouseholdSidebarSection+ResidentComparer+CompareBy compareBy);

    public System.Int32 Compare(Game.UI.InGame.HouseholdSidebarSection+ResidentResult x, Game.UI.InGame.HouseholdSidebarSection+ResidentResult y);
}
```


## Fields

- `private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+ResidentResult, Game.UI.InGame.HouseholdSidebarSection+ResidentResult, System.Int32> m_Compare`  

```csharp
private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+ResidentResult, Game.UI.InGame.HouseholdSidebarSection+ResidentResult, System.Int32> m_Compare;
```


## Constructors

- `public ResidentComparer(Game.UI.InGame.HouseholdSidebarSection+ResidentComparer+CompareBy compareBy)`  

```csharp
public ResidentComparer(Game.UI.InGame.HouseholdSidebarSection+ResidentComparer+CompareBy compareBy);
```


## Methods

- `public Compare(Game.UI.InGame.HouseholdSidebarSection+ResidentResult x, Game.UI.InGame.HouseholdSidebarSection+ResidentResult y) : System.Int32`  

```csharp
public System.Int32 Compare(Game.UI.InGame.HouseholdSidebarSection+ResidentResult x, Game.UI.InGame.HouseholdSidebarSection+ResidentResult y);
```


## Nested types

- `Game.UI.InGame.HouseholdSidebarSection+ResidentComparer+CompareBy`  
- `Game.UI.InGame.HouseholdSidebarSection+ResidentComparer+<>c`  

