## Tokyo Night Theme for VT 

Archlinux [mkinitcpio](https://wiki.archlinux.org/index.php/mkinitcpio) hook to
set the `Virtual Console` colors during early userspace.

This would mean, applications like `tuigreetd` or `tty` have your wanted colors! :)

Depends on [linux-vt-setcolors](https://github.com/evanpurkhiser/linux-vt-setcolors).

### Usage

Copy the files:

- `install/*` to `/etc/initcpio/install/`
- `hooks/*` to `/etc/initcpio/hooks/`
- `setcolors.service` to `/etc/systemd/system/`
- Paste the contents of `vconsole-colors.txt` (Tokyo Night Theme's color values in the right format) to the end of `/etc/vconsole.conf` 

Then, add to `HOOKS` in `/etc/mkinitcpio.conf` either `colors` (if using `udev`) or `sd-colors` (if using `systemd`).
You can see what you use in the `HOOKS` mentioned in the `/etc/mkinitcpio.conf`.

Regenerate the `initramfs` to apply the changes by running `sudo mkinitcpio -p linux` (or whatever kernel you use besides `linux`).
