# HIDProbe Sileo Repo

Nguon Sileo/Zebra de cai `HIDProbe Agent` tren iPhone da jailbreak.

## Add Source

Neu host bang GitHub Pages, them source nay trong Sileo:

```text
https://nguyenthao158258-web.github.io/HIDProbe-Sileo-Repo/
```

Neu dung custom domain rieng, tro domain ve GitHub Pages roi them URL goc, vi du:

```text
https://repo.example.com/
```

## Package

```text
Package: com.hidprobe.agent
Name: HIDProbe Agent
Version: 2.4.0
Port: 17391
```

Goi nay chi cai daemon nen:

```text
/usr/local/bin/HIDProbeAgent
/Library/LaunchDaemons/com.hidprobe.agent.plist
```

Khong tao icon app moi. App HID TrollStore van la app UI/status/config rieng.

## Files

```text
Packages
Packages.gz
Release
debs/hidprobe-agent_2.4.0_rootful_iphoneos-arm64.deb
debs/hidprobe-agent_2.4.0_rootful_iphoneos-arm64e.deb
```

## Verify

Sau khi cai tren iPhone:

```sh
dpkg -s com.hidprobe.agent
launchctl print system/com.hidprobe.agent
curl http://127.0.0.1:17391/health
```

Health OK se tra `agent_listening`.

## Update Repo

Moi lan co `.deb` moi:

```sh
bash installer/build_sileo_repo.sh dist/sileo-repo dist/hidprobe-agent_*.deb
```

Sau do copy noi dung `dist/sileo-repo/` vao repo publish nay, commit va push.
