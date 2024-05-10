## Yabai Configuration Guide

This README details the configuration settings for Yabai, a tiling window manager for macOS. This configuration includes adjustments to the layout, padding, gaps, mouse actions, auto-balancing, and specific rules for managing application windows.

### Configuration Details

#### Layout Settings

- **Layout Type**: Binary Space Partitioning (`bsp`)
  ```sh
  yabai -m config layout bsp
  ```

#### Padding and Gaps

- **Padding**: All padding set to 10pt for top, bottom, left, and right.
- **Window Gaps**: Default gap between windows set to 10pt.
  ```sh
  yabai -m config top_padding    10
  yabai -m config bottom_padding 10
  yabai -m config left_padding   10
  yabai -m config right_padding  10
  yabai -m config window_gap     10
  ```

- **Override Gaps for Space 2**: Window gap for space 2 is set to 0pt.
  ```sh
  yabai -m config --space 2 window_gap 0
  ```

#### Auto-Balance

- **Auto-Balance**: Enabled to automatically balance the size of the windows.
  ```sh
  yabai -m config auto_balance on
  ```

#### Mouse Actions

- **Mouse Modifier**: Set to the `fn` (Function) key.
- **Mouse Action 1**: Window move.
- **Mouse Action 2**: Window resize.
  ```sh
  yabai -m config mouse_modifier fn
  yabai -m config mouse_action1 move
  yabai -m config mouse_action2 resize
  ```

#### Rules for Window Management

- **Floating System Preferences**: Certain system applications and utilities are set not to be managed by Yabai, making them float over other windows instead of tiling.
  ```sh
  yabai -m rule --add app="^System Information$" manage=off
  yabai -m rule --add app="^System Settings$" manage=off
  yabai -m rule --add title='Preferences$' manage=off
  yabai -m rule --add title='^Archive Utility$' manage=off
  ```

- **Floating Settings Windows**: Additional settings windows are set to float.
  ```sh
  yabai -m rule --add title='Settings$' manage=off
  yabai -m rule --add title='^Extension' manage=off
  yabai -m rule --add app="^Alacritty$" manage=off
  ```

### Applying the Configuration

After setting up the configuration, apply the rules to make them effective.
```sh
yabai -m rule --apply
```

---

### Notes

1. **Installation**: Ensure Yabai is properly installed on your macOS before applying these configurations.
2. **Permissions**: Depending on your system's security settings, you might need to grant additional permissions for Yabai to control window management.

For more detailed information or troubleshooting, refer to the official [Yabai documentation](https://github.com/koekeishiya/yabai/wiki).