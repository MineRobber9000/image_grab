# image grab

A set of programs to enable an "image grab" type site.

## How it works (when set up)

1. You locate an image you want to see, that is blocked (for whatever reason) 
where you're trying to look at it.
2. You go on the server you're running the grab on, and run `grabimg <url>`.
3. It spits out a URL you can use to see the image.
4. Once the image has been in the grab for about 1 hour, it's deleted. Goodbye!

## How to set it up

Put `grabimg` and `rawurlme` in your `~/bin` directory, making sure to change 
PATH to your image grab directory in `grabimg` and properly setting up 
`rawurlme`.

Put `grab_expire_cron` somewhere, and then add a line to your crontab like so:
```
*/15 * * * * /path/to/grab_expire_cron
```
This will check every 15 minutes for files that have existed for over an hour,
and delete them. For extra granularity, you can lower the check to every 5
minutes, or even set it to check every minute.

Congrats! Your image grab is now functional!
