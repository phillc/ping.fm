== a simple ruby wrapper for the ping.FM service ==

This is a simple library to automate posting to ping.FM service.

Uses the v1 API:
http://groups.google.com/group/pingfm-developers/web/api-documentation?_done=%2Fgroup%2Fpingfm-developers%3F

Dependencies:
gem: rest_client - http://github.com/adamwiggins/rest-client

      config.gem 'adamwiggins-rest-client', :lib => 'rest_client', :source => 'http://gems.github.com'

Sample Usage:

in config/ping_fm.yml

    development:
      api_key: ........
      user_app_key: ........
    production:
      api_key: ........
      user_app_key: ........


elsewhere:

    PingFM.user_post("status", "hey guys! I'm posting to ping.FM!")

You can also pass additional options:

    PingFM.user_post("status", "hey guys! I'm posting to ping.FM!", :tags => "fun, times", :mood => "emo-happy")

See the v1 API from ping.FM for more details.

Could totally use some work:

* opts parsing in each call to make sure required fields are sent and 
  optional too for v1 of the API
* some optional meta or defining a method_missing to attempt to
  handle all API methods automatically
* reading of config through a yaml for API keys
* parsing of the xml_result into a ruby hash or something cooler using 
  xml-simple or lib-xml
* more awesomeness....

Feel free to fork, add features, or request features.

-- Charles Brian Quinn <cbq at highgroove dot com>
