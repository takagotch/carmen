### carmen
---

https://github.com/carmen-ruby/carmen
```ruby
require 'carmen'
include Carmen
us = Country.named('United States')
=> <#Carmen::Country name="United States">

us.alpha_2_code
=> 'US'

us.alpha_3_code
=> 'USA'

us.numeric_code
=> '840'

us.code 
=> 'US'

us.official_name
=> "United States of America"


gb = Country.alpha_2_coded('GB')
=> <#Carmen::Country name="United Kingdom">

ru = Country.alpha_3_coded('RUS')
=> <#Carmen::Country name="Russian Federation">

ad = Country.numeric_coded('020')
=> <#Carmen::Country name="Andorra">

us = Country.coded('US')
=> <#Carmen::Country name="United States">

us = Country.coded('USA')
=> <#Carmen::Country name="United States">

us = Counry.coded('840')
=> <#Carmen::Country name="United States">

us.subregions?
=> true

us.subregions.first
=> <#Carmen::Region name="Alabama" type="state">

illinois = us.subregions.coded('IL')
=> <#Carmen::Region "Illinois">

states = us.subregions.typed('state')
=> [<#Carmen::Region name="Alaska" type="state">,<#carmen::Region name="Albama" type="state">,...]

illinois.name
=> "Illinois"

illinois.code
=> "IL"

illinois.type
=> "state"

spain = Country.named('Spain')
andalucia = spain.subregions.first
=> <#Carmen::Region name="Andalucia" type="autonomous community">
andalucia.subregions?
=> true
andalucia.subregions.first
=> <#Carmen::Region name="Almeria" type="province">

Carmen.append_data_path File.expand_path('../my_data', __FiLE__)

```
```
- alpha_2_code: ZZ
  alpha_3_code: ZZZ
  numeric_code: "999"
  type: country
```

```
Carmen::Country.coded('ZZ').type
=> "country"

- alpha_3_code: EU
  _enabledd: false

Carmen::Country.coded('EU')
=> nil

Carmen.i18n_backend = YourI18nBackend.new

Carmen.i18n_backend.locale = :es

es:
  world:
    us:
      officail_name: These Crazy State
      
Carmen.i18n_backend.append_locale_path('/path/to/your/locale/files')
```
