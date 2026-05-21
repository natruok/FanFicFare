**Everything below should be configurable within personal.ini — see attachments in release.**

**Changes made:**
1. added links for all individual metadata on title page, like with ao3 export
2. added author/overall work headnotes, associations, and footnotes to metadata
3. created separate summary page that also shows on TOC — shows summary description + work headnotes with horizontal line in between
4. created separate afterword page that also shows on TOC and shows up at the end — includes work end notes, appears if work end notes exist, option to only show up if completed
5. add line break between chapter head & foot notes

**Pending:**
- strip chapter titles & redo only if the chapter isn't named "Chapter #"
- update series naming to "Part # of xxx", but keep indexing by series name
- add configurable "other" page

<HR/>

**PERSONAL.INI CUSTOMIZATIONS REQUIRED:**

```
[epub]
## Used add_to for everything to not replace the ao3 defaults
## Updates to labels from original FFF default ini
rating_level_label:Rating
chapterslashtotal_label:Chapters
warnings_label:Archive Warning
freeformtags_label:Additional Tags
freefromtags_label:Additional Tags
ao3categories_label:Category
series04HTML_label:Additional Series

## create additional links — only part of edited FFF plugin:
add_to_extra_valid_entries:,ratingUrl, fandomsUrl, freeformtagsUrl, ao3categoriesUrl, charactersUrl, warningsUrl, shipsUrl,
 ratingHTML, fandomsHTML, freeformtagsHTML, ao3categoriesHTML, charactersHTML, warningsHTML, shipsHTML,
 series04, series04HTML, freeformtags_list_separator, seriesindex,
 headnote, endnote, assocnote
add_to_make_linkhtml_entries:, rating, fandoms, freeformtags, ao3categories, characters, warnings, ships,
 ratingUrl, fandomsUrl, freeformtagsUrl, ao3categoriesUrl, charactersUrl, warningsUrl, shipsUrl,
 ratingHTML, fandomsHTML, freeformtagsHTML, ao3categoriesHTML, charactersHTML, warningsHTML, shipsHTML,
 series04, series04HTML

## added for links, only part of edited FFF plugin:
ratingHTML_label:Rating
warningsHTML_label:Archive Warning
ao3categoriesHTML_label:Category
fandomsHTML_label:Fandom
shipsHTML_label:Relationship
freeformtagsHTML_label:Additional Tags
charactersHTML_label:Characters
## below only required if intending to use headnote/endnote as part of titlepage entries
headnote_label: Author's Note:
endnote_label: End Notes:

## Customizable headers for the different OTW story notes:
notelabel_authorheadnotes:Author's Note:
notelabel_chaptersummary:Chapter Summary:
notelabel_chapterheadnotes:Chapter Notes:
notelabel_chapterfootnotes:Chapter End Notes:
notelabel_authorfootnotes:End Notes:

## hr = add horizontal line break between chapter head & end notes; leave blank or remove if no line wanted
hrline:hr

## TITLE PAGE
## Updated for titlepageentry div class — to indent info, and break out byline
titlepage_start:<?xml version="1.0" encoding="UTF-8"?>
 <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
 <title>${title} by ${author}</title>
 <link href="stylesheet.css" type="text/css" charset="UTF-8" rel="stylesheet"/>
 </head>
 <body class="fff_titlepage">
 <h3><a href="${storyUrl}">${title}</a></h3>
 <div class="byline">by ${authorHTML}</div>
 <div>

titlepage_entries: ratingHTML, warningsHTML, ao3categoriesHTML, fandomsHTML, shipsHTML, charactersHTML, freeformtagsHTML, language,
 seriesHTML, collectionsHTML, <br/>

titlepage_entry:
 <b>${label}:</b><div class="titlepageentry">${value}</div><br />

background_color: 000000

titlepage_end:
 <b>Stats:</b>
 <div class="titlepageentry">Published: ${datePublished}</div><br />
 <div class="titlepageentry">Updated: ${dateUpdated}</div><br />
 <div class="titlepageentry">Status: ${status}</div><br />
 <div class="titlepageentry">Words: ${numWords} | Chapters: ${chapterslashtotal}</div><hr />

 <b>Downloaded:</b>
 <div class="titlepageentry">${dateCreated}</div><br />
 <div class="titlepageentry">Kudos: ${kudos} | Hits: ${hits}</div><br/>
 <div class="titlepageentry">Bookmarks: ${bookmarks}</div>

 </div>
 </body>
 </html>

exclude_notes:authorheadnotes,authorfootnotes
#,inspiredlinks

## SUMMARY PAGE — below are the defaults, can edit as needed
## to include summary page, between title page & toc/ch 1: true/false
## add in summarypage_start section and update to override section for author head notes
include_summarypage: true

## format if the fic doesn't have author headnotes
summarypage_start:
 <?xml version="1.0" encoding="UTF-8"?>
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
 <title>${title} by ${author}</title>
 <link href="stylesheet.css" type="text/css" rel="stylesheet"/>
 </head>
 <body class="fff_summarypage">
 <div>
 <h3>Summary</h3>
 ${description}

## format if the fic has author headnotes
summarypage_headnote_start:
 <?xml version="1.0" encoding="UTF-8"?>
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
 <title>${title} by ${author}</title>
 <link href="stylesheet.css" type="text/css" rel="stylesheet"/>
 </head>
 <body class="fff_summarypage">
 <div>
 <h3>Summary</h3>
 ${description}
 <hr/>
 <p><b>Author's Note:</b></p>
 <blockquote>${headnote}</blockquote>

summarypage_end:
 </div>                                                            
 </body>
 </html>

## TOC PAGE — part of original fff plugin
## to include TOC page: true = if chapters > 1, always = always, false = off
include_tocpage: false

## AFTERWORD PAGE — below are the defaults, can edit as needed
## include afterword page: true = yes, smart = only if Completed, false = off
include_afterpage: smart

afterpage_start:
 <?xml version="1.0" encoding="UTF-8"?>
 <html xmlns="http://www.w3.org/1999/xhtml">
 <head>
 <title>Afterword</title>
 <link href="stylesheet.css" type="text/css" rel="stylesheet"/>
 </head>
 <body class="fff_afterpage">
 <h3>Afterword</h3>
 <b>End Notes:</b>
 <blockquote>${endnote}</blockquote>

afterpage_end:
 </body>
 </html>

## CSS
## to add in titlepageentry & byline div classes for customized title page
add_to_output_css:
 .titlepageentry { text-align: left; display:inline-block; padding-left: 15px; }
 .byline { display: block; text-align: center;  margin: 0.67em 0; }
## below are optional
 body { line-height: 1.6; }
 body.fff_titlepage div > b { font-weight: bold; display: block; margin-top: 0.6em; }

 a.serieslink { color: #6ba3be; }
 a.authorlink { color: #6ba3be; }
 a.storyurl { color: #6ba3be; }

[overrides]
# to keep Relationships in order w/ URLS - only part of edited FFF plugin
keep_in_order_ships:true
sort_ships:true

## to keep Additional Tags in order w/ URLs — only part of edited FFF plugin
keep_in_order_freeformtags:true
keep_in_order_freeformtagsUrl:true
```

<hr/>
<hr/>

**ARCHIVED NOTES:**

Latest stable: [v46](https://github.com/natruok/FanFicFare/releases/tag/v46)

**Personal customization goals:**
- add links to all metadata on title page like with ao3 export — DONE, see [v31](https://github.com/natruok/FanFicFare/releases/tag/v31)
- create separate summary page that also shows up in TOC — DONE [v31](https://github.com/natruok/FanFicFare/releases/tag/v31)
- create separate afterword page that also showd up in TOC for overall work end notes — DONE, see [v44](https://github.com/natruok/FanFicFare/releases/tag/v44)
- separate overall author head notes into summary page rather than at beginning of ch 1 — PARTIALLY DONE, pending to add ul associations, see [v45](https://github.com/natruok/FanFicFare/releases/tag/v45)
- afterword page to show up only if there are overall end notes — DONE, see [v48](https://github.com/natruok/FanFicFare/releases/tag/v48)
- summary page to show horizontal line for line break and author's note — DONE, see [v48](https://github.com/natruok/FanFicFare/releases/tag/v48)
- summary page to show horizontal line for line break and author's note only if it exists — DONE, see [v49](https://github.com/natruok/FanFicFare/releases/tag/v49)
- separate work end notes into afterword page rather than end of chapter — DONE, see [v50](https://github.com/natruok/FanFicFare/releases/tag/v50)
- make new summary & afternote pages configurable in personal.ini — DONE, see [v50](https://github.com/natruok/FanFicFare/releases/tag/v50)
- add line break between chapter head & foot notes — DONE, see [v51](https://github.com/natruok/FanFicFare/releases/tag/v51)
- strip chapter titles & redo only if the chapter isn't named "Chapter #"
- update series naming to "Part # of xxx", but keep indexing by series name
