**Personal customization goals:**
- add links to all metadata on title page like with ao3 export — DONE, see [v31](https://github.com/natruok/FanFicFare/releases/tag/v31)
- create separate summary page that also shows up in TOC — DONE [v31](https://github.com/natruok/FanFicFare/releases/tag/v31)
- create separate afterword page that also showd up in TOC for overall work end notes — DONE, see [v44](https://github.com/natruok/FanFicFare/releases/tag/v44)
- separate overall author head notes into summary page rather than at beginning of ch 1 — DONE, see [v45](https://github.com/natruok/FanFicFare/releases/tag/v45)
- fix consistency of title headings — DONE, see [v46](https://github.com/natruok/FanFicFare/releases/tag/v46)
- separate work end notes into afterword page rather than end of chapter — DONE, see [v50](https://github.com/natruok/FanFicFare/releases/tag/v50)
- afterword page to show up only if there are overall end notes — DONE, see [v48](https://github.com/natruok/FanFicFare/releases/tag/v48)
- summary page to show horizontal line for line break and author's note — DONE, see [v48](https://github.com/natruok/FanFicFare/releases/tag/v48)
- summary page to show horizontal line for line break and author's note only if it exists — DONE, see [v49](https://github.com/natruok/FanFicFare/releases/tag/v49)
- make new summary & afternote pages configurable in personal.ini — DONE, see [v50](https://github.com/natruok/FanFicFare/releases/tag/v50)
- add line break between chapter head & foot notes — DONE, see [v51](https://github.com/natruok/FanFicFare/releases/tag/v51)
- strip chapter titles & redo only if the chapter isn't named "Chapter #"
- update series naming to "Part # of xxx", but keep indexing by series name



<hr/>



[FanFicFare](https://github.com/JimmXinu/FanFicFare)
==========

FanFicFare makes reading stories from various websites much easier by helping
you download them to EBook files.

FanFicFare was previously known as FanFictionDownLoader (AKA
FFDL, AKA fanficdownloader).

Main features:

- Download FanFiction stories from over [100 different sites](https://github.com/JimmXinu/FanFicFare/wiki/SupportedSites). into ebooks.

- Update previously downloaded EPUB format ebooks, downloading only new chapters.

- Get Story URLs from Web Pages.

- Support for downloading images in the story text. (EPUB and HTML
  only -- download EPUB and convert to AZW3 for Kindle) More details on
  configuring images in stories and cover images can be found in the
  [FAQs] or [this post in the old FFDL thread].

- Support for cover image. (EPUB only)

- Optionally keep an Update Log of past updates (EPUB only).

There's additional info in the project [wiki] pages.

There's also a [FanFicFare maillist] for discussion and announcements and a [discussion thread] for the Calibre plugin.

Getting FanFicFare
==================

### Official Releases

This program is available as:

- A Calibre plugin from within Calibre or directly from the plugin [discussion thread], or;
- A Command Line Interface (CLI) [Python
  package](https://pypi.python.org/pypi/FanFicFare) that you can
  install with:
```
pip install FanFicFare
```
- _As of late November 2019, the web service version is shutdown.  See the [Wiki Home](https://github.com/JimmXinu/FanFicFare/wiki#web-service-version) page for details._

### Test Versions

FanFicFare is released roughly every month, but new test versions are posted more frequently as changes are made.

Test versions are available at:

- The [test plugin] is posted at MobileRead.
- The test version of CLI for pip install is uploaded to the testpypi repository and can be installed with:
```
pip install --extra-index-url https://test.pypi.org/simple/ --upgrade FanFicFare
```

### Other Releases

Other versions may be available depending on your OS.  I(JimmXinu) don't directly support these:

- **Arch Linux**: The latest CLI release can be obtained from the [fanficfare](https://aur.archlinux.org/packages/fanficfare) AUR package. It will install the calibre plugin, if calibre is installed.


[this post in the old FFDL thread]: https://www.mobileread.com/forums/showthread.php?p=1982785#post1982785
[FAQs]: https://github.com/JimmXinu/FanFicFare/wiki/FAQs#can-fanficfare-download-a-story-containing-images
[FanFicFare maillist]: https://groups.google.com/group/fanfic-downloader
[wiki]: https://github.com/JimmXinu/FanFicFare/wiki
[discussion thread]: https://www.mobileread.com/forums/showthread.php?t=259221
[test plugin]: https://www.mobileread.com/forums/showthread.php?p=3084025&postcount=2
