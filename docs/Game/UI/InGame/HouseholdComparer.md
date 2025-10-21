# Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IComparer<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>`  

## Code

```csharp
public class HouseholdComparer : System.Collections.Generic.IComparer<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult>
{
    private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, System.Int32> m_Compare;

    public HouseholdComparer(Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer+CompareBy compareBy);

    public System.Int32 Compare(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult x, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult y);
}
```


## Fields

- `private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, System.Int32> m_Compare`  

```csharp
private readonly System.Func<Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult, System.Int32> m_Compare;
```


## Constructors

- `public HouseholdComparer(Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer+CompareBy compareBy)`  

```csharp
public HouseholdComparer(Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer+CompareBy compareBy);
```


## Methods

- `public Compare(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult x, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult y) : System.Int32`  

```csharp
public System.Int32 Compare(Game.UI.InGame.HouseholdSidebarSection+HouseholdResult x, Game.UI.InGame.HouseholdSidebarSection+HouseholdResult y);
```


## Nested types

- `Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer+CompareBy`  
- `Game.UI.InGame.HouseholdSidebarSection+HouseholdComparer+<>c`  

