---
title: Meminfo
date: 2020-07-16 14:41:06
tags:
---

在linux中常常會發現記憶體越來越少，為了確保程式能長時間執行，所以試著觀察記憶體使用狀況。

可用的資源目前認定是free + buffers + cached

## free / top

### free

``` free
$ free

             total       used       free     shared    buffers     cached
Mem:      16114340   15729504     384836          0    3281776    7756836
-/+ buffers/cache:    4690892   11423448
Swap:      8191996    5433184    2758812

```

### top

``` top
$ top
top - 14:46:06 up 297 days,  6:08, 16 users,  load average: 0.58, 0.42, 0.34
KiB Mem:  16114340 total, 15822976 used,   291364 free,  3271424 buffers
KiB Swap:  8191996 total,  5433184 used,  2758812 free,  7887408 cached

      PR  NI    VIRT    RES    SHR S  %CPU  %MEM   
      20   0    4304    268    244 S 0.000 0.002 
      20   0       0      0      0 S 0.000 0.000 
      20   0 3747804 815480   8052 S 0.000 5.061  
      20   0       0      0      0 S 0.000 0.000  
      rt   0       0      0      0 S 0.000 0.000  
      20   0   19116    540    428 S 0.000 0.003  

```

### meminfo

在有些嵌入式系統 free / top 看不到cached，可以從meminfo去找到。

``` meminfo
cd /proc/meminfo
```
