# Using Themes

If you don't like the default style of Solar or would like to customize the colors to match your game, you can do so with Themes!

By default, Solar comes with one theme, which is our default theme.

Themes for Solar are located in the `Themes` folder under `Configuration` in the Solar folder

You can find community made themes in our [Discord server](https://discord.gg/AdjPbp3mRq) or on the [Themes](/community/themes) page

## Customizing the Default Theme

To customize the default theme, open up the `default.theme` module in the `Themes` folder.

```lua
return {
   Colors = {
      Background = Color3.fromRGB(38,38,38), --// Background Color of UI
      Accent = Color3.fromRGB(25, 150, 255), --// Accent Color of UI
      PrimaryText = Color3.fromRGB(240, 240, 240), --// Primary Text Color
      SuggestionText = Color3.fromRGB(186, 186, 186), --// Suggestion Text Color
      Divider = Color3.fromRGB(93, 93, 93),
   },
   Options = {
      Font = Enum.Font.RobotoMono, --// UI Font
      CornerRadius = UDim.new(0,8), --// Corner Radius of UI
      BackgroundOpacity = 0.15, --// Background Opacity of UI
   }
}

```

In the Colors table, you can customize almost all the colors of Solar's UI

Below that in the Options table, you can change the font, corner radius and background opacity of Solar's UI

You can customize these values to your liking

## Creating your own theme

If you want to keep the default theme & make additional themes, you can duplicate the default theme and then customize the duplicate module!

## Switching Themes

To switch the theme of Solar, open the `Settings` module and edit the `Theme` value to the location of your theme
