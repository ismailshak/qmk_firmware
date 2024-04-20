# Notes

Jotting down things so I don't forget how I did stuff

## Pulling latest from upstream

1. Be on master `git checkout master`
2. Pull latest `git fetch upstream`
3. Merge upstream `git merge upstream/master`
4. Update submodules `git submodule update --init --recursive`
5. Push sync `git push origin HEAD`
6. Checkout feature branch `git checkout dev`
7. Rebase master `git rebase master` (Use alias so committer date is author date)
8. Push updated feature branch `git push origin HEAD`

## Current QMK Config

`qmk config` output

```shell
find.keymap=default
mass_compile.keymap=default
user.keyboard=crkbd
user.keymap=ismailshak
user.qmk_home=<path-to-cloned-repo>
```

## Building Firmware

Since `user.*` defaults are assigned to `qmk config`, it's just `qmk compile` to build the firmware

## Flashing Keyboard

Use the QMK Toolbox GUI. Open it up, and find the `.hex` generated from the previous step.

1. Select the appropriate firmware from the dropdown (or 'Open' one)
2. Unplug left half from USB-C and unplug right half from left half
3. Plug in the left half to the USB-C cable
4. Press the physical Reset button (under the display). You should see that QMK Toolbox print a message that it detected it connecting
5. Click the Flash button in QMK Toolbox and wait until the tool says the keyboard disconnected
6. Repeat steps 3-5 but for the right half
7. Profit
