# prm-parser
Simple python script to edit Nintendo's PRM file format for GCN

# Usage
## CLI
The CLI arguments are the following:
`python prmparser.py <path-to-source-file> <job> <destination-path>`

- If `<path-to-source-file>` is a folder, it will recusrively search the folder and all subfolders for valid source files to compute
- If `<destination-path>` is a folder, it will dump the result into that folder, retaining the name of the source
- `<job>` can be either `c` (compile), `d` (decompile), or `i` (init)

## Template File
Entries follow the format `key = type(value)`, and are seperated by line

Comments are defined by the `#` character

---

Allowed types are as follows:
- s8
- s16
- s32
- s64
- u8
- u16
- u32
- u64
- f32
- f64
- str
- bool
- bytes
- list

Examples
- u8(78)
- u8(0x45)
- s16(-1345)
- f32(0.341)
- f32(123.5f)
- bool(true)
- u64(0x2388328388238)
- str(Example String)
- bytes(0x0102030405060708090A0B0C0D0E0F10)
- list(u8(0x58), u16(0x2382), s8(-17))

---

Thus, a typical prm template should look like this:

```
# This comment is really awesome!
mMyIntKey   = u32(0x12345678)
mMyFloatKey = f32(3.14) #PI haha so funny :)
mMyStrKey   = str(Wow, a string!)
mMyListKey  = list(u8(1), u8(2), u8(3), u8(4))
```
