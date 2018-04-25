# This is a productivity/time tracker tool

Feeling overwhelmed? Can't remember what you did specifically 2 hours ago, 30 minutes ago, 6 hours ago?

This tool could help!

Listening to [weekly dev tips #21](http://www.weeklydevtips.com/021), inspired me to code this, as I thought the [timesnapper](http://www.timesnapper.com/) idea was great, and so simple... and just what I needed!

Basically, let's take a screenshot every minute. That'll be 600 images for a 10 hour work day.

Playing back 1 image per second would take 10 minutes, so instead let's playback 5 images per second and get a day's work recap under 2 minutes!

## Runs as a systemd user process

This seems the best solution, as opening up DISPLAY and XAUTHORITY to a dedicated user doesn't seem worth it.

## Dependencies

- ruby
- feh (basic image viewing, provides a slideshow functionality)
- imagemagick (for timestamping screenshots, makes following the slideshow easier)
- scrot (basic screenshoting tool)

## Install/remove

    ./manage/install
    ./manage/uninstall

## Usage

1. Install

2. Extract today's info, see what you've been working on

    scrot-service-read
    scrot-service-read movie
    scrot-service-read reverse
    scrot-service-read movie reverse

3. Check logs

    journalctl --user-unit scrot.service --since today -f
