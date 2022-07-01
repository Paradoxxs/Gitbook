# Disk

## Physicals drive

* Data lives everywhere
* there are areas on the hard drive that are not visible to you and your tools
* Account for the entire hard drive space
* Have an understanding of the file systems and the evidence format.

### HHD

Platter layout ![](https://remnote-user-data.s3.amazonaws.com/b4FkvNkiJMELNfQ-JomvFt7kRrDcaKST3tQYFaBd\_peXrwsfb\_TbIRNN8bDHuSd7VaOIlwoY8daNdDkzzvmLmnHPnWkNseUv9A7DOBBINsm1XgjGBUwuhdAVR\_AZ5KHG.png)

#### Cluster and slack

* All cluster have a minimum size of 4 KB
* Allocated space
  * cluster allowed to data of a file.
* slack space
  * If a file data is written to a cluster with a size less than cluster space, the remaining unused space is called slack space.
* Delete space
  * Cluster mark as deleted.
* Wiping
  * Because of the density of new drev you only need to wipe once for the data not be recoverable.

#### Common hardware problems

* Stuck head
  * Short buzz or series of buzzes, followed by nothing
* SMART exceeded (Self monitoring analysis reporting technology)
* Blow TVS (Transiet voltage suppression)
  * Remove TVS
* Corrupt ROM
  * Flashing the ROM
* Dead heads
  * Replace head stack
* Seized motor
* Degraded platter surface

### SSD

#### Terms

* Cell - 1 or more bits
* Page - 2 to 8 KB
* Block - 256 KB
* Layer - stacks of cells
* Write - Data is written in 4KiB pages
* Deleted - Data erased in 256 blocks (64 writable pages)

#### Firmware controls

Garbage collection happens at the firmware level on the SSD.

Trimming clear data stored in flash that is deleted, allow for clearing free space.

Wear leveling, A cell can only be written x amount of times before the cell fails, which mean the firmware will try to even out the wear level, by moving data around in pages.

Because SSD have unalloced space that is unsed in case of backup there currently no way to 100% sure that all data have been wiped, there for the best solution is total destruction.

#### Failure

Hardware failure

* Smell of burn component
* Burn marks
* Loud of place noises

Common problem

* Corrupt controller
* Bit rod - Prolong period of no power, can cause some of the bits to flip resulting in data loss.
