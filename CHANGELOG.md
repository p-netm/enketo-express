## Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

[Unreleased]
---------------------
##### Added
- Make record cache expiry time configurable.

##### Changed
- Updated Swedish, Dutch and German translations.
- Show warning if select_multiple option contains spaces in value.
- Guidance hints are now displayed on screen as collapsible element.

##### Fixed
- Likert widget label in Grid Theme overlaps widget in print view.

[1.77.1] - 2019-07-12
--------------------
##### Changed
- Improvements to print style (group header size, opacity of disabled questions, line-height in Grid Theme)
- Improved print style of select minimal widget.

##### Fixed
- Disabled analog-scale widget is still visible.
- Long words break out of cell in Grid Theme.
- Workaround for an iOS browser bug where a readonly date input is actually fully functional. **WARNING: you may have to add a widget to config.json to activate, see default-config.json change**
  
[1.77.0] - 2019-05-21
--------------------
##### Removed
- Support for appearances "quick" and "quickcompact".

##### Added
- Support for appearances "columns", "columns-pack", "columns-n" all with an optional "no-buttons" modifier, **WARNING: you may need to change widgets configuration in config.json `"compact" -> "select-media"` and `"horizontal-choices" -> "columns"`)**.
- 
##### Fixed
- Analog scale widget without current value box, still firing excessive change events.
- Distress widget mercury is not reset properly.

[1.76.3] - 2019-05-09
--------------------
##### Fixed
- Some forms with repeats fail to load in Safari.
- Iframe-friendly views only print first page.
- Draw widgets loose drawing (or last stroke(s) in drawing) on mobile devices if clicking hide-full-screen button or switching device orientation within 1.5 sec after last change.
- Datepickers in Grid Theme in Firefox show the reset button outside the cell.
- Range, Analog Scale, Datetime, and Time widgets fire an unnecessary change event when a new value is set that is equal to the existing value.
- Range widget fires an unnecessary change event when the value is empty, before the value is set, when the user clicks the widget.

[1.76.2] - 2019-04-24
--------------------
##### Fixed
- Failing to clone repeats that only contain calculations.
- Select one calculations not updating correctly.
- Irrelevant calculations inside non-first repeat instances run upon load.
- Date strings without timezone component are not always converted correctly in time zones that have DST.
- Hand-typed/pasted dates with spaces or invalid characters are kept shown to user, but are not stored in model.

[1.76.1] - 2019-04-01
---------------------
##### Changed
- The restriction on crossing paths in the geoshape widget was removed.
- Hide reset button when question is readonly.
 
##### Fixed
- Radiobutton unselect functionality can cause infinite loops with certain custom extensions that update values programmatically.
- Readonly Draw/Signature widget updates with empty file when canvas looses focus. 
- Readonly Select Minimal widget is not readonly.
- Readonly File widget becomes writeable if it becomes relevant.

[1.76.0] - 2019-03-19
---------------------
##### Added
- A configurable option to provide a maximum character length of a text field (default: 2000 characters). **Warning: if overriding widgets in config.json, this widget needs to be explicitly enabled.**

##### Changed
- Updated Russian, Swedish, Spanish, and Dutch translations
  
##### Fixed
- The output in an itemset option label is not populated upon load.

[1.75.3] - 2019-02-27
---------------------
##### Fixed
- Submissions cause an exception in online-only view.

[1.75.2] - 2019-02-26
---------------------
##### Changed
- Partial rewrite of events.
- Improved accuracy of progress tracker.
  
##### Fixed
- Various issues when serving forms in a iframe on iOS devices.
- On touchscreen devices, the draw widget download functionality does not work, and clicking the Draw button empties the canvas.
- XForms using geopoint, geotrace, geoshape, time, date, datetime, select minimal, rank, autocomplete calculations **without form control** (advanced) fail to load.
- Some widgets (such as all geo widgets) do not update view if a calculation changes the underlying value.

[1.75.1] - 2019-02-21
---------------------
##### Fixed
- Calculations using advanced count(/path/to/repeat/node1[text()="something"]) aren't recalculated when a node1 changes.
- Exception occurs when appearance 'horizontal' is added to group (which has no support for this appearance).
- If the window in an online-only multi-page form is resized, while a drawing is on a currently-not-shown page, the submission results in an empty drawing.

[1.75.0] - 2019-02-18
---------------------
##### Changed
- Updated German translation.
- Readonly draw widgets no longer show drawings on grey background in Grid Theme, nor apply an opaqueness filter.
- Repeat deletion with "-" button now requires confirmation.

##### Fixed
- Loading image from record may show error even if it was loaded successfully.
- Generic file upload not working (cannot set property 'src' of null).

[1.74.4] - 2019-02-07
---------------------
##### Fixed
- IE11 fails to load.
- New repeats are always shown in default language.
- Relative repeat-counts not working.

[1.74.3] - 2019-01-10
---------------------
##### Fixed
- Loading a form with a readonly file input throws an exception.
- Times and datetimes with meridian notation are set to empty in the model for times between 12:00 AM and 1:00 AM, and between 12:00 PM and 1:00 PM.

[1.74.2] - 2019-01-07
--------------------
##### Changed
- Fewer model updates during drawing using draw/signature/annotate widgets (performance).
  
##### Fixed
- Loading error in Pages mode when a page has no label.
- Itemsets not populating if inside an irrelevant group upon load.
- Download link not working for Draw/Signature/Annotate widgets.
- Broken autocomplete widget in Safari and all iOS browsers.
- Slider in vertical range widget not aligned properly in Grid Theme.

[1.74.1] - 2018-12-25
-----------------------
##### Fixed
- Likert item option labels with unequal number of lines not lined up correctly in Grid Theme.
- Minification breaks most widgets on Safari and iOS browsers.

[1.74.0] - 2018-12-17 
----------------------
##### Changed
- Updated Spanish translation
- Updated to new widget format. **WARNING: custom widgets need to be converted to new format!**
- Do not include time component for today().

##### Fixed
- API has 100kb body content limit causing issues when editing large instances.
- Date calculations (e.g. today()) for number type questions do not return a number.
- RTL detection not working for Sorani (ckb) and Kurdish (ku) and other languages.

[1.73.0] - 2018-11-13
----------------------
##### Changed
- Modernized client-side Javascript code [Major]. **WARNING: custom widgets need to be converted to ES6 modules!**
- Updated Swedish translation.

##### Fixed
- Default values not loaded in non-first repeat instances. Also causes other repeat problems.
- Table widget option hover background is not centered around radiobutton/checkbox.

[1.72.3] - 2018-10-31
----------------------
##### Changed
- Updated Russian, Spanish, Czech and Dutch translations.
  
##### Fixed
- Autocomplete widget not updating when form language is changed.

[1.72.2] - 2018-10-19
----------------------
##### Fixed
- If grid form starts with a disabled question, the first question has no top border.
- If first page in form is irrelevant upon load, it is still shown (in grayscale).
- Minimal select picker (pulldown) not updating model (regression in 4.60.3).

[1.72.1] - 2018-10-16
----------------------
##### Fixed
- IE11 broken (polyfills not found - 404)
- Loading records not working in IE11. All node values are emptied when a record is supplied.
- In FF when a radiobutton or checkbox is clicked directly in a pulldown select, the URL fragment identifier is updated (and page scrolls to the top).
- Timepicker localized AM/PM strings not detected properly in Firefox and Safari.
- Timepicker meridian field not wide enough for Chinese AM/PM.
- Timepicker meridian detection not working in IE11.
- IE11 polyfill for .after not working on comment nodes.

[1.72.0] - 2018-10-04
----------------------
##### Added
- Support for local encryption: https://blog.enketo.org/encryption/

[1.71.1] - 2018-09-24
----------------------
##### Changed
- Made export feature consistent across browsers.

##### Fixed
- Cascading selections with radiobuttons/checkboxes do not show image labels.
- Loading error when record with repeat calculation was loaded and validateContinuously was set to `true`.

[1.71.0] - 2018-09-11
----------------------
##### Changed
- Performance of form engine (determining index).
- Clean up translation and JS built files and separate better from source files.
- Print hints are now guidance hints, and follow ODK XForms specification

##### Fixed
- Range pickers not showing current value "thumb" on printouts.
- Distresspicker thumb not centered on Chrome and Safari.
- `jr:choice-name()` function not working with autocomplete questions.

[1.70.3] - 2018-08-28
----------------------
##### Changed
- Improved performance of modern browser (at the expense of Internet Explorer 11 performance) by not loading polyfills unnecessarily.

#### Fixed
- Loaded year and month-year values not displayed correctly in date (desktop) widget.
- Calculation results inside repeats are shown incorrectly to user under certain conditions.
- When a repeat is removed, calculations inside sibling repeats (e.g. using `position(..)`) are not always re-calculated.

[1.70.2] - 2018-08-23
----------------------
##### Changed
- In readonly views input fields are now shown if empty.

##### Fixed
- If form in Pages Mode has a repeat as the first page (with field-list), a blank first page is shown.

[1.70.1] - 2018-08-15
---------------------
##### Fixed
- Modal with lots of text not aligned nicely on small phone screens.
- Appearance "placement-map" not showing map in geowidgets. 

[1.70.0] - 2018-08-13
---------------------
##### Added
- Enable/disable meridian in timepicker and datetimepicker based upon detected locale preferences.
- Table of Contents to Pages mode that enables jumping to any page.

##### Fixed
- Questions with calculations do not re-validate immediately when the value is re-calculated (with `validateContinuously: true`).
- Labels with words longer the form width, overlap with other form elements.
- Readonly questions in newly cloned repeats in Grid Theme do not get the proper readonly styling.
- Whitespace only input triggers a `valuechange.enketo` event but should not.
  
[1.69.2] - 2018-08-02
--------------------
##### Changed
- Updated German and Slovak translations.

##### Fixed
- Docker installations fail because the `Dockerfile` specifies NodeJS 6.
- Download links in file input and draw widgets not working in IE11.
- The required asterisks (*) do not update in real-time if `validateContinously` is set to `false`.
- If a required text input field has a non-whitespace value that is replaced by the user to a whitespace-only value the new whitespace-only value is saved and considered valid.

[1.69.1] - 2018-07-25
---------------------
##### Changed
- In Grid Theme readonly questions with value now have the same whole-cell background color as readonly questions without a value.

##### Fixed
- Form previews using the `form` query parameter with a URL value that contains ":" in the path, get stuck in an infinite loop (!).
- If an loading error occurs when the form is reset, no message is output to the user.
- After the first record is created, external data does not get populated for subsequent records.
- Failing to load external data into an offline-capable webform.

[1.69.0] - 2018-07-19
---------------------
##### Removed 
- NodeJS 6 support.

##### Added
- Support for 'no-ticks' appearance in range widget.

##### Fixed
- Range widget in FF, the ticks partially disappear when the widget has a value.
- Randomize() doesn't work for itemsets that use itext() labels (in enketo-transformer).
- An architectural issue with modal dialogs.

[1.68.0] - 2018-07-11
---------------------
##### Added
- api/v2/version endpoint to obtain current Enketo Express version.
- Russian translation.

##### Changed
- Updated Dutch translation.

##### Fixed
- The form width in IE11 is sometimes too small.
- Exceptions thrown with complex jr:choice-name() usage.
- Various Geo Widget styling issues with buttons, mobile (fullscreen) and RTL scripts.

[1.67.1] - 2018-06-27
---------------------
##### Changed
- Updated Lao and Spanish translations.

##### Fixed
- In a form containing a group with a single child repeat (and no other repeat sibling questions), fails to load a record where that group is empty. When creating the first repeat after load an exception occurs.
- Output inside a group that is irrelevant upon loading does not get evaluated when the group becomes relevant.
- Autocomplete question inside a non-first repeat shows list from first repeat.
- Dates are now considered local to fix constraints such as ". < today()"


[1.67.0] - 2018-06-18
----------------------
##### Added
- Ranking widget. **Warning: You may need to update your config.json to activate.**
- URL widget. **Warning: You may need to update your config.json to activate.**

##### Fixed
- Range widget loading error if relevant is used.
- When unfolding collapsed groups, the draw widgets are not functional until the window is resized.
- Various styling degradations of geo widgets.
- Dynamic defaults do not work with encoded square brackets.

[1.66.3] - 2018-06-11
----------------------
##### Changed
- Show latest commit as version on front page.

##### Fixed
- Readonly text inputs with a default value are hidden.
- Certain XPath function calls without parameters cause an infinite loop.

[1.66.2] - 2018-06-06
----------------------
##### Fixed
- Likert widget not instantiating (regression in 1.66.0)
- The print dialog for Grid forms does not show radiobuttons in IE11.
- The button text of offline-capable form sometimes gets stuck on 'Save as Draft' when it should be 'Submit'.
- Full previews (with Enketo ID) do not show correct maximum submission size in file upload questions.
- Previews without Enketo ID do not show correct maximum submission size in file upload questions. **Note: make sure that a `HEAD` request to the form URL responds with the correct `X-Openrosa-Accept-Content-Length` header.**
- Coordinates around the international dateline (longitude < -180 degrees) are considered invalid in geo widgets. Sorry, data collectors in Taveuni!

[1.66.1] - 2018-06-04
---------------------
##### Fixed
- Range widget turns geo coordinate inputs into range inputs.

[1.66.0] - 2018-06-04
--------------------
##### Added
- Support for `<sup>` and `<sub>` (superscript and subscript).
- Support for range widget (basic). **Warning: You may need to update your config.json to activate.**

##### Changed
- Performance-optimized itemsets. Cutting-edge browsers can now deal well with 16,500 item documents.
- Performance-optimized the loading of external data.

[1.65.5] - 2018-05-24
---------------------
##### Changed
- Improved accessibility of buttons and links.

##### Fixed
- Styling interference occurs when an appearance is added to a question type that doesn't support it.

[1.65.4] - 2018-05-18
---------------------
##### Changed
- Button text for alert modals to "OK".
- Improved loading performance.

##### Fixed
- Thanks and logout page too dark (regression in 1.65.2).
- The form language selector is disabled in readonly views.
- If app disables offline functionality, a previously cached app continues to work.

[1.65.3] - 2018-05-15
---------------------
##### Fixed
- Login screen won't allow entering credentials (regression in 1.65.2).

[1.65.2] - 2018-05-14
---------------------
##### Fixed
- Appearance "horizontal" enlarges the last option if the remainder of the options modulo 3 is 1.
- If all repeats containing a question that has skip logic are removed, an exception occurs when obtaining the model as string without irrelevant nodes.

[1.65.1] - 2018-05-02
---------------------
##### Changed
- Hide disabled reset button in draw widget.

##### Fixed
- Comment icon overlaps long label in simple select/select1 questions.
- Pasted incorrect date value converts to today's date.
- When a record is loaded with an empty value for a node that has a default value in the XForm, all secondary instance values are emptied. 

[1.65.0] - 2018-04-25
---------------------
##### Added
- `decimal-time()` support.
- `distance()` support.

##### Fixed
- In Safari, readonly checkboxes and radiobuttons can still be manipulated and WILL modify the record, even if the UI doesn't update.
- `decimal-date-time()` not spec-compliant at all.
- Filepicker and drawing widgets have functional reset button when they are readonly.

[1.64.0] - 2018-04-22
---------------------
##### Added
- Basic `randomize()` support to shuffle nodesets (no support for itemsets with itext labels).
- 
##### Changed
- Increased linespacing for labels of "select" questions.

##### Fixed
- GoTo functionality no longer working (regression in 1.62.1)
- Modal dialogs called from widget (e.g. file input reset) no longer working.
- `min()` and `max()` ignore non-last arguments/nodes with value 0.
- Goto functionality throws exception if target is a comment question that is not inside a group and the form is in Pages Mode.

[1.63.0] - 2018-04-14
---------------------
##### Added
- Portugese translation

##### Changed
- Updated Spanish, German, Slovak, and Dutch translations.
- Styling of + button to create a new repeated section.
- Enketo ID generation is now creating a random string, and longer IDs.

##### Fixed
- Add-repeat (+) button not aligned properly in Grid theme when no repeats exist.
- Manual date input without hyphen (i.e. large number) is converted to non-sensible date.

[1.62.1] - 2018-04-06
---------------------
##### Changed
- Loading screen styling.

##### Fixed
- Download filename may change in filepicker/draw widget if a record with media files is loaded, if the file is not served with the correct name.
- Print button not revealed (regression in 1.62.0).
- Images in Grid theme print/PDF view overflow into neighboring cells.

[1.62.0] - 2018-04-03
---------------------
##### Added
- Ability to directly obtain PDF of empty form or form with a record. See [apidocs.enketo.org](https://apidocs.enketo.org) (3 new endpoints).

##### Changed
- Annotate widget will now no longer allow drawing until an image has been uploaded.

##### Fixed
- Print view of Grid Theme form in Pages mode doesn't properly stretch cells in the current page.
- Markdown headers in Grid Theme are overlapping in print view.
- Print view of Grid Theme doesn't correct width of last question in form.
- If the form starts with a lengthy group, the print view shows only the form title on the first page.
- Loading drawings from existing records, results in blank canvas after window resizing.
- The image map widget shows 'SVG not found error' in Firefox sometimes, and if so, it fails to scale the image.

[1.61.5] - 2018-03-21
---------------------
##### Changed
- In Markdown, make a distinction between paragraphs (2+ subsequent new lines) and simple new lines.
- Positioning of comment widget icon next to question label.
- Center media inside labels.

##### Fixed:
- Repeats with images become exponentially slower to load for each new repeat that is added.
- In offline-capable views, the Image Map widget inside a repeat shows 'SVG image cannot be loaded' message when all is okay.
- In Markdown, newline characters are not converted if they follow a heading.

[1.61.4] - 2018-03-09
---------------------
##### Fixed:
- When radiobutton or checkbox is cleared programmatically the `data-checked` attribute is not updated.
- Filenames of signature, annotation and drawing inputs are set to undefined-xx.png.

[1.61.3] - 2018-03-05
---------------------
##### Fixed:
- If existing drawing/signature/annotion is loaded from a http URL (editing submitted record), an exception occurs.
- Submissions not being made in offline-capable webform views.

[1.61.2] - 2018-03-02
---------------------
##### Added
- Polish translations.

##### Removed:
- File upload "no preview for this file type" message.

##### Fixed
- Cursor in Grid theme set to text for no seemingly good reason.
- Markdown headers not limited from h1-h6 as they should be (in Enketo Transformer)

[1.61.1] - 2018-02-27
---------------------
##### Changed
- Chrome bug workaround base64-conversion of blobs has been removed, so blobs are stored as blobs in Chrome now.
- Show separate custom reset messages for drawing, signature and annotation widgets.

##### Fixed
- Print, Back and First button icons not visible in IE11.
- Date format shown to user in readonly field is different from non-readonly field.
- Autocomplete widget does not accept options that have multiple subsequent spaces in their label.
- Draw widget draw color gets reset to the default color after undo-ing strokes.

[1.61.0] - 2018-02-21
---------------------
##### Added
- Download functionality to draw widgets.
- Support for "new", "new-front", "new-rear" on media inputs.
- Feature to undo drawing strokes in draw and annotate widgets.

##### Changed
- Show helpful error message if SVG image cannot be found with Image Map widget.
- Native month-year datepicker used on mobile devices when available.

##### Fixed
- In annotate widget loaded file disappears when screen is resized.
- Annotate widget not working on touchscreen devices.
- Annotate widget stretches uploaded image.
- Downloaded drawings have a different filename from the one stored in the record.
- Imagemap widget does not work for a group `<g>` of `<path>`s.
- Imagemap scaling issue when width and height defined in SVG file have units (pt).

[1.60.0] - 2018-02-14
---------------------
##### Added
- File pickers can now (only) be reset by a new reset button.
- Download functionality to file pickers.
- Full support for annotate widget.

##### Changed
- Repeats without form controls now no longer take up any visual space in the form.
- Show upload placeholder with max file size.
- Error messages in geopicker are now translatable.
- Draw/signature widget requires confirmation before reset.
- Geo widget and file widget now use consistent (app) modal dialogs instead of inconsistent native dialogs.

##### Fixed
- Instances with special characters in instance id attributes cannot to be queried.
- Namespaces not resolved for secondary instances.
- Slowdown with repeat-count that was introduced in 1.58.0.
- Printing: geo widget with appearance "maps" does not show coordinate fields.
- Printing: Analog scale widget with Grid theme in pages mode is messed up.

[1.59.0] - 2018-01-30
---------------------
##### Added 
- External authentication with token.

##### Changed
- Server-side form caching mechanism was re-written to support dynamic manifest URLs. **WARNING: test this release extra thoroughly wrt form updates**
- Configuration for authentication has changed, see [documentation](./config/README.md). **WARNING: update your config.json** (even though old configuration should still work for now).

##### Fixed
- Date strings returned by XPath evaluator for question with type 'date' are not considered valid dates and set to ''.
- When redirecting to an external login URL, the return URL is not encoded.
- Instance('id' )/path/to/node does not work if 'id' is surrounded by whitespace.
- Markdown headers preceded by whitespace fail to render as header and whitespace trimming is too aggresive.
- Datepicker with "month-year" and "year" appearance shows full value.

[1.58.0] - 2018-01-19
---------------------
##### Added
- Option to turn off page-swipe support.
- Support for escaping \# characters in markdown.

##### Changed
- Restored pulldown select button height to normal.
- Reduced margins around markdown headers.
- Markdown headers now work at the start of any line, even if not followed by a newline.

##### Fixed
- An output inside a group label that is the parent of a repeat with 0 instances, causes a loading exception.
- Readonly question does not show constraint message.
- A top-level group with a relevant that refers to a node inside a repeat may not get re-evaluated when the node changes and multiple repeats exist.
- Notifications/news in form previews are shown on printouts.
- Markdown headers in the middle of a string are not always ignored.

[1.57.0] - 2018-01-08
---------------------
##### Added
- Support for escaping \* and \_ characters in markdown.

##### Changed
- Invalid dates (and datetimes) such as 2018-12-35 are no longer automically converted to a valid date. They convert to empty now.

##### Fixed
- Proper IANA language tag inclusion in XForm does not prevent/override (weak) directionality detection.
- Printing: datetime picker inputs print below each other in Chrome.
- Safari invalidates any valid date (and datetime) with segments < 10, e.g. 2018-01-06.

[1.56.1] - 2018-01-01
---------------------
##### Fixed
- Repeat with field-list and parent group with field-list does not show "+" button and both groups fail to collapse.
- Dialogs no longer shown to user (**serious regression in 1.55.10**).

[1.56.0] - 2017-12-29
----------------------
##### Added
- The "query parameter to add to submission" (in config.json) is now also added to all /formList requests.

##### Changed
- Added workarounds for IE11 to match regular checkbox and radiobutton styling.
- Modest performance improvement with large repeat counts.

##### Fixed
- Collapse icon overlaps border on small screens.
- Black background shown behind radiobuttons and checkboxes on iOS browsers.
- RTL scripts do not have centered checkboxes/radiobuttons in tables.
- If preload item is placed inside a repeat with a repeat-count of 0, an exception occurs.
- RTL scripts with Grid Theme have mislocated repeat numbers and repeat removal button.

[1.55.10] - 2017-12-25
----------------------
##### Changed
- Image scaling by Image Map widget is more sensitive to screen size to avoid scrolling.

##### Fixed
- The advertised required transformer version fails to build on Windows 10.
- In Signature/Draw widget a line can be detected as a page-swipe in Pages mode.
- If Signature/Draw widget has loaded an existing value and is not on the first page, the drawing won't be shown until clicked.
- If SVG image in Image Map widget contains inline `style` attribute with fill and stroke the 'selected' state is not shown.

[1.55.9] - 2017-12-22
---------------------
##### Changed
- Error messages in filepicker are now translatable.
- Firefox checkboxes now styled properly.

##### Fixed
- jr:choicename() is causing an exception when wrapped inside other functions.
- Workaround for an XLSForm limitation by moving "no-collapse" appearance of repeat to its parent group.

[1.55.8] - 2017-12-19
---------------------
##### Changed
- When clicking the label of an upload question, the filepicker will no longer launch.

##### Fixed
- Datepicker not available on iOS browsers (again, sorry).

[1.55.7] - 2017-12-12
---------------------
##### Fixed
- Offline loading fails if language code in `Accept-Language` header contains a dialect such as `sv-SE`.

[1.55.6] - 2017-12-11
---------------------
##### Fixed
- Printing: When swapping to Grid Theme via API or app 'default theme' setting, the proper print dialog is not shown.
- Printing: Non-relevant non-select fields are not greyed out.
- Printing: Geo widget without "maps" appearance is shown on screen but not on printout.
- Printing: Geo widget map/zoom selector buttons are shown on printouts.
- Printing: Various Analog Scale widget styling issues.
- Grid Theme: A table-list/list-no-label question does not have a bottom border.
- Grid Theme: Top of page sometimes does not have a border.
- jr:choice-name() function can not handle syntax with more complex XPaths.
- Nodenames with dots cause an exception during extraction of a serialized model without irrelevant nodes.

[1.55.5] - 2017-11-29
--------------------
##### Fixed
- When a repeat is removed any logic that depends on repeat position changes is not updated when it should be.
- Printing: only first page printed in Firefox.
- Printing: group collapse carets shown.
- Printing: number input up/down buttons shown in Firefox.
- Repeat with relevants and parent group without `ref` attribute is not revealed when relevant becomes true.
- In pages mode, text and number inputs can no longer get focus.
- Printing: select-one does not show all options in long lists.
- Printing: styling improvements for draw/distress/likert widgets.

[1.55.4] - 2017-11-24
--------------------
##### Changed
- Visually separate repeat instances in Grid Theme.

##### Fixed
- A new repeat with a date field that is not relevant by default does not get the date widget on non-touchscreen devices.
- Draw/signature widget not working in pages mode sometimes, if it is not on the first page.

[1.55.3] - 2017-11-13
---------------------
##### Changed
- Styling of repeat + button in Grid Theme.
- Error message when form cannot be found in /formList.

##### Fixed
- A calculated item (without form control) and with a relevant inside a repeat throws an exception when there are 0 repeats and the relevant is evaluated.
- Exception occurs in error page generation when page cannot be found.
- Various issues with repeat + button in Pages Mode when repeat=page.
- Excessive change events fired by datepicker, timepicker, and datetimepicker when reset button is clicked when value is empty.

[1.55.2] - 2017-11-02
----------------------
##### Changed
- Updated Swedish, Slovak, Czech, German and Dutch translations.

##### Fixed
- Safari/iOS browsers fail to load Swedish (and others probably) UI language.

[1.55.1] - 2017-10-27
----------------------
##### Changed
- Track fragment identifier (#abcd) if Google Analytics is enabled, and no longer track querystrings.

##### Fixed
- If repeat = page in Pages mode, the second+ repeat is not shown.

[1.55.0] - 2017-10-19
----------------------
##### Changed
- Time format according to ODK XForms Specification (10:12 -> 10:12.00.000-06:00). **WARNING: Make sure your backend is ready for this.**

[1.54.0] - 2017-10-16
----------------------
##### Added
- Make all label groups collapsible.
- Let appearance "compact" on a group collapse this group by default.
- Make first repeat removable with button if repeat-count is not used.
- Let appearance "minimal" on a repeat prevent automatic creation of the first repeat instance.

#### Fixed
- Data type conversion issues for integers and dates.

[1.53.1] - 2017-10-09
----------------------
##### Fixed
- Max() and min() fail if nodeset is empty (0 repeats).
- If first page is not relevant it is still displayed upon load.
- Datepicker not available on iOS browsers.
- In nested repeats a user-entered repeat count is always taken from the first repeat if current repeat instances in the series are zero.

[1.53.0] - 2017-10-03
----------------------
##### Added
- Ability to [add custom widgets](https://github.com/kobotoolbox/enketo-express/blob/master/doc/custom-widgets.md) or [remove default widgets](https://github.com/kobotoolbox/enketo-express/tree/master/config#widgets) in config.json. **Have an issue? Check whether your config.json contains an old "widgets" property. If so, you'll probably want to just remove it.**

##### Fixed
- With validateContinuously=true, a new repeat instance is immediately validated.
- Pesky "error" message that sourcemap for bootstrap-datepicker.css is not found (when dev tools are open in browser).
- Incorrect Content-type of error responses.

[1.52.0] - 2017-09-26
---------------------
##### Added
- Ability to overwrite translations (in forks).

##### Fixed
- Readonly fields with calculation are not cleared in model when they become irrelevant if clearIrrelevantImmediately is set to `true`.
- Calculated items without form control were calculated even if they were inside an irrelevant group.
- Radiobuttons inside a repeat are sometimes incorrectly removed from the submission.

[1.51.1] - 2017-09-13
---------------------
##### Fixed
- Form loading error with new decimal input mask (on Safari at least). 

[1.51.0] - 2017-09-06
----------------------
##### Added
- Support for appearance="numbers" on text inputs on mobile devices.
- Fixed input masks for integer and decimal inputs.

##### Changed
- Make goto-target-not-found error translatable.

[1.50.2] - 2017-08-17
----------------------
##### Fixed
- In some situations, nested repeat nodes that are relevant are removed from the record string as if they were irrelevant.
- In tables, the heading row (appearance=label) can be misaligned with the lower rows.
- Cloned select minimal question with relevant inside repeat is hidden when loading record with multiple repeats.
- Draw/signature widget is instantiated for file input types other than "image".
- Draw/signature widget is never enabled if it has a relevant expression.
- File inputs do not always clear properly when they become irrelevant.

[1.50.1] - 2017-08-10
---------------------
##### Fixed
- Manual date edits do not get propagated to model if Enter key is not pressed.
- Edit and readonly views do not translate default error messages for "constraint" and "required" logic.
- When loading record with repeats, any select/select1 questions (without appearance "minimal") in non-first repeats are not initialized properly.
- Comment icon and required asterisk overlapping with each other and with label in Grid theme.
- Timepicker styling issues in Grid theme.

[1.50.0] - 2017-08-03
---------------------
##### Added
- Signature/Draw widget.

##### Fixed
- HTML title element not populated with form title in readonly views.

[1.49.0] - 2017-07-25
---------------------
##### Changed
- Touchscreen detection to change widgets and appearance has been tweaked and is now only considering iOS and Android browsers.
- Hide irrelevant questions from printout if a record is loaded for editing.

##### Fixed
- A readonly select minimal (desktop) widget becomes editable when it has a "relevant" expression that evaluates to true.

[1.48.3] - 2017-07-10
---------------------
#### Fixed
- Offline-capable views fail to update and load media. **WARNING: recommend immediate update if currently on 1.48.0 or higher**

[1.48.2] - 2017-07-07
---------------------
##### Fixed
- Emergency temporary workaround for checked state of checkbox in Firefox.
- Error message when removing irrelevant nodes because the node cannot be found.
- Readonly select minimal widget is not properly readonly in special readonly views on touchscreens.

[1.48.1] - 2017-07-03
---------------------
##### Fixed
- Readonly select minimal widget is not properly readonly on touchscreens.

[1.48.0] - 2017-06-26
---------------------
##### Added
- "no-text-transform" style to be used with Grid Theme to prevent uppercasing labels.
- Readonly views for empty forms and submitted records. See new [/survey/view](https://apidocs.enketo.org/v2#/post-survey-view) and [/instance/view](https://apidocs.enketo.org/v2#/post-instance-view) API endpoints.

##### Fixed
- Edit views not redirecting upon submission.
- API /instance/* endpoints required _return_url_ parameter when it should be optional.

[1.47.3] - 2017-06-20
---------------------
##### Changed
- Updated datepicker module.

##### Fixed
- Media files in a repeat group not displayed in repeat clones in offline-capable forms.
- Duplicate logic evaluation when a repeat is added.

[1.47.2] - 2017-06-19
---------------------
##### Changed
- Allow parens in server URL.
- Reduced swipe sensitivity to avoid accidental "click-swiping" with a mouse.

##### Fixed
- Page swipe bypasses block-page-navigation-on-new-constraint-error feature.
- If form in Pages mode has only one page, this page is not shown. 
- Datetime and date widgets do not update with calculated date when they are not readonly.

[1.47.1] - 2017-06-09
---------------------
##### Changed
- Add loadError if "go to" field cannot be found.
- Localize %a and $b in format-date() to form locale at time of calculation.

##### Fixed
- Frozen UI if "go to" field is a comment field whose linked question is hidden.

[1.47.0] - 2017-05-25
---------------------
##### Added
- Ability to jump to a specific question upon load in previews and edit views.

##### Changed
- Updated Swedish translations.

##### Fixed
- Timepicker and Datetimepicker issues around empty and default values.
- When loading a record with nested repeats the second+ series gets inserted out-of-order in the model.
- When loading a record with nested repeats and additional nested groups, the nested repeats are not cloned in the view.

[1.46.1] - 2017-05-18
---------------------
##### Fixed
- Branches and Outputs not initialized when repeat is cloned.

[1.46.0] - 2017-05-17
---------------------
##### Added
- Image Map select widget.

##### Fixed
- Itemsets inside a repeat with a choice_filter (predicate) dependency outside the repeat are not initialized when repeat is cloned.

[1.45.2] - 2017-05-09
---------------------
##### Added
- Support for appearance 'hide-input' in ArcGIS geo widget.

##### Fixed
- Exception occurs when obtaining cleaned-of-irrelevants model string if repeat has a relevant and a repeat-count of 0.
- Performance of forms with repeats (issue with dataupdate event data).

[1.45.1] - 2017-05-01
---------------------
##### Changed
- ArcGIS API for JS updated to 4.3 in ArcGIS geo widget.
- Updated Czech, German, Slovak and Dutch translations.

##### Fixed
- IE11 exception upon loading forms with repeat templates.
- Progress bar seems incorrect because comment questions are not excluded from progress calculation.

[1.45.0] - 2017-04-27
---------------------
##### Removed
- "validated.enketo" event.
- Subtle "required" text on focus.

##### Added
- Swedish translations.
- Ends-with() and abs() XPath support.

##### Changed
- Textareas (multiline widget) will autogrow now.
- If validatePage is set to `false`, block page navigation for some milliseconds if required to ensure that user sees new error message.
- Always lock scrolling of ArcGIS geo widget until user clicks the map (previously only on touchscreens).

##### Fixed
- XPath int() conversion incorrect for negative values.
- A repeat with a relevant and a repeat-count of 0, throws exception.
- Selectpicker (non-touch) does not show checked status if radiobuttons/checkboxes themselves are clicked.

[1.44.0] - 2017-04-20
---------------------
##### Added
- Ability to customize pretty much everything in Enketo Core (not endorsing doing this though).

[1.43.1] - 2017-04-14
---------------------
##### Fixed
- Repeats no longer shown on separate page in pages mode when they have field-list appearance.
- Loading values into first radiobutton or first checkbox fails to update UI.

[1.43.0] - 2017-04-13
--------------------
##### Changed
- Questions or groups that are irrelevant will no longer be included in submission. **WARNING**
- Redirect upon submission only enabled for single submission views. Other views will ignore returnUrl parameter.
- Hide required “*” when dynamic required expression evaluating to false at the time the input field is validated.
- Updated Slovak and Czech translations.
- First repeat in a series has become removable when repeat-count variable is zero.

[1.42.2] - 2017-03-30
---------------------
##### Fixed
- CSV conversion fails for some CSV files due to inability to detect delimiting character.
- Client-side login fails if Enketo is running with basePath set
- In pages mode, if page (group) is relevant but only includes irrelevant questions, it is displayed as an empty page.
- Inputupdate.enketo event fires even if value hasn't changed.

[1.42.1] - 2017-03-22
---------------------
##### Changed
- Label of readonly question with a calculate expression is styled as regular question.
- Input field of readonly question with a calculate expression is now always visible to user.

##### Fixed
- ArcGIS geopicker fails to initialize inside a repeat.
- Value not cleared from widget UI when it becomes irrelevant and clearIrrelevantImmediately is set to `true`.
- Autocomplete widget causes exception when branch is hidden or revealed (due to relevant expression).

[1.42.0] - 2017-03-20
---------------------
##### Added
- Ability to pass attachments to instance to be edited. See [doc](https://apidocs.enketo.org/v2#/post-instance).
- Ability to pro-actively flush a survey cache. See [doc](https://apidocs.enketo.org/v2#/delete-survey-cache).
- Safari and iOS browser support for autocomplete widget.
- Ability to disable page validation (default is unchanged).

##### Changed
- Use systemd instead of upstart for redis in Vagrant setup.
- Reduced vertical whitespace between label and radiobuttons/checkboxes.

##### Fixed
- Vagrant installation issues with redis.
- Exception occurs when forms contains no textarea (multiline text widget).
- Repeat count updates in pages mode causes unhelpful page flipping behaviour if the repeat has _field-list_ appearance.
- Negative decimal numbers not converted correctly to integers.

[1.41.1] - 2017-03-14
---------------------
##### Fixed
- Cookies not passed for some communication that uses 'external authentication'.
- Styling issues with readonly questions.
- Grid theme does not print complete textarea if text requires scrolling.

[1.41.0] - 2017-03-09
---------------------
##### Added
- Ability to add custom data to dataupdate event.
- Ability to pass session properties (metadata) when instantiating form.
- Exp10() and log() functions.

##### Changed
- Updated Spanish translation.

##### Fixed
- XPath number results not converted to date and datetime when stored.

[1.40.0] - 2017-03-02
---------------------
##### Added
- Autocomplete widget for all browsers except: Safari and all browsers on iOS.
- Support for truly dynamic repeat count (jr:count attribute).

##### Fixed
- Select desktop picker options cannot be selected by pressing spacebar.
- Accessibility issue with file input picker (tab traversal, focus).

[1.39.1] - 2017-02-23 
---------------------
##### Fixed
- jr:choice-name() inside a repeat produces incorrect results.
- Media labels in itemsets are not shown.

[1.39.0] - 2017-02-20
---------------------
##### Added: 
- CSV conversion for language columns.

##### Fixed:
- Loading error dialog not rendering support email address correctly.
- Button backgrounds not displaying in Firefox.
- Incomplete type conversion of int, decimal, time, date and datetime.
- Calculation with relevant on readonly field inside repeat not evaluated when it should be.

[1.38.0] - 2017-02-10
---------------------
##### Added:
- An optional "validate continuously" mode.
- Send validated.enketo and invalidated.enketo events with extensible/custom data.

[1.37.1] - 2017-02-03
---------------------
##### Changed:
- FF on Android: Simpler Add to Homescreen guidance.

##### Fixed:
- FF on Android: Add to Homescreen button not clickable.
- Incorrect position of queue icon during loading when offline-capable icon is not yet visible.
- Accessiblity issues with radiobuttons, checkboxes, likert, compact.

[1.37.0] - 2017-01-25
---------------------
##### Removed:
- npm 2.x support **WARNING: check your npm version. It should be 3.x or 4.x**

##### Fixed:
- Client settings do not pick up query parameters with value `false`.
- Pencil icon span escaped in side bar.
- Click on form header brand without link still changes URL hash.

[1.36.5] - 2017-01-18
---------------------
##### Changed:
- Valuechange.enketo event now fires _after_ validation and passes validation result.

##### Fixed
- fixed: Horizontal analog scale label and slider overlap on small screens.
- translations were loaded 3 times affecting performance

[1.36.4] - 2017-01-06
---------------------
##### Changed
- Updated Czech, Slovak, German and Swahili translations.
- Moved down 'Powered by' footer on large screens.

##### Fixed
- Branding logo in form header is stretched sometimes.
- Subtle "required" message remains visible for empty questions with dynamic required expressions that evaluate to false().
- When question has a comment widget and is in an invalid state, this state is not removed when the comment value changes and makes the question valid.

[1.36.3] - 2016-12-22
---------------------
##### Changed
- Docker setup.

##### Fixed
- Excessive submission logging.
- When a question becomes irrelevant, its value is cleared immediately, but should be kept until submission.

[1.36.2] - 2016-12-14
---------------------
##### Fixed
- Comment widget in pages mode without field-list has hidden comment field and shows empty page.
- HTML not rendered in modal dialog.
- Repeat position injection gets confused if repeat has sibling with nodename that is equal to start of repeat nodename.

[1.36.1] - 2016-12-08
---------------------
##### Fixed
- Label of comment widget not shown when used with an analog-scale question.
- Entire label of complex (geo, analog scale) widget triggers comment button click.
- Comment icon not displayed inline after non-block label of analog-scale widget.
- Esri/ArcGIS geopicker does not re-instantiate in a cloned repeat.
- API endpoint /survey/all returns 4 incorrect URLs for single submission webforms.

[1.36.0] - 2016-12-02 
---------------------
##### Added
- ArcGIS widget: multiple basemaps with toggle button.
- Support for preload attributes on nodes that have a form control. 

##### Changed
- Updated Persian, Finnish and Dutch translations.
- Readonly styling of: likert widget, compact picker, dates, datetimes, and others.

##### Fixed
- User is able to manipulate readonly widgets: distresspicker, analog-scale-picker, select-desktop-picker, filepickers, geopicker.
- Calculations do not update: analog-scale-picker, distresspicker, mobile regular select, mobile multiselect picker preview, timepicker, geopicker, esri-geopicker.
- XPath calculation returing a datetime string for an XML node with type time is not converted, resulting in an invalid time.
- Geo widget on touchscreens does not hide Google Maps layer when exiting map view

[1.35.3] - 2016-11-08
---------------------
##### Added
- Finnish translation.

##### Fixed
- Offline icon position slightly off.


[1.35.2] - 2016-11-04
---------------------
##### Changed
- Updated Czech, Slovak, German and Dutch translations.

##### Fixed
- Min() and max() evaluation causes infinite loop when used with multiple node-set arguments.

[1.35.1] - 2016-10-31
---------------------
##### Fixed
- Repeat names with dots do not create multiple repeats upon loading and do not default values except for the first repeat.
- Public form.validate() function is skipping constraint validation if xml type is string, binary, select or select1.

[1.35.0] - 2016-10-27
---------------------
##### Added
- Comment widget enabled by default.

##### Changed
- Allow form to load if external data fails to dowload (but still show strong warning).

##### Fixed
- XML entities in CSV document are not encoded.
- Empty string literals ('""') are evaluated to 'undefined'.
- MS Edge does not properly clone repeats.
- "Different Encoding" error if instance encoding is specified, even if it's compatible.

[1.34.5] - 2016-10-20
---------------------
##### Fixed
- If OpenRosa server takes more than 2 minutes to respond to /submission, records stay stuck in browser queue despite being received.
- Too much whitespace in form header on small iOS 9 devices in Pages mode. 

[1.34.4] - 2016-10-18
---------------------
##### Fixed
- If repeat has no template, duplicate and conflicting ordinal attributes are added.
- Loading a record with namespaced attributes utterly fails in IE11.
- When record contains text nodes as siblings of repeats, new repeats are not added in correct position.

[1.34.3] - 2016-10-17
---------------------
##### Changed
- If logo source in config.json is "", remove all branding space in Pages mode on small screens.

[1.34.2] - 2016-10-13
---------------------
##### Changed
- Even less whitespace in form header and footer, especially in pages mode.

##### Fixed
- When branch is disabled an exception 'Cannot read property "readonly"' occurs.

[1.34.1] - 2016-10-11
---------------------
##### Added
- Documentation on the "comment feature".

##### Changed
- Tightened up form header and form footer with less whitespace especially in pages mode.

##### Fixed
- XPath functions containing "" or '' and refer to absolute paths sometimes produce incorrect result.

[1.34.0] - 2016-09-19 
---------------------
##### Added
- Advanced and regular single submission webform views and API endpoints. **WARNING: requires [additional configuration item](https://github.com/kobotoolbox/enketo-express/blob/master/config/README.md#less-secure-encryption-key)!**

[1.33.2] - 2016-09-16
---------------------
##### Added
- Documentation on ordinals.

##### Fixed
- IE11 adds rogue namespaces to ordinal attributes.

[1.33.1] - 2016-09-14
---------------------
##### Changed
- Updated Persian translation

##### Fixed
- Webform previews have incorrect (non-existing) JS bundle reference.

[1.33.0] - 2016-09-07
---------------------
##### Added
- Optional ability to add repeat ordinal attributes to model in enketo namespace.
- Improved extensibility.

##### Changed
- Validation logic refactored and behaviour for required field validation sligthly changed. If a required has a value and is then emptied, the background will turn red.
- Updated German, Czech, Dutch and Slovak translations.

##### Removed
- Workaround for [ODK Aggregate bug](https://github.com/opendatakit/opendatakit/issues/1116) because it doesn't really solve anything.

##### Fixed
- Fragile namespace handling in model.

[1.32.4] - 2016-08-15
---------------------
##### Fixed
- Compact appearances hide text label even if media label is absent.
- A potential scenario where the server cache gets never updated.

[1.32.3] - 2016-07-29
---------------------
##### Fixed
- Offline-capable webforms not working when offline.

[1.32.2] - 2016-07-27
---------------------
##### Fixed
- Slow performance of pulldata for huge files.

[1.32.1] - 2016-07-21
---------------------
##### Changed
- Updated German, Slovak and Czech translations.

##### Fixed
- String values are trimmed before added to model.
- Comment widget scrolling and button hover behavior.

[1.32.0] - 2016-07-15
---------------------
##### Added
- Ability to add additional translation strings in port of EE.

##### Changed
- Updated Lao translation.
- Show "*" for all questions with a "required" expression.
- Switched to enketo namespace for "for" attribute.

##### Fixed
- Npm 3 sass build error.
- Integer and decimal type values convert 'NaN' to '' (reverted ODK Aggregate bug workaround).

[1.31.0] - 2016-06-29
---------------------
##### Added
- Invalid XForms without /meta/instanceID will now be "fixed" by Enketo (temporarily).
- Ability to configure via environment variables instead of config.json.
- Documentation for deployment with Heroku

##### Removed
- Attempt to persist redis in Enketo app itself - **WARNING: persistence is now 100% arranged in your redis configuration!**

[1.30.1] - 2016-06-10
---------------------
##### Fixed
- External data not working in IE11.
- XForm without instanceID does not show load error.

[1.30.0] - 2016-06-08
---------------------
##### Added
- Support for user-specific dynamic external data documents.
- Widgets now have access to model's evaluate function.

##### Changed
- Updated Persian, Dutch and Czech translations.
- When requesting /formList, add formID query parameter (for performance).
- Comment widget now shown below linked question.
- Comment widget automatically focuses on comment input.

[1.29.4] - 2016-05-26 
---------------------
##### Changed
- Comment widget styling improvements.

##### Fixed
- Readonly select widgets are not disabled.
- Repeat buttons overlapping borders in Grid theme.
- IE11 Record loading "Interface not supported" error.
- IE11 Namespace errors when non-native XPath evaluator is used for namespaced nodes.

[1.29.3] - 2016-05-17
----------------------
##### Fixed
- Extremely slow loading when XForm model contains many nodes.

[1.29.2] - 2016-05-14
----------------------
##### Changed
- Comment widget styling improvements.

##### Fixed
- Not showing when comment question is in invalid state.
- Duplicate Enketo Ids are issued. **WARNING: This is a critical fix. [Recommended to deploy immediately!](https://github.com/kobotoolbox/enketo-express/blob/master/doc/duplicates.md)**
- Unfixable state of surveys with duplicate Enketo Id. ([Tool](https://github.com/kobotoolbox/enketo-express/blob/master/doc/duplicates.md) added to fix) **

[1.29.1] - 2016-05-11
----------------------
##### Added
- Czech translation.

##### Changed
- Styling of notes (readonly questions).
- Offline-capable URLs now use "x" instead of "_". Old URLs are still working. **WARNING: APIs return different offline-capable URLs.**
- Home page layout.

##### Fixed
- String literals not excluded from /model/instance[1] injection.
- Samsung S7 sms app rewrites "\_" in  http://enke.to/\_/#abcd URL. 
- Styling issues with # markup in labels, especially in Grid theme.

[1.29.0] - 2016-05-05
----------------------
##### Added
- Proper namespace support.
- Comment widget.

##### Fixed
- Minor markdown issues.

[1.28.0] - 2016-04-27
----------------------
##### Added
- 11 XPath math functions.

##### Changed
- If a submission returns a response with a generic 400 statusCode, output any well-formed OpenRosa response message to the user.
- Updated Persian and Spanish translations.

[1.27.1] - 2016-04-21
----------------------
##### Fixed
- Update check for forms requiring authentication fails in offline-capable webforms.
- Number inputs in Grid Theme not printing.
- Value of distress widget not easily visible when printing.
- Select element on mobile not showing first value in virgin state (e.g. when creating a repeat).

[1.27.0] - 2016-04-15
----------------------
##### Added
- Lao translation.
- Ability to use piwik for analytics.

##### Changed
- Updated Slovak, German, Dutch translations.
- Offline capability now enabled by default. **WARNING: to disable offline-capability, make sure to override this in your config.json!**

##### Fixed
- HTML title not populating when the form title contains numbers or special characters.
- Markdown formatting of outputs is not working.

[1.26.3] - 2016-04-01
----------------------
##### Changed
- Select minimal widget is now scrollable and won't stretch form.

##### Fixed
- Itemset update not retaining existing values when appropriate.

[1.26.2] - 2016-03-29
----------------------
##### Changed
- Wider select minimal widget in all themes. Full 100% of cell in Grid theme.
- Always show value in select minimal widget when only a single value is selected.
- Switched back to transparent icon for browser tabs.

##### Fixed
- Values in cloned repeat without jr:template are not emptied.
- Radio buttons and checkboxes not properly aligned vertically.
- Select minimal widget not aligned properly in RTL language.

[1.26.1] - 2016-03-24
----------------------
##### Added
- Hindi translation.

##### Changed
- Updated Slovak translation.
- Show version on home page.

##### Fixed
- If maxSubmissionSize request fails (e.g. unsupported on server) or the maxSubmissionSize value is updated, the form media resources are cleared.
- If /instance API endpoint is called for a survey that has never been launched the response URL contains a ::null enketo ID.

[1.26.0] - 2016-03-23
----------------------
##### Added
- Chinese translation.
- Limited IE11 support.

##### Fixed
- RTL form language right-aligns map layer options.
- Single-page form in pages mode throws exception and has no submit button.
- Very first time a form is stored in the browser, the query parameter to pass to submissions is not stored.
- When offline, and an attempt is made load a form with an uncached querystring, redirect to querystring-less URL.
- Submissions broken when basePath is used.

[1.25.1] - 2016-03-14
----------------------
##### Changed
- Redirect to new API v2 documentation from /api/v2.
- Updated French, Dutch, and Persian translations.

##### Fixed
- Languages not loading sometimes.
- Submit button not re-enabled after validation error.
- Performance degradation after changing a value in the form and upon submitting.
- Older browsers give "Array.from" error, when loading offline-capable webform.

[1.25.0] - 2016-03-09
----------------------
##### Added
- Enketo can now be configured with a base path, allowing Enketo to run with other servers on the same (sub)domain.

##### Removed
- Offline-capable iframe-friendly webform views and API endpoints.

##### Fixed
- Subtle 'required' message cannot be translated.
- Google maps tile layers not using https.

[1.24.1] - 2016-03-04 
----------------------
##### Added
- French translation.

##### Changed
- More modest font size for bold text, especially in Grid theme.
- Form UI elements also translatable.
- Updated Persian translation.

##### Fixed
- Options in select minimal are underlined.
- Group labels in RTL languages are left-aligned.
- When offline-capable webform is added to iOS homescreen it doesn't work.
- Submit button "busy" state is reset too early.
- Add-to-homescreen guidance only shows translation key.
- Exceptions occuring with file inputs on iOS devices.
- Only last media file in repeated file input is submitted.

[1.24.0] - 2016-02-23
----------------------
##### Added 
- Submission parameter now passed in offline-capable views too.
- Full-featured iframe-friendly offline-capable webform views.

##### Changed
- Webform URL format for iframe-friendly views (**WARNING: Always use API to get webform URLs to avoid regressions for your app.**)
- Different loader image, and now displayed in main brand color.

##### Removed
- Special client-side debugging mode. It is now always outputting log messages to the console.

##### Fixed
- Submit and Save-as-draft fail in offline-capable views if no values were changed.
- Submit and Save-as-draft buttons have incorrect font.

[1.23.2] - 2016-02-10
----------------------
##### Changed
- Form section headers are now left-aligned again.

##### Fixed
- In pages mode, adding a repeat to the current page scrolls to top of page.
- Constraint is evaluated twice when form value is changed (performance).
- Deleted default values re-appear when a record is loaded.
- Form scrolls to first question upon load.

[1.23.1] - 2016-02-09
----------------------
##### Changed
- Make form updates propagate much faster in offline-capable views.

##### Fixed
- Min() and max() return undefined for empty values.
- Parallel batch uploads may cause lost data in ODK Aggregate.

[1.23.0] - 2016-02-01
----------------------
##### Added
- Support for dynamic required expressions.
- Support for jr:requiredMsg.
- Basic support for big-image form attributes on itext values.
- Vietnamese translation.

##### Changed
- Updated Spanish, Slovak and Dutch translations.

##### Fixed
- Existing XForm content of secondary external instances not properly cleared if nodename is not 'root' or if multiple root-level nodes are present.
- Rogue XML namespace added in ODK Collect submission causes namespace incompatibility error when loaded for editing.

[1.22.1] - 2016-01-08
---------------------
##### Added
- Persian translation.

##### Changed
- Updated Dutch translation.

##### Fixed
- Empty lines in external CSV data result in empty items.
- Media files in recovered auto-saved record get lost during saving as a regular record.
- Auto-saving did not work with records loaded from storage. Only enabled for new records now.

[1.22.0] - 2016-01-01 
---------------------
##### Added
- Export functionality.
- Add-to-homescreen guidance for iOS/Safari, Android/Chrome and Android/Firefox.

##### Changed
- Links are underlined.
- Updated German, Dutch and Slovak translations.

##### Fixed
- Under some conditions surveys/list and surveys/number return too many results.
- Multiple span elements on same line get rendered as one span.
- Media files not removed from browser storage after submission.
- Media files from camera app in iOS get overwritten because the same filename is provided by the iOS camera pp.

[1.21.2] - 2015-12-18
---------------------
##### Changed
- Attempt to upload queue immediately after saving a final record.

##### Fixed
- If users logs out, queue cannot be submitted, no login UI shown.
- OpenRosa authentication: a change in auth status for one user causes global appCache refresh.

[1.21.1] - 2015-12-07
---------------------
##### Changed
- Show helpful "Use Safari on iOS" message when unsupported iOS browser is used.
- Updated Slovak, Dutch and Norwegian translations.

##### Fixed
- Empty error dialog when form fails to load.
- Form footer margins incorrect.
- Media & data form resource retrieval does not work with "external authentication".
- Media missing from submission in offline-capable views.

##### Removed
- "Experimental" warning message

[1.21.0] - 2015-12-01
---------------------
##### Added
- InstanceID logging of successful submissions (optional feature, **off by default**).

##### Fixed
- Submission counters not updated upon successful submission.
- Node 4 incompatibility.

[1.20.4] - 2015-11-25
---------------------
##### Added
- Slovak translation.

##### Changed
- Updated Italian, Dutch and German translations.
- Redirect all IE users to /modern-browsers page.

##### Fixed
- Clicking brand logo link with '#' value messes up offline views.
- Several issues where updating form media files did not properly update the form caches on server and client.
- File uploads in Chrome in offline-capable view fail to load after an hour (workaround for browser bug).
- If accompanying file for record cannot be retrieved, upload is blocked forever.
- NodeJS 0.12 incompatibility.

[1.20.3] - 2015-11-13
---------------------
##### Fixed
- If form resource retrieval fails, it won't be re-attempted upon next load
- Chevron icons in timepicker not shown.
- Current() does not switch context instance for relative paths in an XPath predicate.

[1.20.2] - 2015-11-02
---------------------
##### Changed
- Make form updates propagate quicker in offline webform views.

##### Fixed
- Themes with hyphen in name do not register.
- A label or hint that contains a \<span\> element without other markdown is not rendered as HTML.
- False 'Form has updated' messages appear continously every 20 minutes.

[1.20.1] - 2015-10-23
---------------------
##### Fixed
- External data loading failing.
- Encoded return URLs were not decoded.

[1.20.0] - 2015-10-22
---------------------
##### Added
- Ability to link to custom library to obtain account info.

##### Changed
- Previews now only allowed for forms hosted on linked server.

##### Fixed
- API /surveys/list and /surveys/number return error when linked server is "".
- Styling of load error dialog sometimes messed up.

[1.19.3] - 2015-10-21
----------------------
##### Fixed
- Media uploads failing 

[1.19.2] - 2015-10-19
----------------------
##### Fixed
- Previews not working with form query parameter.
- Directionality of language not correctly determined if first hint (or label, if no hints in form) has value '-'.

[1.19.1] - 2015-10-15
-----------------------
##### Fixed
- Language selector on small screens has right border.
- During loading the form footer is not positioned correctly, and loader image is not centered.

[1.19.0] - 2015-10-14
-----------------------
##### Added
- Next-page validation in pages mode.

##### Changed
- Analog scale picker behaviour when value is empty.

##### Fixed
- Question focus issues in pages mode.

[1.18.1] - 2015-10-07
-----------------------
##### Fixed
- Vagrant build failing due to npm version.
- Markdown lists generated if first item was not preceded by newline character.

[1.18.0] - 2015-10-06
-----------------------
##### Added
- Analog Scale picker

##### Changed
- Form footer styling.
- Location of required * now on left of question (in LTR language).

[1.17.0] - 2015-09-10
-----------------------
##### Added
- More comprehensive markdown support and now activated in all labels and hints.

##### Fixed
- If theme changed via API, offline view does not update.
- Edit view form injection fails with certain characters.

[1.16.0] - 2015-09-05
------------------------
##### Added
- Ability to disable themes in config.json.
- Support for pulldata function in XForms that contain a reference to the external data in the model.

##### Fixed
- Form initialization issue in Android (enketo-core 4.0.2)

[1.15.0] - 2015-08-28
------------------------
##### Changed
- Switched to CommonJS modules (**WARNING: forks with custom client scripts, tests need to be updated).

##### Fixed
- HTML titles not populated

[1.14.4] - 2015-08-26 
------------------------
##### Fixed
- Repeat buttons missing in Grid theme.
- Pulldowns get cut off when the extend beyond form border.
- Formfooter buttons in pages mode overlap form border.

[1.14.3] - 2015-08-13
------------------------
##### Changed
- Reduce space between border and form on small screens.

##### Fixed
- Loading a record with multiple repeats with missing nodes fails with error message.
- Select minimal widgets in Grid theme overlap other text in print view.

[1.14.2] - 2015-08-05
------------------------
##### Changed
- Repeat background color in Grid theme.
- Background color of selected radiobutton/checkbox on touchscreen in non-Grid themes.

##### Fixed
- Repeat button location in Grid theme.
- Radio buttons inside cloned repeat, require 2 clicks if the master was selected.
- Radio button and checkbox default values not populated correctly in cloned repeat. Overriding values in first repeat. 
- Indexed-repeat() result incorrect if expression is inside 2+ repeat.
- Webform not responsive when used in full-size iframe.

[1.14.1] - 2015-07-30
------------------------
##### Fixed
- In pages mode, an exception occurs after submission showing empty page.
- In pulldown select radiobuttons/checkboxes not aligned properly.

[1.14.0] - 2015-07-29
------------------------
##### Added
- Appearance "compact-n" support for media grid pickers.

##### Fixed
- Indexed-repeat() expressions not working if the position is dynamic.
- Page navigation buttons messed up on small screen in pages-mode.
- Top-level (non-grouped) questions on first row do not have a top border.
- Language options in form language selector oddly aligned when mix of rtl and ltr languages is used (FF).
- Title directionality is not displayed according to script used in Grid theme.

[1.13.0] - 2015-07-27
-----------------------
##### Added
- Right-to-left form language directionality support.

##### Changed 
- Made page-swipe less sensitive on touchscreens in pages-mode.

[1.12.2] - 2015-07-24
-----------------------
##### Fixed
- Error message is not useful when formList is found to be empty.
- Form injection fails with certain arabic characters.

[1.12.1] - 2015-07-20 
------------------------
##### Fixed
- Nested branches do not get evaluated when the parent is enabled.

[1.12.0] - 2015-07-08
------------------------
##### Added
- Right-to-left UI language directionality support.

##### Changed
- Vagrant setup script updated.

##### Fixed
- Validation error dialog message not translated.
- Fallback (english) language not cached in offline views.
- Geo Widget map tiles only partially loaded if widget not visible upon initial form load.

##### Removed
- Non-functional export button removed until the functionality can be added.

[1.11.1] - 2015-06-29
------------------------
##### Fixed
- API endpoint /surveys/list does not include server_url property in each survey item.
- Formhub authentication regression. **WARNING: Formhub users, see additional config.json setting to work around formhub bug.**
- Media for protected forms cannot be retrieved (on strict compliant OpenRosa servers).

[1.11.0] - 2015-06-25
------------------------
##### Added
- Auto-save unsaved data in offline-capable webform views
- API endpoint /surveys/list

##### Fixed
- A note preceding a traditional table is formatted as a group label.
- A note following a traditional table is formatted as a group label.
- Incorrect error message shown when loading a record with a file in the edit view.

[1.10.0] - 2015-06-18 
------------------------
##### Changed
- OpenRosa Form ID is now case-sensitive. **WARNING: any existing forms that have a form ID that included a capitalized letter, will get a new Enketo ID. Existing Enketo IDs will keep working though.**

##### Fixed
- Groups and repeats missing from print view in pages mode.
- Sidebar handle is shown up in print view.
- Back button in pages shows merged pages after form reset.
- Incorrectly capitalized form IDs result in unlaunchable forms. 
- First page in pages mode is shown if it is disabled.
- Existing trigger value not populated in form.

[1.9.1] - 2015-06-16
------------------
##### Added
- Swahili language

##### Changed
- Improved performance in logic evaluation.

##### Fixed
- Firefox only prints first page.
- Failing to load record.
- Records with nested repeats loaded incorrectly and completely corrupting model.

[1.9.0] - 2015-05-28
------------------
##### Added
- Index-repeat() support

##### Changed
- Faster loading

##### Fixed
- Calculations on select_one inside a repeat clone throw an exception.
- Irrelevant questions inside a repeat clone are shown but should be hidden.
- Calculations inside repeat clones are not evaluated upon form load.

[1.8.9] - 2015-05-08
------------------
##### Added 
- Enable print script for themes based on Grid Theme that include "grid" in the theme name.

##### Changed
- Do not attempt to load table/radio/likert/media grid widgets when they are not required.
- Even faster validation for some forms.
- Better performance of large default repeat creation with jr:repeat-count.

##### Fixed
- Screen view remaining at full screen width after printing form with Grid Theme.
- Print dialog buttons not visible with Grid Theme (Enketo Express).
- Sequential notes overlapping each other with Grid Theme.
- Exception occuring in some specific cases when loading an existing record.
- Click lag (especially on mobile) due to slow progress bar update.

[1.8.8] - 2015-04-23
-------------------
##### Changed
- Branch update performance
- Calculate update performance 
- Widget loading performance, **WARNING: remove triggerwidget, add horizontal choices widget, see [default-config](./config/default-config.json)**

##### Fixed
- Top border missing and margin too small when a visible note is preceded by a hidden note.
- Any branch containing a geoshape widget caused an exception to occur when it was made irrelevant.
- Appearance 'horizontal' no longer displays with evenly-spaced columns.
- Some buttons in Safari have border and background when they shouldn't have.
- Side bar in Safari is not stretching to bottom.

[1.8.7] - 2015-04-17
------------------
##### Added
- Italian language
- Romanian language

##### Fixed
- All forms with logic broken in Internet Explorer.
- When existing instance with multiple repeats is loaded, only the first repeat is created and populated.
- XML nodenames ending with hyphen or underscore failed to be found.

[1.8.6] - 2015-04-15
---------------
#### Fixed
- Broken submissions.

[1.8.5] - 2015-04-15
---------------------
##### Added
- Arabic language (left-to-right still).

##### Changed
- Text and number inputs in Grid Theme now displayed in full cell width.
- Updated Greek, German, and Dutch language.

##### Fixed
- Geowidget not displayed displayed in full width in pages mode with Grid Theme.
- Hide/show input fields button in Geo Widgets in Grid Theme not clickable after clicking show.
- Remove existing content form external instances to enable ODK Validate hack.
- Reliance on .csv extension for external data broke broke Aggregate support.

[1.8.4] - 2015-04-09
---------------
##### Changed
- Allow empty Google Analytics domain in configuration.

##### Fixed
- Authentication not working on https (reverse proxy).
- API URLs not returning https (reverse proxy).

[1.8.3] - 2015-04-08
---------------
##### Added
- German language
- Greek language

##### Changed
- Much faster form validation.

##### Fixed
- Not showing 'save as draft' in pages mode.

[1.8.2] - 2015-03-23
---------------
##### Added
- Show supported languages on front page.

##### Fixed
- Media files not submitted in offline-enabled views.

[1.8.1] - 2015-03-17
------------
##### Fixed
- Installation with Vagrant failed.
- Local Redis configuration was ignored.

[1.8.0] - 2015-03-09
-----------
##### Added
- Support for external instance sources, CSV and XML
- Spanish language

[1.7.1] - 2015-02-27
-----------
##### Changed
- Configuration now done with local config.json that overrides default (rename existing config/config.json before updating!).
- Dutch translation
- Authentication documentation

##### Fixed
- Installation with Vagrant.
- In media input widget, when media is too large, record is still populated with file name.
- Broken form retrieval with formhub servers.
- Error message 'ECONNREFUSED' not correctly changed to human-readable message. 

[1.7.0] - 2015-02-19
-----------
##### Added
- Meta data for username
- Meta data for deviceid
- OpenRosa authentication
- Change log

##### Changed
- API v2 documentation

##### Fixed
- Form cache on server would not update if XForm content (only) changed

[1.6.1] - 2015-02-19
-----------
##### Added
- Panic button to clear browser database

##### Fixed
- Redirect IE9 and less to Modern Browsers page
- Manifest taking over all error pages and redirecting to 'offline' page.

[1.6.0] - 2015-02-12
-----------
##### Added
- Full offline capability
- Grid Theme
- Temporary API v2 documentation

##### Changed
- API access of parameters using a modern method.

##### Fixed
- Grid theme in pages mode shows all questions at full width.
- File inputs keep shows file name after input is emptied.

[1.5.1] - 2014-12-31
-----------
##### Fixed
- Repeat groups not working when they have no \<group\> wrapper.
- Multiple markdown links in a note are merged into one.

[1.5.0] - 2014-12-30
-----------
##### Added
- Internationalization of user interface
- Dutch language
- Populate page title with name of form

##### Fixed
- False 'edited' event firing.
- Multipe markdown links in a note are merged into one.
- Select minimal in first repeat not working right.

[1.4.0] - 2014-12-18
-----------
##### Added
- Support for multipe themes.
- Theme switching via API (v2)

##### Changed
- Styling of 'Pages mode' buttons

##### Fixed
- Stretch short forms and short pages to full height of screen.
- KoBo/Formhub themes occassionaly print in screen style when print button is used.
- Incorrect dialog positioning.

[1.3.1] - 2014-12-16
-----------
##### Fixed
- App breaks when form is loaded with a default value for geopoint/geotrace/geoshape.

[1.3.0] - 2014-12-12
-----------
##### Added
- Ability to paste KML coordinates in geoshape widgets.
- Ability to add Google Maps layers for geo widgets.

[1.2.1] - 2014-12-05
-----------
##### Added 
- Ability to print from iframe views.

#### Fixed
- Send X-OpenRosa-Version header to comply with OpenRosa specs.

[1.2.0] - 2014-11-11
-----------
##### Added
- External authentication support.

[1.1.1] - 2014-11-08
-----------
##### Fixed
- Instance API endpoint does not add return URL to response.

[1.1.0] - 2014-11-08
-----------
##### Added
- Ability for iframed view to post message to parent window.

##### Changed
- Hide print button in iframe views

##### Fixed
- Crash in Internet Explorer 10 (due to use of console.time).
- Various iframe issues.
- Issue with reporting edit status of current form.

[1.0.3] - 2014-11-07
-----------
##### Fixed
- Various issues with modal dialogs

[1.0.2] - 2014-11-06
-----------
##### Fixed
- Time, date and datetimepickers are reset when user clicks Enter elsewhere in form

