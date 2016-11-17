---
layout: post
title:  "Synology main disk crashed."
date:   2016-11-17 21:27:57 +0100
categories: synology upgrade bad-sectors
---
Just realized that the main (read only) disk in my synology NAS is marked as crashed :-/
Its a Synology 210j NAS bought in 2010 i guess. Initially installed a 1.5TB disk which survived until now. 

Where to go from here? 

1. Buy new disk (maybe two this time for data replication)
2. Install new disk in NAS
2. Move old data to new disk
3. Be happy

1
-
Bought a cheap (~800DKK) Toshiba 3TB replacement disk. Its not labeled NAS but will probably work fine anyways.

2
-
Its was fairly easy to install the disk, since theres room for two disks in the synology. After starting the NAS again I went to storage management and used the wizard to add the new volume as an individual disk.

Formatting and checking the disk took about 8 hours to finish.

3
-
I could not move shares to the new volume using the webinterface since the volume was marked as crashed. So I ended up using ssh to log into the device and copy all the needed data.

```ssh -p 5022 -u root synology-ip```

```cp -r from_folder to_folder```

Should have used screen or nohub to 
