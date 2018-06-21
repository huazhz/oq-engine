Classical Hazard QA Test, Case 3
================================

============== ===================
checksum32     4,051,148,706      
date           2018-06-05T06:38:54
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 1, num_levels = 3

Parameters
----------
=============================== ==================
calculation_mode                'classical'       
number_of_logic_tree_samples    0                 
maximum_distance                {'default': 200.0}
investigation_time              1.0               
ses_per_logic_tree_path         1                 
truncation_level                0.0               
rupture_mesh_spacing            1.0               
complex_fault_mesh_spacing      1.0               
width_of_mfd_bin                1.0               
area_source_discretization      0.05              
ground_motion_correlation_model None              
minimum_intensity               {}                
random_seed                     1066              
master_seed                     0                 
ses_seed                        42                
=============================== ==================

Input files
-----------
======================= ============================================================
Name                    File                                                        
======================= ============================================================
gsim_logic_tree         `gsim_logic_tree.xml <gsim_logic_tree.xml>`_                
job_ini                 `job.ini <job.ini>`_                                        
source                  `source_model.xml <source_model.xml>`_                      
source_model_logic_tree `source_model_logic_tree.xml <source_model_logic_tree.xml>`_
======================= ============================================================

Composite source model
----------------------
========= ======= =============== ================
smlt_path weight  gsim_logic_tree num_realizations
========= ======= =============== ================
b1        1.00000 trivial(1)      1/1             
========= ======= =============== ================

Required parameters per tectonic region type
--------------------------------------------
====== ================ ========= ========== ==========
grp_id gsims            distances siteparams ruptparams
====== ================ ========= ========== ==========
0      SadighEtAl1997() rrup      vs30       mag rake  
====== ================ ========= ========== ==========

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=1, rlzs=1)
  0,SadighEtAl1997(): [0]>

Number of ruptures per tectonic region type
-------------------------------------------
================ ====== ==================== ============ ============
source_model     grp_id trt                  eff_ruptures tot_ruptures
================ ====== ==================== ============ ============
source_model.xml 0      Active Shallow Crust 31,353       31,353      
================ ====== ==================== ============ ============

Slowest sources
---------------
========= ============ ============ ========= ========== ========= ========= ======
source_id source_class num_ruptures calc_time split_time num_sites num_split events
========= ============ ============ ========= ========== ========= ========= ======
1         AreaSource   31,353       0.52101   5.26674    1.00000   31,353    0     
========= ============ ============ ========= ========== ========= ========= ======

Computation times by source typology
------------------------------------
============ ========= ======
source_class calc_time counts
============ ========= ======
AreaSource   0.52101   1     
============ ========= ======

Duplicated sources
------------------
There are no duplicated sources

Information about the tasks
---------------------------
================== ======= ======= ======= ======= =========
operation-duration mean    stddev  min     max     num_tasks
RtreeFilter        0.10301 0.02682 0.04592 0.17204 60       
count_eff_ruptures 0.06985 0.02454 0.02222 0.11768 32       
================== ======= ======= ======= ======= =========

Fastest task
------------
taskno=32, weight=35, duration=0 s, sources="1"

======== ======= ========= ======= ======= ===
variable mean    stddev    min     max     n  
======== ======= ========= ======= ======= ===
nsites   1.00000 0.0       1       1       353
weight   0.10000 7.461E-09 0.10000 0.10000 353
======== ======= ========= ======= ======= ===

Slowest task
------------
taskno=16, weight=100, duration=0 s, sources="1"

======== ======= ========= ======= ======= ====
variable mean    stddev    min     max     n   
======== ======= ========= ======= ======= ====
nsites   1.00000 0.0       1       1       1000
weight   0.10000 1.491E-08 0.10000 0.10000 1000
======== ======= ========= ======= ======= ====

Data transfer
-------------
================== =============================================================================== ========
task               sent                                                                            received
RtreeFilter        srcs=5.46 MB monitor=20.33 KB srcfilter=16.35 KB                                6.75 MB 
count_eff_ruptures sources=7.22 MB param=13.47 KB monitor=11.03 KB srcfilter=7.28 KB gsims=3.75 KB 11.22 KB
================== =============================================================================== ========

Slowest operations
------------------
============================== ========= ========= ======
operation                      time_sec  memory_mb counts
============================== ========= ========= ======
PSHACalculator.run             13        63        1     
total prefilter                6.18062   3.46875   60    
splitting sources              5.28254   8.90625   1     
reading composite source model 5.23572   0.04297   1     
total count_eff_ruptures       2.23536   6.51172   32    
managing sources               2.15995   52        1     
unpickling prefilter           0.51268   1.03516   60    
aggregate curves               0.02641   0.0       32    
unpickling count_eff_ruptures  0.00890   0.0       32    
store source_info              0.00427   0.0       1     
reading site collection        9.689E-04 0.0       1     
saving probability maps        1.855E-04 0.0       1     
============================== ========= ========= ======