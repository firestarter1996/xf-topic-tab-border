# 🗂️🔵 Topic Tab Border

A Nagram XF plugin that draws an outline in your accent color around the open topic in the topic tabs of a forum, like the Media, Files and Links switch on a profile. The tab keeps its normal light fill; the outline is added on top and follows the slide between tabs.

## Install

1. Download `topic_tab_border.plugin` from the latest release.
2. Send it to yourself in Nagram XF and tap it, or open it from Settings, Plugins.
3. Turn it on. Settings: on or off, and border width (Thin, Medium, Thick).

## What's new in 1.0.8 (11-08-2026)

Fixes Nagram XF force closing a few seconds after it opened. The plugin defined its own Java Runnable class while it loaded. Chaquopy gives every Python Runnable the same Java class and points it at the newest Python class before that class is finished, so another plugin's Runnable that ran on the main thread or the storage queue in that moment was rebuilt through the unfinished class and the app died with `AttributeError: '_Fix' object has no attribute '_chaquopyGetType'`. Now the plugin uses the SDK's own Runnable, makes one at load and reuses it for every fix, removes it on unload, never lets an error reach Java, and installs its hooks on the UI thread.

## What's new in 1.0.7

The open Usage tab could show its blue label and light fill with no outline. The outline is now never skipped while the app itself marks a tab as open: if the plugin's own lookup comes up empty, it outlines the tab the app marked.

## What's new in 1.0.6

A topic tab could stay bold and blue after you left it, as if it were still open. The outline then went missing on that topic and on the one you opened. The outline now follows the topic that is really open, and any tab still showing itself as open gets set back to normal right after the frame it was seen in. Only the open topic is ever bold, blue and outlined.

## Speed

The outline is drawn inside the tab strip's own draw pass, which only runs when the strip changes. There are no timers, no polling and no extra redraws: a few Java calls per frame while the tabs move, and settings are read at most twice a second. A stuck tab is fixed once and costs nothing after.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=firestarter1996/xf-topic-tab-border&type=Date)](https://star-history.com/#firestarter1996/xf-topic-tab-border&Date)
