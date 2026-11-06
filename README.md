# 🗂️🔵 Topic Tab Border

A Nagram XF plugin that draws an outline in your accent color around the open topic in the topic tabs of a forum, like the Media, Files and Links switch on a profile. The tab keeps its normal light fill; the outline is added on top and follows the slide between tabs.

## Install

1. Download `topic_tab_border.plugin` from the latest release.
2. Send it to yourself in Nagram XF and tap it, or open it from Settings, Plugins.
3. Turn it on. Settings: on or off, and border width (Thin, Medium, Thick).

## What's new in 1.0.6

A topic tab could stay bold and blue after you left it, as if it were still open. The outline then went missing on that topic and on the one you opened. The outline now follows the topic that is really open, and any tab still showing itself as open gets set back to normal right after the frame it was seen in. Only the open topic is ever bold, blue and outlined.

## Speed

The outline is drawn inside the tab strip's own draw pass, which only runs when the strip changes. There are no timers, no polling and no extra redraws: a few Java calls per frame while the tabs move, and settings are read at most twice a second. A stuck tab is fixed once and costs nothing after.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=firestarter1996/xf-topic-tab-border&type=Date)](https://star-history.com/#firestarter1996/xf-topic-tab-border&Date)
