# Earport privacy policy

Last updated: 30 September 2026

This policy explains what information the Earport desktop app handles, where
it is kept, and which outside services it talks to.

## Who we are

Earport is made by Lachlan Holt, an individual developer in Australia
("I", "me"). Contact: earport.support@gmail.com

## The short version

- **I collect nothing.** Earport has no analytics, telemetry, crash
  reporting, advertising or tracking, and there is no Earport account. No
  information about you or how you use Earport is sent to me.
- Your library, playlists, settings and logs stay on your computer.
- Earport only contacts outside services to do things you ask for, such as
  importing a playlist or downloading a song, plus a check for Earport
  updates. Those services receive what is described below.

## What is stored on your computer

Everything Earport stores is on your own computer. None of it is uploaded
to me.

| What | Where |
| --- | --- |
| Your library: music files, playlists, artwork and the Earport database (`earport.db`) | The library folder you chose. By default `%USERPROFILE%\Earport`. |
| Settings, including your Spotify Client ID and the folders you chose | `%APPDATA%\com.earport.app\settings.json` |
| Logs (file paths, song titles and errors, for troubleshooting). Kept for 14 days, then deleted automatically. | `%APPDATA%\com.earport.app\logs` |
| Music tools you asked Earport to download (yt-dlp, FFmpeg, Deno, fpcalc) | `%APPDATA%\com.earport.app\bin` |
| Your Spotify sign-in (a refresh token) | Windows Credential Manager, under the name "Earport". It is never written to a plain file. |
| The app's interface cache (Microsoft WebView2) | `%LOCALAPPDATA%\com.earport.app` |
| The app itself | `%LOCALAPPDATA%\Earport` |

Logs are never sent anywhere automatically. If you attach them to a bug
report, you choose what to share; check them first for anything you would
rather not share.

## Outside services Earport contacts

Earport connects to these services directly from your computer. Each one
sees your IP address and ordinary technical details of the connection (such
as the time of the request), as happens with any internet request. Each
service handles that information under its own privacy policy. I don't
receive any of it.

### Spotify (optional, only if you connect it)

- **Addresses:** `accounts.spotify.com`, `api.spotify.com`,
  `open.spotify.com` (oEmbed), `i.scdn.co` and other Spotify image servers
  (cover art).
- **What happens:** you sign in on Spotify's own page in your web browser,
  using a Spotify developer app you created yourself. Earport never sees your
  Spotify password.
- **Permissions Earport asks for:**
  - `playlist-read-private` and `playlist-read-collaborative`: read your
    playlists, including private and collaborative ones;
  - `user-library-read`: read your Liked Songs;
  - `playlist-modify-private` and `playlist-modify-public`: create or update
    a playlist in your account, only when you use Export.
- **What Earport reads:** your Spotify user ID and display name, and the
  titles, artists, albums, durations and artwork links of the playlists and
  Liked Songs you choose to import. It never reads or saves Spotify audio.
- **What Spotify receives:** your sign-in, your requests for that data, and
  the names and track lists of playlists you export.
- **To stop:** use **Disconnect** in Earport (Settings → Spotify), which
  removes the saved sign-in from Windows Credential Manager. You can also
  remove Earport's access at <https://www.spotify.com/account/apps/>.

Spotify privacy policy: <https://www.spotify.com/legal/privacy-policy/>

### YouTube (when finding and downloading songs)

- **Addresses:** YouTube and its video servers (through yt-dlp),
  `www.youtube.com/oembed`, `i.ytimg.com` (thumbnails).
- **What YouTube receives:** search terms made from the song's title and
  artist, the links of videos Earport checks or downloads, and playlist links
  you paste in. Earport does not sign in to YouTube or use your browser's
  cookies.

Google privacy policy: <https://policies.google.com/privacy>

### SoundCloud and Deezer (only when you import a link from them)

- **Addresses:** SoundCloud: `soundcloud.com` and `api-v2.soundcloud.com`
  (through yt-dlp), `on.soundcloud.com` (to open a share link), and
  `i1.sndcdn.com` and other SoundCloud image servers (cover art). Deezer:
  `api.deezer.com`, `link.deezer.com` and `deezer.page.link` (to open a share
  link), and `e-cdns-images.dzcdn.net` and other Deezer image servers (cover
  art).
- **What they receive:** the link of the playlist or album you import, and
  the same link again when Earport checks a linked playlist for changes.
  Earport does not sign in to either service, and reads only public
  playlists and albums.
- **What Earport reads:** the playlist's or album's name, and each song's
  title, artist, album, duration, ISRC code (Deezer, when given) and artwork
  link. Songs are found and downloaded from YouTube, as for any other
  import; nothing is downloaded from SoundCloud or Deezer.

SoundCloud privacy policy: <https://soundcloud.com/pages/privacy>
Deezer privacy policy: <https://www.deezer.com/legal/personal-datas>

### MusicBrainz and the Cover Art Archive (when fixing song info)

- **Addresses:** `musicbrainz.org`, `coverartarchive.org` (and the
  `archive.org` servers that host the images).
- **What they receive:** the song title, artist and album being looked up,
  and the IDs of releases whose cover art is fetched. Requests identify
  Earport and its version, with a link to the Earport releases page; they
  contain nothing about you.
- Audio fingerprints made by fpcalc are compared on your computer only and
  are not sent anywhere.

MetaBrainz privacy policy: <https://metabrainz.org/privacy>

### GitHub (music tools and Earport updates)

- **Addresses:** `api.github.com` and `github.com` (and GitHub's download
  servers).
- **Music tools:** when you ask Earport to install yt-dlp, FFmpeg, Deno or
  fpcalc, it asks GitHub for the latest official release of that tool and
  downloads it from there. On the update schedule below, it also asks GitHub
  for the latest yt-dlp version number, to tell you in Settings when a newer
  one is out. It never installs a tool by itself.
- **Updates:** by default, a little after Earport starts and every six hours
  while it stays open, and whenever you click **Check for app updates**, it
  fetches
  `https://github.com/lachiegitholt/EarportApp/releases/latest/download/latest.json`
  (or, if you choose stable versions only,
  `https://github.com/lachiegitholt/EarportApp/releases/download/stable/latest.json`)
  to see if there is a newer version. If there is, it downloads it, and only
  installs it when you choose **Restart to update**.
- **Changing or turning off update checks:** in **Settings → Updates** you
  can choose how often Earport checks (at launch, every six hours, daily or
  weekly), have it ask before downloading, check only when you click **Check
  for app updates**, or turn off the checks for Earport and for music tools
  separately.
- **What GitHub receives:** the file being requested. GitHub may count
  downloads, but I don't receive information that identifies you.

GitHub privacy statement: <https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement>

### Microsoft WebView2

Earport's window uses Microsoft Edge WebView2, part of Windows. If it is
missing, the installer downloads it from Microsoft. WebView2 is covered by
Microsoft's privacy statement and your Windows diagnostic data settings, not
by Earport.

## What Earport does not do

- No analytics, telemetry, usage statistics or crash reporting.
- No advertising and no advertising identifiers.
- No selling or sharing of personal information. I don't hold any to share.
- No Earport account or sign-in.

## Deleting your information

Because everything is on your computer, you control it. To remove all of it:

1. In Earport, go to Settings → Spotify and choose **Disconnect**, if you
   connected Spotify.
2. Uninstall Earport from Windows Settings → Apps. If the uninstaller offers
   to delete the app's data, tick it.
3. Delete your library folder (by default `%USERPROFILE%\Earport`) if you no
   longer want the music, playlists and database in it. Keep anything you want
   to hold on to.
4. Delete `%APPDATA%\com.earport.app` and `%LOCALAPPDATA%\com.earport.app` if
   they are still there.
5. If you didn't disconnect Spotify first, open Windows Credential Manager →
   Windows Credentials and remove the entry named "Earport".
6. Remove Earport's access to your Spotify account at
   <https://www.spotify.com/account/apps/>. You can also delete the Spotify
   developer app you created at <https://developer.spotify.com/dashboard>.

## Children

Earport is not directed at children under 13. I don't knowingly collect
information from anyone, including children.

## Changes to this policy

If this policy changes, the new version will be published at
<https://github.com/lachiegitholt/EarportApp/blob/main/PRIVACY.md> with a new
"Last updated" date. The history of changes is kept in that repository.

## Contact

Questions about this policy: earport.support@gmail.com
