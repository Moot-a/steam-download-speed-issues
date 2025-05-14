# Steam Download Troubleshooting

## `steam_dev.cfg`
Create a file named steam_dev.cfg in your steam install directory :  

|            OS            | File Path                                                        |
| :----------------------: | ---------------------------------------------------------------- |
|         Windows:         | `C:\Program Files (x86)\Steam\steam_dev.cfg)`                    |
| Linux (Native install):  | `~/.steam/steam/steam_dev.cfg`                                   |
| Linux (Flatpak Install): | `~/.var/app/com.valvesoftware.Steam/.steam/steam/steam_dev.cfg`  |

Windows : `steam_dev.cfg`
```cfg
@nClientDownloadEnableHTTP2PlatformWindows 0
@fDownloadRateImprovementToAddAnotherConnection 1.1
@cMaxInitialDownloadSources 15
```

Linux : `steam_dev.cfg`
```cfg
@nClientDownloadEnableHTTP2PlatformLinux 0
@fDownloadRateImprovementToAddAnotherConnection 1.1
@cMaxInitialDownloadSources 15
```

*MacOS (not sure)* : `steam_dev.cfg`
```cfg
@fDownloadRateImprovementToAddAnotherConnection 1.1
@cMaxInitialDownloadSources 15
```

HTTP2 Disabling  
Windows: `@nClientDownloadEnableHTTP2PlatformWindows 0`  
Linux: `@nClientDownloadEnableHTTP2PlatformLinux 0`  
MacOS: No toggle available.  
HTTP2 can cause slowdowns (e.g., on Windows, speed went from 10-20MB/s to 60MB/s after disabling).

More Connections  
Use `@fDownloadRateImprovementToAddAnotherConnection 1.1`  
This increases the number of servers Steam connects to, improving speeds in some cases (up to 10 servers).

More Initial Servers  
Use `@cMaxInitialDownloadSources 15`  
Some users report speed boosts by adding more initial servers.

## DNS

Changing DNS settings could be helpful too :

| DNS Provider |          DNS           |
| :----------: | :--------------------: |
|  Cloudflare  | `1.1.1.1` \| `1.0.0.1` |
|    Google    | `8.8.8.8` \| `8.8.4.4` |

---
Sources :  
https://www.reddit.com/r/linux_gaming/comments/16e1l4h/slow_steam_downloads_try_this/  
https://wiki.archlinux.org/title/Steam/Troubleshooting  
https://gist.github.com/FikriRNurhidayat/ce18426ad94fff2140538c0adf0e06ec?permalink_comment_id=4806133#gistcomment-4806133  
