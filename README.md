[hub]: https://hub.docker.com/r/wizfrk/hath/

# wizfrk/hath

[hub]

![e-hentai.org banner](https://forums.e-hentai.org/uploads/post-2104618-1420415820.png)

Hentai@Home (H@H) is a Peer-2-Peer gallery distribution system which reduces the load on the E-Hentai Galleries. Current version: 1.4.2

H@H is a project that can be compared to a cross between the SETI@home project and BitTorrent.

All participating users run a small Java-based client that downloads files from the main E-Hentai servers to their computer and passes those files on to people who browse the E-Hentai Galleries. This allows E-Hentai to serve many more images using less server bandwidth.

The client may be run freely for any duration of time but it is recommended to run it continuously for as long as possible for maximum rewards.

For more info including requirements and technical data see: https://ehwiki.org/wiki/Hentai@Home

## Usage
```
docker run \
  --name hath \
  --ports: <port>:6969 \
  -v /path/to/your/hath/cache:/hath/cache \
  -v /path/to/your/hath/data:/hath/data \
  -v /path/to/your/hath/download>:/hath/download \
  -v /path/to/your/hath/log:/hath/log \
  -v /path/to/your/hath/tmp:/hath/tmp \
  -e HATH_KEY=YOUR_HATH_CLIENT_ID:YOUR_HATH_CLIENT_KEY \
  -e TZ=YOUR_TIMEZONE \
  wizfrk/hath
```

## Parameters

* `--net=host` - Uses host network with container, use this if H@H have trouble accepting connections. This will let H@H use the host's internal IP for routing instead of the internal IP used by Docker bridge.
* `-v /hath/cache` - H@H cache folder
* `-v /hath/data` - H@H data folder
* `-v /hath/download` - H@H download folder
* `-v /hath/log` - H@H log folder
* `-v /hath/tmp` - H@H tmp folder
* `-e HATH_ID` - H@H Client ID:H@H Client Key
* `-e TZ` - Timezone H@H will run in
