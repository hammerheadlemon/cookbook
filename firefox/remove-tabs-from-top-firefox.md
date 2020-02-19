To use the Tree Style Tab extension in firefox without having the tabs also at the top, the steps are:

1. Ensure there is a "chrome" directory inside the Firefox profile directory. On linux, this is at `/home/user/.mozilla/firefox/sdj8i9fjsdsdff/` (the latter string being a random string folder name containing all your profile stuff).
2. Paste the following into a new file in chrome called `userChrome.css`:

```css
@namespace url("http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul");

/* to hide the native tabs */
#TabsToolbar {
    visibility: collapse;
}

/* to hide the sidebar header */
#sidebar-header {
    visibility: collapse;
}
```

The latter bit is optional if you want to keep the title of the sidebar, which I do at this point.

3. Restart Firefox.

Reference for this is [here](https://www.reddit.com/r/firefox/comments/736cji/how_to_hide_native_tabs_in_firefox_57_tree_style/)

Mix this with the Dark theme and the Dark Background and Light text extension and you have a pretty nice dark-looking Firefox.
