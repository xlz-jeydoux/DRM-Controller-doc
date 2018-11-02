Features
========

The DRM Controller manages the sensitive data communication between the System Software (AXI4-Lite I/F) and the Protected IP Cores (DRM Bus I/F):

   * The DRM Controller reads and interprets the encrypted License Key and conveys securely the Activation Codes and the Credit timers to the Protected IP Cores
   * The DRM Controller collects the Metering Data from the Protected IP Cores and delivers an encrypted and authenticated Metering Data block to the System
   
The DRM Controller delivers to the System Software, design and chip level information for the License Key request:

   * DNA = Public Chip ID (128 bits)
   * Protected IPs VLNVs (64 bits each)
   
   
The DRM Controller enables 3 Licensing modes:

   * The Node Lock mode where a single License Key per circuit is used to provide Activation Codes to the Protected IPs. The License Key generation is based on the Public Chip ID. The License Key can be stored locally and reloaded at runtime whenever needed during the circuit lifecycle. The License Key can optionally contain a Credit timer value for each IP for temporary or demo licenses.
   * The Floating mode where a stream of time-based License Keys per circuit is used to provide Activation Codes and Credit Timers to the Protected IPs. The License Keys generation is based on the Public Chip ID and a random seed generated at runtime after reset. The License Key cannot be provisioned and can be used only during the current runtime, the DRM Controller keeping the random seed value until the next reset.
   * The Metering mode where an Activation session is maintained with Floating Licenses and a License Timer as long as the DRM Controller delivers authenticated Metering Data blocks. The License Timer initialization value determines the duration of the current random seed value and so the activation validity period and the Metering Data collection frequency. When the License Timer exhausts, the DRM Controller deactivates the IP Cores until a valid License Timer value is reloaded. The DRM Web Service delivers a new valid License Timer value only if an authenticated Metering Data block is provided in the License request. This mechanism enforces a periodic Metering Data collection during the HW operations.
   
   Supported License Types per FPGA Vendor:

.. list-table::
   :header-rows: 1

   * - 
     - Xilinx
     - Intel
   * - **Metering**
     - YES
     - YES
   * - **Floating**
     - YES
     - YES
   * - **Node Lock**
     - YES
     - Partially [#f1]_
     

.. rubric:: Footnotes

.. [#f1] Supported on :ref:`FPGA supported` excepted on `Intel PAC <https://www.intel.com/content/www/us/en/programmable/products/boards_and_kits/dev-kits/altera/acceleration-card-arria-10-gx.html>`_  context, because Chip ID primitive is not reachable

