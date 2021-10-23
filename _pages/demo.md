---
layout: page
title: Demo
---

<!-- A minimal structure for the ScreenAdapter defined in browser/screen.js -->
<div id="screen_container">
    <div id="screen"></div>
    <canvas id="vga"></canvas>
</div>

<!-- Initialize v86 -->
<script src="/js/libv86.js"/>
</script>
<script>
"use strict";

window.onload = function () {
    var emulator = window.emulator = new V86Starter({
        wasm_path: "/v86.wasm",
        memory_size: 512 * 1024 * 1024,
        vga_memory_size: 8 * 1024 * 1024,
        screen_container: document.getElementById("screen_container"),
        bios:
        {
            url: "https://github.com/XyrisOS/website/blob/main/bios/seabios.bin?raw=true",
        },
        vga_bios:
        {
            url: "https://github.com/XyrisOS/website/blob/main//bios/vgabios.bin?raw=true",
        },
        hda:
        {
            url: "https://github.com/XyrisOS/website/blob/main/res/xyris.img?raw=true",
            async: true,
        },
        autostart: true,
    });
}
</script>
