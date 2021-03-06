===================================================================
ganesha-cache-config -- NFS Ganesha Cache Configuration File
===================================================================

.. program:: ganesha-cache-config


SYNOPSIS
==========================================================

| /etc/ganesha/ganesha.conf

DESCRIPTION
==========================================================

NFS-Ganesha reads the configuration data from:
| /etc/ganesha/ganesha.conf

This file lists NFS-Ganesha Cache config options.

CACHEINODE {}
--------------------------------------------------------------------------------

NParts (uint32, range 1 to 32633, default 7)
    Partitions in the Cache_Inode tree.

Cache_Size(uint32, range 1 to UINT32_MAX, default 32633)
    Per-partition hash table size.

Use_Getattr_Directory_Invalidation(bool, default false)
    Use getattr for directory invalidation.

Dir_Max_Deleted(uint32, range 1 to UINT32_MAX, default 65536)
    Max size of per-directory cache of removed entries

Dir_Max(uint32, range 1 to UINT32_MAX, default 65536)
    Max size of per-directory dirent cache

Dir_Chunk(uint32, range 0 to UINT32_MAX, default 128)
    Size of per-directory dirent cache chunks, 0 means directory chunking is not
    enabled.

Entries_HWMark(uint32, range 1 to UINT32_MAX, default 100000)
    High water mark for cache entries.

LRU_Run_Interval(uint32, range 1 to 24 * 3600, default 90)
    Base interval in seconds between runs of the LRU cleaner thread.

Cache_FDs(bool, default true)
    Whether to cache open files

FD_Limit_Percent(uint32, range 0 to 100, default 99)
    The percentage of the system-imposed maximum of file descriptors at which
    Ganesha will deny requests.

FD_HWMark_Percent(uint32, range 0 to 100, default 90)
    The percentage of the system-imposed maximum of file descriptors above which
    Ganesha will make greater efforts at reaping.

FD_LWMark_Percent(uint32, range 0 to 100, default 50)
    The percentage of the system-imposed maximum of file descriptors below which
    Ganesha will not reap file descriptonot reap file descriptors.

Reaper_Work(uint32, range 1 to 2000, default 1000)
    Roughly, the amount of work to do on each pass through the thread under
    normal conditions.  (Ideally, a multiple of the number of lanes.)

Biggest_Window(uint32, range 1 to 100, default 40)
    The largest window (as a percentage of the system-imposed limit on FDs) of
    work that we will do in extremis.

Required_Progress(uint32, range 1 to 50, default 5)
    Percentage of progress toward the high water mark required in in a pass
    through the thread when in extremis

Futility_Count(uint32, range 1 to 50, default 8)
    Number of failures to approach the high watermark before we disable caching,
    when in extremis.

Retry_Readdir(bool, default false)
    Behavior for when readdir fails for some reason:
    * true will ask the client to retry later,
    * false will give the

See also
==============================
:doc:`ganesha-config <ganesha-config>`\(8)
