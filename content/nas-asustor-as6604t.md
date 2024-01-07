+++
author = "Sathyajith Bhat"
categories = ["Computing"]
date = 2023-01-21T12:00:00Z
description = "I finally bought a NAS - The Asustor Lockerstor 4 AS6604T 4-Bay NAS. A brief review and my experiences with it."
featured_image = "https://i.sathyabh.at/sb/as6604t-nas/nas_initilizing.jpg"
meta_image = "https://i.sathyabh.at/sb/as6604t-nas/nas_initilizing.jpg"
tags = ["NAS", "homeserver", "linux"]
title = "A brief look at my new NAS - The Asustor AS6604T 4-bay NAS"
type = "post"
url = "/2023/01/21/asustor-lockerstor4-as6604t/"
aliases = [ "/nas" ]

+++

I'd been meaning to buy a NAS unit for some time, but it never materialized. Now that things had settled down a bit, I started doing research on NAS devices. I spent a lot of time reading and watching YouTube videos, particularly comparing Synology and QNAP, and was nearly ready to make a purchase when I came across Jeff Geerling's review of the Asustor Lockerstor 4 AS6604T and found it to be quite good. Given that it was available and Centercomm had a sale going on for it, I decided to purchase it along with two Seagate IronWolf 6TB hard drives.

### Unboxing

The AS6604T came in a fairly standard box. There was nice foam padding on the inside to prevent damage during shipping. The accessories box included an external power brick, cable ties, screws to hold the drives to the caddy, and 2x CAT 5e LAN cables.

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_box.jpg" "NAS Box" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_box_back.jpg" "NAS Box from back" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_accessories_box.jpg" "Accessories Box" "Asustor AS6604T NAS" >}}

Note that this is a 4-bay diskless unit and didn't come with any drives - I ordered two Seagate IronWolf 6TB disks separately (hindsight, ordering two drives together in general is not a good idea as they might be from the same batch, and might fail together). The CAT 5e cables included in the box meant that I didn't have to go hunting for LAN cables, which is a nice addition.

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "ironwolf_harddisk.jpg" "IronWolf Hard Disk" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "harddisk_with_nas.jpg" "IronWolf Hard Disk with the NAS" "Asustor AS6604T NAS" >}}

The NAS unit is quite compact, about the size of my palm!

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "palm_for_reference.jpg" "Palm for reference!" "Asustor AS6604T NAS" >}}

### Hardware Specs

When looking for NAS devices, you'll find plenty that are at a low price, but the catch is that most are powered by ARM processors. These ARM processors are decent, but I didn't want to grab an ARM-based device, especially due to the generally poor availability of software. I didn't want to go hunting for ARM-based packages or Docker images. That said, here's what the AS6604T's hardware specs are:

* Processor: Intel Celeron J4125 64-bit Quad-Core 2.0GHz (burst up 2.70 GHz)
* Memory: 4GB SO-DIMM DDR4 
    * Total Memory Slots 2
    * Memory Expandable up to 8GB (2x 4GB)
* 4 Drive Bays + 2 M.2 Slots
    * Supported drives
        * 3.5" SATA HDD/SSD
        * 2.5" SATA HDD/SSD
        * M.2 2280 NVMe
* Ports:
    * 3x USB 3.2 Gen 1
    * Network 2x 2.5 Gigabit Ethernet
    * HDMI Output 1x HDMI 2.0a

The M.2 slots can only be used for data storage or caching, not for both, so keep that in mind. Apart from these, the AS6604T has a two-line LCD screen on the top part of the front panel that shows the system status and is further customizable to show various information, such as the IP address, temperature, or you can set your own custom text.

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "nas_booting.jpg" "The LCD shows status of the NAS which is handy if you're wondering what's happening" "Asustor AS6604T NAS" >}}

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "nas_initilizing.jpg" "The LCD shows status of the NAS which is handy if you're wondering what's happening" "Asustor AS6604T NAS" >}}

The drive bays are on the bottom half and come with a push-button release and are easy to slide out. Unfortunately, you'll need a screwdriver to tighten the screws on the disk bay, as Asustor hasn't provided thumbscrews that would allow installing the drives without any tools.

### First boot / Out of box experience

The AS6604T comes with its own custom distro called [Asustor Data Master (ADM)](https://www.asustor.com/admv2?type=1&subject=1&sub=101). When you boot up for the first time, you're prompted to initialize the NAS. The initialization process will prepare the hard disk, formatting it with the btrfs file system and configuring your hard disk to RAID levels based on how many drives you've installed. Since I installed only two drives, ADM configured it with RAID 1. The initialization didn't take too long and once you see the IP address on the LCD, you can point your browser to this IP. 

You'll be greeted with an ominous TLS cert warning (and Edge just refused to load the page for me) since it defaults to TLS with a self-signed cert. I actually quite like the Web UI - it mimics most of the phone/tablet OS home screen with shortcuts to most of the commonly used stock apps, settings, and you can customize and add a mini widget that shows essential hardware metrics such as CPU & memory utilization, disk space utilization, RAID array status, as well as some important logs. 

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "adm_web_ui.jpg" "The Asustor ADM Web UI" "Asustor AS6604T NAS" >}}

The default username and password for the AS6604T is admin, and when you log in, you're reminded multiple times to change these, to create a new user, to change the default port used for the Web UI (though I don't see how useful changing the port is - people are likely to just nmap and find open ports) and to disable unwanted services. Asustor devices were hit by a [bad ransomware attack in Feb 2022](https://www.theverge.com/2022/2/22/22945962/asustor-nas-deadbolt-ransomware-attack), and this looks like one way of telling people to mind the security of their devices. The NAS device will also complete synchronizing the RAID array in the background, and for my 6TB volume, it took about 14 hours or so. During this sync process, you can still use your device, and you probably will not notice any difference. If you install too many apps, you'll see a slider on the sides, and clicking on it reveals the next page with a nice, smooth transition. It sounds trivial, but it really does add a nice touch.

Out of the box, besides the settings, the AS6604T comes with the following applications pre-installed:

* Access Control: Lets you create users, join AD/LDAP groups, create shared folders and enable/disable app access to users
* App Central: Asustor's package manager/app store
* Backup & Restore: Asustor's backup app with support for rsync-based sync as well as backup of internal folders/external devices
* Cloud Backup center: Backup your NAS contents right to Cloud providers (S3, Backblaze etc)
* Services: Lets you enable/disable services such as SMB, NFS, WebDAV, Rsync, and even web server & reverse proxies
* File Explorer: As the name suggests, a UI for your files
* Snapshot center: Lets you take snapshots of your volumes
* Dr. ASUSTOR: Simple app that runs some diagnostics of your NAS and provides suggestions on how you can improve security.

### App Central

The App Central is the AS6604T's preferred way of installing apps. The App Central comes with a decent number of apps, including fan favorites like Plex, Jellyfin, Sonarr, Radarr, and Photo Prism. Installing from the App Central is incredibly easy - it's just a single click, and a few seconds later, the app is ready - complete with an icon on the Web UI.

It might have been the fastest and simplest way to install Plex, Tailscale, Photoprism, and many more. For many apps, the App Central install just wraps the Docker image pull and run, while for a few others, they do a native install, i.e., without using Docker. Sadly, the ADM doesn't use deb/rpm/aur or such commonly used packages and seems to use its custom package manager called "APKG" and the packages use .apk extension, but I don't believe they are the same as Alpine's packages. The lack of deb/rpm support means that you cannot add Debian/Ubuntu/other custom repos, update and install, rather, you would have to search for Asustor's versions of it (if it's not there in the App Store).

That said, given how many apps in the App Central require Docker to be pre-installed, I think it makes more sense to skip the packaged apps and use Docker to run your apps. Portainer, a web UI for managing Docker containers, is also available in the App Central, and after installing this, managing apps became much easier. Soon enough, I want to start using Terraform to manage and run the containers so I don't have to keep track of how I installed/ran the containers. An annoying problem I noticed with the Docker way of installing is that ADM puts all the apps in the default bridge network. This breaks [inter-container DNS resolution](https://stackoverflow.com/q/41400603/92837) and will no doubt cause a lot of problems for many people.

### EZ-Connect

Another service worth mentioning is EZ-Connect (or EZConnect, depending on where you look at the settings). EZConnect is two things: a Dynamic DNS service, as well as some sort of cloud-relay-passthrough service that lets you connect to your NAS even if you can't get a static IP. The downside is that most of the third-party apps aren't usable via this relay service. The security implications are that you connect via EZConnect using a Cloud ID that might be easily guessable, and if you have a weak admin password (which you really shouldn't), then you're opening your NAS up for easy unauthorized access. 

I tried it for a day before feeling uneasy about it and shut down all access to the NAS via the public Internet, making it accessible only via Tailscale.

### Annoyances 

The AS6604T is a pretty nice device, and especially if you're happy with the software the App Central offers, it's one of the devices that you can set up and not worry about it. If you bought the device with plans of using more than just a NAS (think more like a mini home server), I think you'll have to temper your expectations, especially on the stock hardware configuration. 

The 4GB RAM is not quite sufficient, and you'll have to upgrade the RAM (and I have seen on Reddit people upgrading to 16GB - even though that is not officially supported). Over the past few months that I have been using it, I've run into some annoying things that I wish could have been fixed if not for the OS:

* The ADM OS is a slimmed-down OS with busybox as the shell. It severely limits what you can do with the terminal.
* `TERM` variable is set incorrectly, so terminal apps like htop crash with an `Error opening terminal: xterm-256color.` error unless you override it.
* `sudo` requiring a password: after getting used to cloud servers with `NOPASSWD` set for `sudo`, this is infuriating. Setting `sudoers` doesn't work because it gets reset on boot.
* I've often seen Docker and the docker proxy completely stop working. Like a hard stop - `docker ps` doesn't respond at all, none of the apps running in containers accept incoming requests, etc. Trying to stop the Docker service doesn't work either as it hangs up waiting for response from the Docker daemon. The only way to 'fix' it is to force a reboot. 

### What am I running on it?

The first thing that I setup was [Plex Media Server](https://www.plex.tv/) - and that's been running pretty well. Besides Plex, I've also set up the below services - most of them running as containers

* [Portainer](https://www.portainer.io/) for container management
* [Netdata](https://github.com/netdata/netdata) for monitoring
* [Tailscale](https://tailscale.com/) for access to the device from outside of my home network
* [Jackett](https://github.com/Jackett/Jackett), [Sonarr](https://sonarr.tv/), [Radarr](https://radarr.video/) and [qBitTorrent](https://www.qbittorrent.org/) - to acquire media
* [AdGuard Home](https://adguard.com/en/adguard-home/overview.html) for blocking ads and trackers at a network level. 
* [RIPE Atlas Probe](https://atlas.ripe.net/about/) to measure the external network connectivity 

With all of these running, the NAS runs quietly at low CPU and memory utilization levels. I experimented with Photo Prism for managing photos, but Photo Prism ended up consuming most of the CPU and memory and would definitely need a RAM upgrade before running it full-time. Besides these, I also have [restic](https://restic.net/) running backups of my photos and documents to S3 at regular intervals.

### Cost of purchases:

* Asustor Lockerstor AS6604T - 749 AUD
* Seagate IronWolf 6TB 3.5" NAS Hard Drive - 239 AUD

### Summary

Overall, I am quite happy with the Asustor AS6604T NAS and would recommend it to anyone looking for a decent 4-bay NAS, assuming you will use it as a NAS and not as a full-blown home server. With a RAM upgrade, the AS6604T can act as a mini home server as well, but the problems I have seen with the ADM OS make me question if it's worth going that route. There are posts on [Reddit on How to install](https://www.reddit.com/r/asustor/comments/t3kh1t/newb_installing_ubuntu_linux_on_asustor_as5304t/) Ubuntu or other Linux distros on the NAS, but it will require a significant time investment. Also, there are plenty of reports of losing fan control if an alternate OS is installed. If you're just looking for backups and a couple of side containers, the AS6604T will do just fine. If you have any questions, please leave a comment or [send me toot on @SathyaBhat@Mastodon](https://mastodon.social/@Sathyabhat), I'll be happy to answer.
