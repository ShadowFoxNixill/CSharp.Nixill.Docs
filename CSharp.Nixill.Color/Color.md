```csharp
public struct Color
```

# Summary
Represents a single color.



# Constructors


## `Color()`
Creates a new `Color` with the default parameters (transparent black).


## `Color(float, float, float)`
Creates a new, opaque `Color` with the specified red, green, and blue levels (in sRGB color space).

### Parameters
* `float` **`red`**: The amount of red to use in the color.
* `float` **`green`**: The amount of green to use in the color.
* `float` **`blue`**: The amount of blue to use in the color.


## `Color(float, float, float, float)`
Creates a new `Color` with the specified red, green, and blue levels (in sRGB color space).

### Parameters
* `float` **`red`**: The amount of red to use in the color.
* `float` **`green`**: The amount of green to use in the color.
* `float` **`blue`**: The amount of blue to use in the color.
* `float` **`alpha`**: The opacity of the color.



# Properties


## `Alpha`
`float`: The opacity of the `Color`.


## `Blue`
`float`: The sRGB blue content of the `Color`.


## `Green`
`float`: The sRGB green content of the `Color`.


## `LinearBlue`
`float`: The linear blue content of the `Color`.


## `LinearGreen`
`float`: The linear green content of the `Color`.


## `LinearRed`
`float`: The linear red content of the `Color`.


## `Red`
`float`: The sRGB red content of the `Color`.
