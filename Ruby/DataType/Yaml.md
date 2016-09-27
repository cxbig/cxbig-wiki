# Ruby - Data Type - Yaml

## Samples

### Read & Write

```rb
require 'yaml'

# File profile.yml
# ---
# name: cxbig
# age: 30

person = YAML.load_file('profile.yml')

p person['name']
# => 'cxbig'

person['job'] = 'DevOps'

File.open 'profile.yml', 'w' do |f|
  f.write person.to_yaml
end

# File profile.yml
# ---
# name: cxbig
# age: 30
# job: DevOps
```


