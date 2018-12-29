# [hide] BBCode

With the [[hide] bbcode][5], members can hide their message content from people that haven't posted in their topic. One can also choose whether or not attachments should be hidden.
Compatibility has been added for these extensions:
 * [Thanks for Posts][1]: You can choose in the ACP that people can also (or only) unhide [hide] codes by thanking the user for the post. Thanks on posts containing a [hide] code may not be deleted.
 * [Quick Reply][2]: When needed, page reloads after a quick reply.

Caution should be taken with these extensions:
 * [Topic Preview][3]: This extension [seems][4] to display the hidden text by default. You can disallow the BBCode to show up in the ACP of Topic Preview.

## Installation:
 * Copy the contents of the extension to ext/marcovo/hideBBcode/
 * Install the extension under ACP -> Customise -> Manage extensions.
 * Configure the extension under ACP -> Extensions -> [HIDE] BBCODE -> General settings


```
#!/bin/sh

# Define path
TMP_PATH="/tmp"
PHPBB_PATH="/var/www/phpbb/"
PHPBB_EXT_PATH="/var/www/phpbb/ext/"

# Purge cache
cd $PHPBB_PATH
cd cache
rm -r production

# Install thanks for posts
cd $TMP_PATH
rm -r thanks_for_posts
git clone https://github.com/Naguissa/thanks_for_posts.git
cd thanks_for_posts
git checkout tags/3.2.11 -b 3.2.11
cp -r gfksx/ $PHPBB_EXT_PATH

# Install hidebbcode
cd $PHPBB_EXT_PATH
mkdir -p $PHPBB_EXT_PATH/marcovo
cd marcovo
rm -r hideBBcode
git clone git@github.com:johnelliotbaker/hideBBcode.git 
```


 [1]: https://github.com/rxu/thanks_for_posts
 [2]: https://github.com/Tatiana5/QuickReply
 [3]: https://github.com/VSEphpbb/topicpreview
 [4]: https://www.phpbb.com/community/viewtopic.php?p=14164491#p14164491
 [5]: https://www.phpbb.com/community/viewtopic.php?f=456&t=2279486
