Classical PSHA — Area Source
============================

============== ===================
checksum32     3,283,112,543      
date           2018-06-05T06:39:11
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 1, num_levels = 19

Parameters
----------
=============================== ==================
calculation_mode                'classical'       
number_of_logic_tree_samples    0                 
maximum_distance                {'default': 200.0}
investigation_time              50.0              
ses_per_logic_tree_path         1                 
truncation_level                3.0               
rupture_mesh_spacing            2.0               
complex_fault_mesh_spacing      2.0               
width_of_mfd_bin                0.2               
area_source_discretization      5.0               
ground_motion_correlation_model None              
minimum_intensity               {}                
random_seed                     23                
master_seed                     0                 
ses_seed                        42                
=============================== ==================

Input files
-----------
======================= ============================================================
Name                    File                                                        
======================= ============================================================
gsim_logic_tree         `gmpe_logic_tree.xml <gmpe_logic_tree.xml>`_                
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
====== =================== ========= ========== ==========
grp_id gsims               distances siteparams ruptparams
====== =================== ========= ========== ==========
0      BooreAtkinson2008() rjb       vs30       mag rake  
====== =================== ========= ========== ==========

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=1, rlzs=1)
  0,BooreAtkinson2008(): [0]>

Number of ruptures per tectonic region type
-------------------------------------------
================ ====== ==================== ============ ============
source_model     grp_id trt                  eff_ruptures tot_ruptures
================ ====== ==================== ============ ============
source_model.xml 0      Active Shallow Crust 11,132       11,132      
================ ====== ==================== ============ ============

Slowest sources
---------------
========= ============ ============ ========= ========== ========= ========= ======
source_id source_class num_ruptures calc_time split_time num_sites num_split events
========= ============ ============ ========= ========== ========= ========= ======
1         AreaSource   11,132       0.02237   0.06416    1.00000   484       0     
========= ============ ============ ========= ========== ========= ========= ======

Computation times by source typology
------------------------------------
============ ========= ======
source_class calc_time counts
============ ========= ======
AreaSource   0.02237   1     
============ ========= ======

Duplicated sources
------------------
There are no duplicated sources

Information about the tasks
---------------------------
================== ======= ========= ======= ======= =========
operation-duration mean    stddev    min     max     num_tasks
RtreeFilter        0.00713 0.00395   0.00338 0.02592 54       
count_eff_ruptures 0.01118 8.221E-04 0.01029 0.01225 4        
================== ======= ========= ======= ======= =========

Fastest task
------------
taskno=2, weight=278, duration=0 s, sources="1"

======== ======= ========= ======= ======= ===
variable mean    stddev    min     max     n  
======== ======= ========= ======= ======= ===
nsites   1.00000 0.0       1       1       121
weight   2.30000 2.394E-07 2.30000 2.30000 121
======== ======= ========= ======= ======= ===

Slowest task
------------
taskno=4, weight=278, duration=0 s, sources="1"

======== ======= ========= ======= ======= ===
variable mean    stddev    min     max     n  
======== ======= ========= ======= ======= ===
nsites   1.00000 0.0       1       1       121
weight   2.30000 2.394E-07 2.30000 2.30000 121
======== ======= ========= ======= ======= ===

Data transfer
-------------
================== =========================================================================== =========
task               sent                                                                        received 
RtreeFilter        srcs=145.14 KB monitor=18.25 KB srcfilter=14.71 KB                          167.37 KB
count_eff_ruptures sources=134.34 KB param=2.21 KB monitor=1.38 KB srcfilter=932 B gsims=524 B 1.4 KB   
================== =========================================================================== =========

Slowest operations
------------------
============================== ========= ========= ======
operation                      time_sec  memory_mb counts
============================== ========= ========= ======
PSHACalculator.run             0.70515   0.0       1     
managing sources               0.43318   0.0       1     
total prefilter                0.38476   3.46875   54    
splitting sources              0.06477   0.0       1     
reading composite source model 0.04902   0.0       1     
total count_eff_ruptures       0.04472   5.75781   4     
unpickling prefilter           0.02949   0.0       54    
store source_info              0.00610   0.0       1     
aggregate curves               0.00122   0.0       4     
unpickling count_eff_ruptures  0.00108   0.0       4     
reading site collection        6.979E-04 0.0       1     
saving probability maps        2.341E-04 0.0       1     
============================== ========= ========= ======