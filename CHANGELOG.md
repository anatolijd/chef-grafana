# CHANGELOG for grafana

This file is used to list changes made in each version of grafana.

## 1.1.0:

__breaking changes__

* `config.js` data for `graphite` and `elasticsearch` changed back to use:

  - `window.location.protocol+"//"+window.location.hostname+":"+window.location.port+"/_graphite"`
  - `window.location.protocol+"//"+window.location.hostname+":"+window.location.port`

  The idea is to allow external access without `CORS` problems or credential leaks in `config.js`.

* Value for `default['grafana']['install_path']` changed from `/opt` to `/srv/apps` (Greg Fitzgerald) [#13](https://github.com/JonathanTron/chef-grafana/pull/13)
* Default installation uses zip file instead of git (Greg Fitzgerald) [#13](https://github.com/JonathanTron/chef-grafana/pull/13)

__minor changes__

* Major cleanup and additional tests (Greg Fitzgerald) [#13](https://github.com/JonathanTron/chef-grafana/pull/13)

## 1.0.6:

* Releasing to opscode community site [Thanks to @gregf in #12](https://github.com/JonathanTron/chef-grafana/pull/12)

## 1.0.5:

__breaking changes__

* `config.js` was unintentionally changed to use node info to configure graphite and elasticsearch index.
* Value for `default['grafana']['grafana_index']` changed from `grafana-dash` to `grafana-index` (Greg Fitzgerald) [#11](https://github.com/JonathanTron/chef-grafana/pull/11)
* Update grafana to 1.6.0 (Greg Fitzgerald) [#11](https://github.com/JonathanTron/chef-grafana/pull/11)

## 1.0.4:

* Update config.js based on the one in 1.5.4
* Update to grafana 1.5.4
* Update to new download URL

## 1.0.3:

* Add some basic specs, foodcritic, knife test and enable TravisCI

* Fix error with undefined grafana_user variable [Thanks to @klamontagne](https://github.com/JonathanTron/chef-grafana/commit/50fa3836dcf410e37b96533e25d952e8bc6c2472#commitcomment-5857007)

* Fix timezone value quoting in config.js (Anatoliy D.) [#9](https://github.com/JonathanTron/chef-grafana/pull/9)

* Update grafana to 1.5.2 (Grégoire Seux) [#7](https://github.com/JonathanTron/chef-grafana/pull/7)

* Don't set normal attribute `node['nginx']['default_site_enabled']` (Grégoire Seux) [#5](https://github.com/JonathanTron/chef-grafana/pull/5)

* Remove `"use strict";` from `config.js` as it seems to not be present in
  grafana releases, thanks to @iiro for proposing it in [#1](https://github.com/JonathanTron/chef-grafana/pull/1)

* Don't search when `node['grafana']['es_server']` or `node['grafana']['graphite_server']`
  is set and don't use normal attributes (Grégoire Seux) [#3](https://github.com/JonathanTron/chef-grafana/pull/3)

* Refactor and separate install in two recipes: `install_git` and `install_file`
  (Grégoire Seux) [#2](https://github.com/JonathanTron/chef-grafana/pull/2)

## 1.0.2:

* Update file release to 1.5.1

## 1.0.1:

* Update file release to 1.5.0

## 1.0.0:

* Initial release of grafana
