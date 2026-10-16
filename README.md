# spotify-player-overlay

A minimal Gentoo overlay providing `media-sound/spotify-player-0.25.1`
(`~amd64`). Upstream requires **Spotify Premium**.

With `app-eselect/eselect-repository` installed, add and sync the overlay:

```sh
sudo eselect repository add spotify-player-overlay git https://github.com/vovanbl411/spotify-player-overlay.git
sudo emerge --sync spotify-player-overlay
```

Accept the initial testing keyword, then install:

```sh
echo 'media-sound/spotify-player ~amd64' | sudo tee /etc/portage/package.accept_keywords/spotify-player
sudo emerge --ask media-sound/spotify-player
```

The default USE flags enable rodio streaming and MPRIS media control. On Linux,
rodio outputs through ALSA; the validated runtime path is ALSA through PipeWire.
Optional flags are `daemon`, `fzf`, `image`, `notify`, and `pixelate`.
`daemon` requires `streaming`; `pixelate` requires `image`.

See [upstream](https://github.com/aome510/spotify-player/tree/v0.25.1)
for authentication, application configuration, and usage.
