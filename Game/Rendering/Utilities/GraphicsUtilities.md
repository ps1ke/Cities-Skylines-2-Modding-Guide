# Game.Rendering.Utilities.GraphicsUtilities

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class GraphicsUtilities
{
    public static System.Void GenerateRandomWindowsTexture();
}
```


## Methods

- `public static GenerateRandomWindowsTexture() : System.Void`  

```csharp
public static void GenerateRandomWindowsTexture()
	{
		byte[] collection = new byte[25]
		{
			255, 245, 235, 224, 214, 204, 194, 184, 173, 163,
			153, 143, 133, 122, 112, 102, 92, 82, 71, 61,
			51, 41, 31, 20, 0
		};
		int num = 125;
		Texture2D texture2D = new Texture2D(num, num, TextureFormat.RGB24, mipChain: false);
		Color32[] pixels = texture2D.GetPixels32();
		int num2 = 0;
		int num3 = 0;
		for (int i = 0; i < 625; i++)
		{
			List<byte> list = new List<byte>(collection);
			Color32 color = ColorUtils.NiceRandomColor();
			for (int j = 0; j < 5; j++)
			{
				for (int k = 0; k < 5; k++)
				{
					int index = ((k != 0 || j != 0) ? ((k != 4 || j != 4) ? Random.Range(0, list.Count - 1) : (list.Count - 1)) : 0);
					pixels[num2 + k + (num3 + j) * num] = color;
					list.RemoveAt(index);
				}
			}
			num2 += 5;
			if (num2 == num)
			{
				num2 = 0;
				num3 += 5;
			}
		}
		texture2D.SetPixels32(pixels);
		File.WriteAllBytes(Path.Combine(Application.dataPath, "Art/Resources/Textures/WindowsIdxMapGeneratedDebug.png"), texture2D.EncodeToPNG());
		Object.DestroyImmediate(texture2D);
	}
```


