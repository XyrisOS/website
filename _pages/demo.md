---
layout: page
title: Demo
---

# This demo is very outdated

We are working on updating the demo image. Thank you for your patience.

<!-- A minimal structure for the ScreenAdapter defined in browser/screen.js -->
<div id="screen">
    <div style="white-space: pre; font: 12px monospace; line-height: 12px;"/>
    <canvas style="display: none"></canvas>
</div>

<!-- Initialize v86 -->
<script src="/js/libv86.js"></script>
<script>
"use strict";

window.onload = function () {
    var emulator = window.emulator = new V86Starter({
        wasm_path: "/v86.wasm",
        memory_size: 512 * 1024 * 1024,
        vga_memory_size: 8 * 1024 * 1024,
        screen_container: document.getElementById("screen"),
        bios:
        {
            url: "/bios/seabios.bin",
        },
        vga_bios:
        {
            url: "/bios/vgabios.bin",
        },
        cdrom:
        {
            url: "/res/xyris.iso",
            async: true,
        },
        autostart: true,
    });
}
</script>
