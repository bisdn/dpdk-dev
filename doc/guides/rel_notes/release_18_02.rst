DPDK Release 18.02
==================

.. **Read this first.**

   The text in the sections below explains how to update the release notes.

   Use proper spelling, capitalization and punctuation in all sections.

   Variable and config names should be quoted as fixed width text:
   ``LIKE_THIS``.

   Build the docs and view the output file to ensure the changes are correct::

      make doc-guides-html

      xdg-open build/doc/html/guides/rel_notes/release_18_02.html


New Features
------------

.. This section should contain new features added in this release. Sample
   format:

   * **Add a title in the past tense with a full stop.**

     Add a short 1-2 sentence description in the past tense. The description
     should be enough to allow someone scanning the release notes to
     understand the new feature.

     If the feature adds a lot of sub-features you can use a bullet list like
     this:

     * Added feature foo to do something.
     * Enhanced feature bar to do something else.

     Refer to the previous release notes for examples.

     This section is a comment. do not overwrite or remove it.
     Also, make sure to start the actual text at the margin.
     =========================================================

* **Added the ixgbe ethernet driver to support RSS with flow API.**

  Rte_flow actually defined to include RSS, but till now, RSS is out of
  rte_flow. This patch is to support igb and ixgbe NIC with existing RSS
  configuration using rte_flow API.

* **Add MAC loopback support for i40e.**

  Add MAC loopback support for i40e in order to support test task asked by
  users. According to the device configuration, it will setup TX->RX loopback
  link or not.

* **Add the support of run time determination of number of queues per i40e VF**

  The number of queue per VF is determined by its host PF. If the PCI address
  of an i40e PF is aaaa:bb.cc, the number of queues per VF can be configured
  with EAL parameter like -w aaaa:bb.cc,queue-num-per-vf=n. The value n can be
  1, 2, 4, 8 or 16. If no such parameter is configured, the number of queues
  per VF is 4 by default.

* **Added the i40e ethernet driver to support RSS with flow API.**

  Rte_flow actually defined to include RSS, but till now, RSS is out of
  rte_flow. This patch is to support i40e NIC with existing RSS
  configuration using rte_flow API.It also enable queue region configuration
  using flow API for i40e.

* **Added NVGRE and UDP tunnels support in Solarflare network PMD.**

  Added support for NVGRE, VXLAN and GENEVE tunnels.

  * Added support for UDP tunnel ports configuration.
  * Added tunneled packets classification.
  * Added inner checksum offload.

* **Added the igb ethernet driver to support RSS with flow API.**

  Rte_flow actually defined to include RSS, but till now, RSS is out of
  rte_flow. This patch is to support igb NIC with existing RSS configuration
  using rte_flow API.

* **Add AVF (Adaptive Virtual Function) net PMD.**

  A new net PMD has been added, which supports Intel® Ethernet Adaptive
  Virtual Function (AVF) with features list below:

  * Basic Rx/Tx burst
  * SSE vectorized Rx/Tx burst
  * Promiscuous mode
  * MAC/VLAN offload
  * Checksum offload
  * TSO offload
  * Jumbo frame and MTU setting
  * RSS configuration
  * stats
  * Rx/Tx descriptor status
  * Link status update/event


API Changes
-----------

.. This section should contain API changes. Sample format:

   * Add a short 1-2 sentence description of the API change. Use fixed width
     quotes for ``rte_function_names`` or ``rte_struct_names``. Use the past
     tense.

   This section is a comment. do not overwrite or remove it.
   Also, make sure to start the actual text at the margin.
   =========================================================


ABI Changes
-----------

.. This section should contain ABI changes. Sample format:

   * Add a short 1-2 sentence description of the ABI change that was announced
     in the previous releases and made in this release. Use fixed width quotes
     for ``rte_function_names`` or ``rte_struct_names``. Use the past tense.

   This section is a comment. do not overwrite or remove it.
   Also, make sure to start the actual text at the margin.
   =========================================================


Removed Items
-------------

.. This section should contain removed items in this release. Sample format:

   * Add a short 1-2 sentence description of the removed item in the past
     tense.

   This section is a comment. do not overwrite or remove it.
   Also, make sure to start the actual text at the margin.
   =========================================================


Known Issues
------------

.. This section should contain new known issues in this release. Sample format:

   * **Add title in present tense with full stop.**

     Add a short 1-2 sentence description of the known issue in the present
     tense. Add information on any known workarounds.

   This section is a comment. do not overwrite or remove it.
   Also, make sure to start the actual text at the margin.
   =========================================================


Shared Library Versions
-----------------------

.. Update any library version updated in this release and prepend with a ``+``
   sign, like this:

     librte_acl.so.2
   + librte_cfgfile.so.2
     librte_cmdline.so.2

   This section is a comment. do not overwrite or remove it.
   =========================================================


The libraries prepended with a plus sign were incremented in this version.

.. code-block:: diff

     librte_acl.so.2
     librte_bitratestats.so.2
     librte_bus_dpaa.so.1
     librte_bus_fslmc.so.1
     librte_bus_pci.so.1
     librte_bus_vdev.so.1
     librte_cfgfile.so.2
     librte_cmdline.so.2
     librte_cryptodev.so.4
     librte_distributor.so.1
     librte_eal.so.6
     librte_ethdev.so.8
     librte_eventdev.so.3
     librte_flow_classify.so.1
     librte_gro.so.1
     librte_gso.so.1
     librte_hash.so.2
     librte_ip_frag.so.1
     librte_jobstats.so.1
     librte_kni.so.2
     librte_kvargs.so.1
     librte_latencystats.so.1
     librte_lpm.so.2
     librte_mbuf.so.3
     librte_mempool.so.3
     librte_meter.so.1
     librte_metrics.so.1
     librte_net.so.1
     librte_pci.so.1
     librte_pdump.so.2
     librte_pipeline.so.3
     librte_pmd_bnxt.so.2
     librte_pmd_bond.so.2
     librte_pmd_i40e.so.2
     librte_pmd_ixgbe.so.2
     librte_pmd_ring.so.2
     librte_pmd_softnic.so.1
     librte_pmd_vhost.so.2
     librte_port.so.3
     librte_power.so.1
     librte_reorder.so.1
     librte_ring.so.1
     librte_sched.so.1
     librte_security.so.1
     librte_table.so.3
     librte_timer.so.1
     librte_vhost.so.3



Tested Platforms
----------------

.. This section should contain a list of platforms that were tested with this
   release.

   The format is:

   * <vendor> platform with <vendor> <type of devices> combinations

     * List of CPU
     * List of OS
     * List of devices
     * Other relevant details...

   This section is a comment. do not overwrite or remove it.
   Also, make sure to start the actual text at the margin.
   =========================================================
