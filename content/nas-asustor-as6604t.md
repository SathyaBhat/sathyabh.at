+++
author = "Sathyajith Bhat"
categories = ["Computing"]
date = 2023-01-19T12:00:00Z
description = "After much delay, I finally bought a NAS - The Asustor Lockerstor 4 AS6604T 4-Bay NAS. A brief review and my experiences with it."
# featured_image = ""
# meta_image = "" 
tags = ["NAS", "homeserver"]
title = "A brief look at my new NAS - The Asustor 6604T"
type = "post"
url = "/2023/01/19/asustor-lockerstor4-as6604t/"

+++

I'd been meaning to buy a NAS unit since quite some time, but it never masterialized. Now that things had settled down a bit, I started doing some research about NAS devices. I spent a lot of time reading, watching YouTube videos) - especially a lot Synology vs QNAP ones and nearly was ready to purchase it when I came across [Jeff Geerling's review of the Asustor Lockerstor 4 AS6604T](https://www.youtube.com/watch?v=vBccak8f-VY) and found it quite good. Given that it was available and Centercomm had a sale going on for it, I purchased it along with two Seagate IronWolf 6TB hard drives.

### Unboxing

The AS6604T came in a fairly standard box. There was a nice foam padding on inside to prevent some damage during shipping. There was a separate accessories box that came with an external power brick, cable ties, screws to hold the drives to the caddy and 2x CAT 5e LAN cables. 

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_box.jpg" "NAS Box" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_box_back.jpg" "NAS Box from back" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "as6604t_accessories_box.jpg" "Accessories Box" "Asustor AS6604T NAS" >}}

Note that this is a 4-bay diskless unit and didn't come with any drives - I ordered two Seagate IronWolf 6TB disks separately (hindsight, ordering two drives together in general is not a good idea as they might be of the same batch and might fail together). The CAT 5e cables with the box meant that I didn't have to go hunting for LAN cables and is a nice addition.

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "ironwolf_harddisk.jpg" "IronWolf Hard Disk" "Asustor AS6604T NAS" >}}
{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "harddisk_with_nas.jpg" "IronWolf Hard Disk with the NAS" "Asustor AS6604T NAS" >}}

The NAS unit is quite compact and about the size of my palm!

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "palm_for_reference.jpg" "Palm for reference!" "Asustor AS6604T NAS" >}}

### Hardware Specs

While looking for NAS devices, you'll find plenty that are at a low price - the catch being that most are powered by ARM processors. These ARM processors are decent-ish but I didn't want to grab ARM-based devices, especially due to generally poor availability of software and I simply didn't want to go hunting for ARM based packages or Docker images. That said, here's what the AS6604T's hardware specs are:

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
    * Network 2x 2.5 Gigabit Ethernet (2.5G/1G/100M)
    * HDMI Output 1x HDMI 2.0a

The M.2 slots can only be used data storage or for caching - not for both, keep that in mind. Apart from these, the AS6604T has a two-line LCD screen on the top part of the front panel that shows the system status and is further customizable to show various information, such as the IP address, temperature, or you can set your own custom text. 

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "nas_booting.jpg" "The LCD shows status of the NAS which is handy if you're wondering what's happening" "Asustor AS6604T NAS" >}}

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "nas_initilizing.jpg" "The LCD shows status of the NAS which is handy if you're wondering what's happening" "Asustor AS6604T NAS" >}}


The drive bays are on the bottom half and come with a push-button release and are easy to slide out. Sadly you'll need a screwdriver to tighten the screws on the disk bay, as Asustor hasn't provided thumbscrews that would have allowed to install the drives without any tools.

### First boot / Out of box experience

The AS6604T comes with it's own custom distro called [Asustor Data Master (ADM)](https://www.asustor.com/admv2?type=1&subject=1&sub=101). When you boot up the first time you're prompted if you'd like to initialize the NAS. The initialize process will prepare the hard disk, formatting it  with btrfs filesystem and configuring your hard disk to RAID levels based on how many drives you've installed. Since I installed only two drives, ADM configured it with RAID 1. The initialization didn't take too long and once you see the IP address on the LCD, you can point to this IP on a browser. 

You'll be greeted with an ominous TLS cert warning (and Edge just refused to load the page for me) since it defaults to TLS with a self-signed cert. I actually quite like the Web UI - it mimicks most of the phone / table OS home screen with shortcuts to most of the commonly used stock apps, settings and you can customize and add a mini widget that shows essential hardware metrics such as CPU & Memory utilization, disk space utilization, RAID array status as well as some important logs. 

The default username and password for AS6604T is admin and when you login, you're reminded multiple times to change these, to create a new user, to change the default port used for the Web UI (though I don't see how useful changing port is - people are likely to just nmap and find out open ports) and to disable unwanted services. Asustor devices were hit by a [bad ransomware attack in Feb 2022](https://www.theverge.com/2022/2/22/22945962/asustor-nas-deadbolt-ransomware-attack) and this looks like one way of telling people not to mind the security of their devices. The NAS device will also complete synchronizing the RAID array in the background and for my 6TB volume, it took about 14 hours or so. During this sync process, you can still use your device and you probably will not notice any difference. If you install too many apps, you'll see a slider on sides and clicking on reveals the next page which a nice, smooth transition. It sounds trivial but it really does add a nice touch. 

Out of the box, besides settings the AS6604T comes with following applications pre-installed:

* Access Control: Lets you create users, join AD/LDAP groups, create shared folders and enable/disable app access to users
* App Central: Asustor's package manager / app store.
* Backup & Restore: Asustor's backup app with support for rsync-based sync as well as backup of internal folders/external devices
* Cloud Backup center: Backup your NAS contents right to Cloud providers (S3, Backblaze etc)
* Services: Lets you enable/disable services such as SMB, NFS, Web DAV, Rsync and even web server & reverse proxies.
* File Explorer: As the name says, a UI for your files
* Snapshot center: Lets you take snapshots of your volumes3
* Dr. ASUSTOR: Simple app that runs some diagnostics of your NAS and provides suggestions 

### App Central

The App Central is the AS6604T's preferred way of installing apps. The App Central comes with a decent number of apps - including fan favorites like Plex, Jellyfin, Sonarr, Radarr, Photo Prism etc. Installing from the App Central is incredibly easy - it's just a single click and few seconds later, the app is ready - complete with an icon on Web UI. 

{{< fancybox "https://i.sathyabh.at/sb/as6604t-nas" "adm_web_ui.jpg" "The Asustor ADM Web UI" "Asustor AS6604T NAS" >}}


It just might have been the fastest and simplest way I was able to install Plex, Tailscale, Photoprism, and manyu more. For many apps, the App centre install just wraps Docker image pull and run, while for few others, they do a native install, ie without using Docker. Sadly the ADM doesn't use deb/rpm/aur or such commonly used packages and seems to use it's custom package manager call "APKG" and the packages use `.apk` extension - but I don't believe they are the same as Alpine's packages. The lack of deb/rpm support means that you cannot add Debian/Ubuntu/other custom repos, update and install, rather would have to search for Asustor's versions of it (if it's not there in the App Store).

That said, given how many apps in the App Central require Docker to pre-installed, I think it makes more sense to skip the packaged apps and use Docker to run your apps. Portainer, a web UI for managing Docker containers is also available in the App Central and after installing this, managing apps became much easier. Soon enough, I want to start using Terraform to manage and run the containers so I don't have to keep track of how I installed/ran the containers. An annoying problem I noticed with the Docker way of installing is that ADM puts all the apps in the default bridge network. This breaks [inter-container DNS resolution](https://stackoverflow.com/q/41400603/92837) and will no doubt will cause a lot of problem to many people.

### EZ-Connect

Another service worth mentioning is EZ-Connect (or EZConnect, depending on where you look at the settings). EZConnect is two things: a Dynamic DNS service as well as some sort of cloud-relay-passthrough service that lets you connect to you NAS even if you can't get a static IP. The downside is that most of the third party apps aren't usable via this relay service. The security implications: You connect via EZConnect using a Cloud ID that might be easily guessable and if you have a weak admin password (you really shouldn't) then you're opening your NAS up for easy unauthorized access. I tried it for a day before feeling uneasy about it and shut down all access to the NAS via the public Internet, making it accessible only via Tailscale.

### Annoyances 

The AS6604T is a pretty nice device, and especially if you're happy with the software the App Central offers, it's one of the devices that you can setup and not worry about it. If you bought the device with plans of using more than just a NAS (think more like a mini homeserver), I think you'll have to temper your expectations, especially on the stock hardware configuration. The 4GB RAM is not quite sufficient and you'll have toi upgrade the RAM (and I have seen on reddit people upgrading to 16GB - even though that is not officially supported). Over the past few months that I have been using it, I've run into some annoying things that I wish could have been fixed if not for the OS:

* The ADM OS is a slimmed down OS with busybox as the shell. Severely limits what you can do with the terminal.
* TERM variable is set incorrectly, so terminal apps like `htop` crash with an `Error opening terminal: xterm-256color.` error unless you override it
* `sudo` requiring password: after getting used to cloud servers with NOPASSWD set for sudo, this is infuriating. Setting sudoers doesn't work because it gets reset on boot.
* I've often seen Docker and docker proxy completely stop working. Like hard stop - `docker ps` doesn't response at all, none of the apps running in containers accept incoming requests etc. Trying to stop the docker service doesn't work either as it just hangs up. The only way to 'fix' it is to force a reboot. 

### What am I running on it?

The first thing that I setup was [Plex Media Server](https://www.plex.tv/) - and that's been running pretty well. Besides Plex, I've also set up the below services - most of them running as containers

* [Portainer](https://www.portainer.io/) for container management
* [Netdata](https://github.com/netdata/netdata) for monitoring
* [Tailscale](https://tailscale.com/) for access to the device from outside of my home network
* [Jackett]https://github.com/Jackett/Jackett), [Sonarr](https://sonarr.tv/), [Radarr](https://radarr.video/) and [qBitTorrent](https://www.qbittorrent.org/) - to acquire media
* [AdGuard Home](https://adguard.com/en/adguard-home/overview.html) for blocking ads and trackers at a network level. 
* [RIPE Atlas Probe](https://atlas.ripe.net/about/) to measure the external network connectivity 

With all of these running, the NAS runs quiet at low CPU and memory utilization levels. I experimented with Photo Prism for managing photos but Photo Prism would end up consuming most of the CPU and memory and would definitely need a RAM upgrade before letting it run full time. Besides these, I also have [restic](https://restic.net/) running backups of my photos and documents to S3 at regular intervals. 

### Summary

Overall, I'm quite happy with the Asustor AS6604T NAS and would recommend it for anyone looking for a decent 4-bay NASm, assuming you'll use it as a NAS and not as a full-blown homeserver. With a RAM upgrade, the AS6604T can act as a mini homeserver as well, but the problems that I have seen with the ADM OS makes me question if it's worth going that. There are posts on [Reddit on How to install](https://www.reddit.com/r/asustor/comments/t3kh1t/newb_installing_ubuntu_linux_on_asustor_as5304t/) Ubuntu/other Linux distros on the NAS but will require a siginificant time involvement. Also there are plenty of reports of losing fan control if install an alternate OS. If you're just looking at backups and couple of side containers, the AS6604T will do just well. Have any questions? Leave a comment or [send me toot on @SathyaBhat@Mastodon](https://mastodon.social/@Sathyabhat), I'll be happy to answer.




 