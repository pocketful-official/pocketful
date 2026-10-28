# Is Pocketful safe?

You shouldn't have to take anyone's word for it. Here is what Pocketful does, and how to
check your download yourself.

## What it talks to

No accounts, no tracking, no ads, no analytics. Pocketful talks only to:

- the music services you use it with (Deezer, MusicBrainz and the others listed in the
  [third-party notices](THIRD-PARTY-NOTICES.md)), to find and play music;
- this project's releases page, once a day if you leave it on, to see if there's a new
  version;
- this project's `status.json`, about once an hour (see "The project's switch" below).

The last two are plain requests to GitHub with nothing that identifies you or your device;
the project never sees who you are.

## Your download is the one that was published

Each release lists the SHA-256 fingerprint of every file in `SHA256SUMS.txt`. On Windows,
in PowerShell:

    Get-FileHash .\Pocketful-<version>-win64.zip

The result must match the line in `SHA256SUMS.txt`. Check the Android .apk the same way on
a computer.

## Updates must be signed by the project

Each release's `SHA256SUMS.txt` is signed (`SHA256SUMS.txt.sig`) with the project's Ed25519
key. That key is kept offline and never goes online. The apps carry only its public half:

    b9daab648cf354a7838b8e92d575fc871c949cfa9fa5e5f2c6f9d6cb20b993b9

Before installing an update, the apps check that signature and the file's fingerprint, and
refuse anything that doesn't match. So even someone who took over the project's GitHub
account could not push an update to you.

On Android, the app is signed with the project's own certificate
(`CN=The Pocketful Project`, SHA-256
`25:76:F1:07:0A:8B:B4:DB:48:D1:DC:8B:F5:E4:2C:E3:7F:CD:3F:FB:57:DE:EC:27:6B:D8:70:35:26:07:07:AB`),
and Android itself refuses any update signed with another.

## Scan it yourself

Upload the file to [VirusTotal](https://www.virustotal.com/gui/home/upload), which checks it
with about 70 antivirus engines, or search there for its SHA-256.

One or two little-known engines may flag the Windows app. That happens to many small free
apps that aren't signed with a paid certificate, because some engines are wary of any
program they rarely see. The well-known engines (Microsoft Defender, Kaspersky, ESET,
Bitdefender) are the ones to look at.

## The project's switch

The project can show you a message, pause downloads, or switch Pocketful off, for example
if a version turns out to have a security problem or if the project ends. It does this with
`status.json`, signed with the same offline key, so nobody else can use it.

A second project key can sign `status.json` too, so the switch can be used quickly, but it can
only do the mildest part: show a notice, pause downloads, switch Pocketful off for a while and
switch it back on. It can't sign an update, retire a version, close the project for good or
change the project's address; only the offline key can.

- It can show a notice, pause downloading and streaming, or show a "switched off" screen;
  it can also retire a version older than a given one.
- If the project ever has to end, it can say so for good ("closed"): Pocketful then shows a
  goodbye message and does nothing else, and from then on asks nothing of the internet.
- It can **never** delete, change or upload anything: your music, playlists and settings
  stay on your device, and the songs are ordinary files that play in any app.
- Without internet, Pocketful keeps working as it did the last time it checked.

## Why Windows says "Windows protected your PC"

Microsoft SmartScreen warns about apps that aren't signed with a paid certificate.
Certificates cost money every year and are tied to a real person's identity, and Pocketful
is free and made anonymously. Click **More info**, then **Run anyway**.

## Reporting a security problem

Use Feedback in the app's Settings, or write to the address on the project's
[contact page](https://pocketful-official.github.io/pocketful/contact/). Please say it's
about security, and give the project time to fix it before telling anyone else.
