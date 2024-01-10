> This is a hard fork from jbmorely/showrss 
> Intended for personal use only (i.e. no support is offered, but use it if you like.)

# Showrss

Fetch the latest links from a ShowRSS feed, and add them to a torrent client.

Added magnets are cached in `~/.showrss_cache`

# Requirements

Install the requirements:

```bash
pip install -r requirements.txt --use-mirrors
```

Run:

```bash
python showrss.py
```

# Configuration

`showrss` expects to find a configuration file at `~/.showrss`:

```ini
[default]
user_id = 12345
command = transmission-remote -a
quality = default
```

The configuration file defines two things:

### user_id

Your ShowRSS user identifier.

You can find this by clicking on the 'feeds' link and generating a personal feed. The URL for the feed will be something like:

    http://showrss.info/rss.php?user_id=12345&hd=null&proper=null

Your user_id is the value after `user_id=`. `12345` in this example.

### command

The command-line for starting torrents. The torrent URL is appended to the end of the command.

Transmission on Linux:

```ini
command = transmission-remote -a
```

Transmission on OS X:

```ini
command = open /Applications/Transmission.app
```

### quality (optional)

The desired show quality. May be one of:

- `default` - ShowRSS per-show settings
- `standard` - Only standard torrents
- `high` - Only 720p HD torrents
- `all` - Both types of torrents

# License

`showrss` is available under the MIT license. See the LICENSE file for more info.
