Classical Hazard QA Test, Case 11
=================================

============== ===================
checksum32     3,151,174,296      
date           2018-06-05T06:39:13
engine_version 3.2.0-git65c4735   
============== ===================

num_sites = 1, num_levels = 4

Parameters
----------
=============================== ==================
calculation_mode                'classical'       
number_of_logic_tree_samples    0                 
maximum_distance                {'default': 200.0}
investigation_time              1.0               
ses_per_logic_tree_path         1                 
truncation_level                0.0               
rupture_mesh_spacing            0.01              
complex_fault_mesh_spacing      0.01              
width_of_mfd_bin                0.001             
area_source_discretization      10.0              
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
b1_b2     0.20000 trivial(1)      1/1             
b1_b3     0.60000 trivial(1)      1/1             
b1_b4     0.20000 trivial(1)      1/1             
========= ======= =============== ================

Required parameters per tectonic region type
--------------------------------------------
====== ================ ========= ========== ==========
grp_id gsims            distances siteparams ruptparams
====== ================ ========= ========== ==========
0      SadighEtAl1997() rrup      vs30       mag rake  
1      SadighEtAl1997() rrup      vs30       mag rake  
2      SadighEtAl1997() rrup      vs30       mag rake  
====== ================ ========= ========== ==========

Realizations per (TRT, GSIM)
----------------------------

::

  <RlzsAssoc(size=3, rlzs=3)
  0,SadighEtAl1997(): [0]
  1,SadighEtAl1997(): [1]
  2,SadighEtAl1997(): [2]>

Number of ruptures per tectonic region type
-------------------------------------------
================ ====== ==================== ============ ============
source_model     grp_id trt                  eff_ruptures tot_ruptures
================ ====== ==================== ============ ============
source_model.xml 0      Active Shallow Crust 3,500        3,000       
source_model.xml 1      Active Shallow Crust 3,000        3,000       
source_model.xml 2      Active Shallow Crust 2,500        3,000       
================ ====== ==================== ============ ============

============= =====
#TRT models   3    
#eff_ruptures 9,000
#tot_ruptures 9,000
#tot_weight   900  
============= =====

Slowest sources
---------------
========= ============ ============ ========= ========== ========= ========= ======
source_id source_class num_ruptures calc_time split_time num_sites num_split events
========= ============ ============ ========= ========== ========= ========= ======
1         PointSource  2,500        0.01910   1.669E-06  1.00000   3         0     
========= ============ ============ ========= ========== ========= ========= ======

Computation times by source typology
------------------------------------
============ ========= ======
source_class calc_time counts
============ ========= ======
PointSource  0.01910   1     
============ ========= ======

Duplicated sources
------------------
There are no duplicated sources

Information about the tasks
---------------------------
================== ======= ======= ======= ======= =========
operation-duration mean    stddev  min     max     num_tasks
RtreeFilter        0.01297 0.00385 0.00959 0.01716 3        
count_eff_ruptures 0.00846 0.00126 0.00701 0.00934 3        
================== ======= ======= ======= ======= =========

Fastest task
------------
taskno=2, weight=300, duration=0 s, sources="1"

======== ======= ====== === === =
variable mean    stddev min max n
======== ======= ====== === === =
nsites   1.00000 NaN    1   1   1
weight   300     NaN    300 300 1
======== ======= ====== === === =

Slowest task
------------
taskno=1, weight=350, duration=0 s, sources="1"

======== ======= ====== === === =
variable mean    stddev min max n
======== ======= ====== === === =
nsites   1.00000 NaN    1   1   1
weight   350     NaN    350 350 1
======== ======= ====== === === =

Data transfer
-------------
================== ======================================================================== ========
task               sent                                                                     received
RtreeFilter        srcs=3.42 KB monitor=1.01 KB srcfilter=837 B                             3.76 KB 
count_eff_ruptures sources=3.9 KB param=1.29 KB monitor=1.03 KB srcfilter=699 B gsims=360 B 1.05 KB 
================== ======================================================================== ========

Slowest operations
------------------
============================== ========= ========= ======
operation                      time_sec  memory_mb counts
============================== ========= ========= ======
PSHACalculator.run             0.40439   0.0       1     
managing sources               0.18433   0.0       1     
total prefilter                0.03890   2.85156   3     
total count_eff_ruptures       0.02537   5.65234   3     
reading composite source model 0.02113   0.0       1     
store source_info              0.00781   0.0       1     
aggregate curves               0.00121   0.0       3     
unpickling count_eff_ruptures  0.00102   0.0       3     
unpickling prefilter           8.547E-04 0.0       3     
reading site collection        8.245E-04 0.0       1     
splitting sources              3.660E-04 0.0       1     
saving probability maps        2.551E-04 0.0       1     
============================== ========= ========= ======