Qui aliqua commodo laborum ad consequat pariatur. Amet consequat pariatur ex et nostrud sint laborum duis aute. Cillum consequat amet occaecat id sint. Aliquip consequat do incididunt enim cillum elit reprehenderit incididunt ut in eu qui culpa.

## Versioning
The API uses [Semantic Versioning](https://semver.org). This means that any non-backward compatible change will result in an increment of the major version (`1.x.x` --> `2.x.x`). You can be confident that your integration will remain stable across updates, as long as the major version does not change.
Versions correspond to the [API Reference](../reference/index.md).

### Changelogs
* Version [`v1.x.x`](../reference/v1-x-x.md) represents the initial release of the API.

---

## Quick Start Guide
* Adding the api to your project
* Initializing the API
* Amet ex quis magna ullamco amet.
* Ad id quis proident dolore irure nostrud minim labore laboris anim sint.

### Adding the api to your project
1. Download the [Api file]().
2. Put in your project directory, under `/lua/api`.
3. Do not rename it, or you will need to change `#!lua require("api/BeamPermsAPI")`!

If you did everything correctly, your project should look something like this:
```hl_lines="2-3"
my_plugin/
├── lua/
│   └── api/
│       └── BeamPermsAPI.lua
└── main.lua
```

### Initializing the API
1. Requiring the API file
```lua
BP = require("api/BeamPermsAPI")
```
2. Checking if the API is available
```lua
if BP.isDisabled() then
  ... -- The API is not available, functions will not be registered!
end
```

Which gives us the final code for the API:
```lua linenums="1"
BP = require("api/BeamPermsAPI")

...

if BP.isDisabled() then
  print("BeamPermsAPI is disabled, ...")
end
```

**:tada: You can now use the API**