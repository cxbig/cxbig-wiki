# Ruby - Data Type - JSON

## Samples

### Parse : string to object

```rb
require 'json'

str = "{\"name\":\"cxbig\",\"age\":30,\"role\":[\"PHP Developer\",\"DevOps\"]}"
JSON.parse str
# => Hash 
# {
#   name: 'cxbig',
#   age: 30,
#   role: [
#     'PHP Developer',
#     'DevOps'
#   ]
# }
```

### Parse : object to string

```rb
require 'json'

person = {
    name: 'cxbig',
    age: 30,
    role: [
        'PHP Developer',
        'DevOps'
    ]
}

person.to_json
# or
JSON.unparse person
# => "{\"name\":\"cxbig\",\"age\":33,\"role\":[\"PHP Developer\",\"DevOps\"]}"

JSON.pretty_generate person
# =>
# {
#   "name": "cxbig",
#   "age": 30,
#   "role": [
#     "PHP Developer",
#     "DevOps"
#   ]
# }
```

Tips:
- `Hash` has no `to_json` method except you `require 'json'`


