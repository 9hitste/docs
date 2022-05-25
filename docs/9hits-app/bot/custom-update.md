# Custom update

---------

## Overview
In case you have a lot of computers which running the bot, and you need to change the settings for these computers in bulk, such as proxy list, campaigns, user-agents, or anything else.

If you just want update your proxy list only, it is recommended to set [the Proxy Source option](configuration.md) to an URL link to your proxy text file. Eg: `http://my-site.com/proxies.txt`. So every time you need to update your proxy list, just update the file `proxies.txt` on your host.

## How does it works?
In the setting, we have two options:

* Update Url: URL to check your update version. It should be a simple text file, containing the content in the following format: `version_number|download_update_url`
* Frequency Check: Time to periodically check your update version from the `Update URL` in minutes.

The bot will periodically check for the information from your Update URL. Your latest version number will be saved at the `config/bot/custom-version.txt` file.

If the saved version number is differs from your version number on the `Update URL`, the bot will download the zip file from the `download_update_url`, unzip the update file and restart itself.

For example we have an `Update Url` is `http://my-site.com/check.txt` with the content
```
9999|http://my-site.com/update.zip
```

In the `Update Url`, the current version number is `9999`, to do the update, we just need to prepare a new update file and upload to `my-site.com/update.zip`, in this example it is `update.zip`, then change the version number in the file `my-site.com/check.txt` to let the bot know that it needs to download the new update file. For example:
```
10000|http://my-site.com/update.zip
```

You can see the current custom version of your update from the [9Hits Panel](https://panel.9hits.com/bot/sessions), it is the `CustomVersion` column.

!!! warning
    The update file will be extracted from the root directory of the app, so please note the directory structure and files in your update file.