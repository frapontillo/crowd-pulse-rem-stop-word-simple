crowd-pulse-rem-stop-word-simple
================================

Text-based Crowd Pulse stop word remover for tags, tokens and categories.

--------------------------------

The `simple` plugin needs a series of stop words files in the class loader accessible resources 
directory. These files will be loaded if specified in the plugin configuration, e.g.:

```json
    "stop-word-step": {
        "plugin": "simple",
        "config": {
            "apply_to": ["tokens", "tags", "categories"],
            "dictionaries": {
                "all": ["stop-words-{{LANG}}", "generic-stop-words"],
                "tokens": ["stop-words-{{LANG}}-tokens", "some-tokens"],
                "tags": ["stop-words-{{LANG}}-tags"],
                "categories": ["stop-words-{{LANG}}-categories", "exclude-categories"]
            }
        }
    }
```

Where:

* `apply_to` defines which elements will be marked for stop word removal among `tokens`, `tags` and `categories`
* `dictionaries` contains lists of file names containing stop words for all or some among tokens, tags, categories
* `{{LANG}}` is a placeholder for a two-character lang code that will be replaced at runtime with the message language
  (this way you can create multiple stop word lists, and each can be specific for a particular element type and for a 
  language)

You can download stop words files for some languages [here](https://github.com/frapontillo/stop-words).
  
## License

```
  Copyright 2015 Francesco Pontillo

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.

```