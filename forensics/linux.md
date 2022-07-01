# Linux







#### Mounting E01 on Linux

1. sudo ewfmount {image} {mount directory}
2. sudo mmls {mount directory}/ewf1
3. Look for the sector that have the largest length that not an meta slot.
4. calculate the byte offset, take the sector start offset that was found in the previous step and multiple it with the unit byte sector e.g. {start \* 512}
5. sudo mount -o ro,loop,offset={offset in byte {mount directory} {logical mount directory} norecovery parementer might be need to mount
6. sudo chroot {logical mount directory} - will change the machine root directory to the new logical drive, will act is if you log into the machine
7. exit - can be used to logout of the system again
8. umount - unmount the directory from the system
