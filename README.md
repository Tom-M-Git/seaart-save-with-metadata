For **filename**:

Filename `c730a1ed0bda90fa1857eca8392a7db7_high.webp` will become `seaart-official.2025-09-22.seaart-film.seaart-film.2025-11-21.webp`.

Where each part is `[username]`.`[work created]`.`[basemodel]`.`[checkpoint]`.`[seed]`.`[file created]`.`webp`. Some will be empty if they're absent.

The structure of the name is subject to change in the future.

Filename is **sanitized** to be filename-safe during process (except for CJK.) For example,

**spaces** -> `-`

**CAPITAL LETTERS** -> **small letters**

**CJK** -> **Kept as-is** (as there is no way I know to reliably romanize all CJK letters. Japanese is the chaotic example.)

**multiple hyphens** -> `-`

Leading and trailing spaces -> trimmed

Leading and trailing dots `.` -> trimmed

For **XMP**,

`Title` = Page title

`Creator` = User on SeaArt

`Subject` = `ai-generated`, `prompt`

`Source` = URL of work

`Description` = `"prompt": "", "model": "", "checkpoint": "", "lora": [], "sampler": "", "steps": "", "cfg scale": "", "seed": "", "work created": ""`

**Regex** is applied before embedding `title` and `prompt`. For example,

**CJK punctuations** / **Full-width punctuations** -> **Latin (half-width) punctuations**

**full-width parentheses** -> **half-width**

**full-width spaces** -> **half-width**

**multiple redundant spaces** -> **single spaces**

**multiple parentheses** -> **split with spaces** e.g. `(( ))` -> `( ( ) )`
> Because image viewers like **XnView** for some reasons, automatically removes everything inside double or triple brackets and themselves in XMP after written and saved. So to safely keep it all. Although ExifTool seems to still keep the data, it does so for better safety.
