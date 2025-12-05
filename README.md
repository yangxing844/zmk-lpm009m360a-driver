zmk display driver called lpm_view driver based on lpm009m360a jdi display
to use this module with nice_view pin out, first define `lpm_view_spi` in your keyboard.dts
```c++
lpm_view_spi: &<your spi bus> {
    compatible = "nordic,nrf-spim";
    pinctrl-0 = <&spi2_default>;
    pinctrl-1 = <&spi2_sleep>;
    pinctrl-names = "default", "sleep";
    cs-gpios = <&gpio0 26 (GPIO_ACTIVE_HIGH | GPIO_PULL_DOWN) >;
};
```
change gpio to your corresponding io

then copy  `lpm_view` folder in `config/boards/shields/lpm_view` in `https://github.com/yangxing844/zmk-config/tree/master/config/boards/shields/lpm_view` to your keyboard shields

next, build with lpm_view shield in `build.yaml`

```c++
- board: polaris_left
    shield: lpm_view

```

