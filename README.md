## How do I use it?
1. [Download your Twitter archive](https://twitter.com/settings/download_your_data) (Settings > Your account > Download an archive of your data).
2. Unzip to a folder.
3. Copy [parser.py](https://raw.githubusercontent.com/timhutton/twitter-archive-parser/main/parser.py) into the same folder. (e.g. Right-click, Save Link As...)
4. Run the script with [Python3](https://realpython.com/installing-python/). e.g. `python parser.py` from a command prompt opened in that folder.

If you are having problems, the discussion here might be useful: https://mathstodon.xyz/@timhutton/109316834651128246

## What does it do?
The Twitter archive gives you a bunch of data and an HTML file (`Your archive.html`). Open that file to take a look! It lets you view your tweets in a nice interface. It has some flaws but maybe that's all you need. If so then stop here, you don't need our script.

Flaws of the Twitter archive:
- It shows you tweets you posted with images, but if you click on one of the images to expand it then it takes you to the Twitter website. If you are offline or have deleted your account or twitter.com is down then that won't work.
- The tweets are stored in a complex JSON structure so you can't just copy them into your blog for example.
- The images they give you are smaller than the ones you uploaded. I don't know why they would do this to us.
- The links are all obfuscated in a short form using t.co, which hides their origin and redirects traffic to Twitter, giving them analytics. Also they will stop working if t.co goes down.

Our script does the following:
- Converts the tweets to [markdown](https://en.wikipedia.org/wiki/Markdown) with embedded images, videos and links.
- Replaces t.co URLs with their original versions.
- Copies used images to an output folder, to allow them to be moved to a new home.
- Afterwards, it asks if you want to try downloading the original size images using [download_better_images.py](https://raw.githubusercontent.com/timhutton/twitter-archive-parser/main/download_better_images.py).

## TODO:
- Output as HTML files?
- Parse likes and DMs too (Issues [#22](https://github.com/timhutton/twitter-archive-parser/issues/22) and [#6](https://github.com/timhutton/twitter-archive-parser/issues/6))

