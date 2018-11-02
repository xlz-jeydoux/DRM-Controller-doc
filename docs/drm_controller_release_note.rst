Release Note
============

   * Release: 3.0.0.0:
      * Naming convention
   * Release: 2.3.2.4:
      * Timing closure enhancement to work at 200 MHz
   * Release 2.3.2.3:
      * Refine DRM bus logic port naming conventions in IPXact abstract bus definition
   * Release 2.3.2.2:
      * Usage of aes128-cbc for P1735 encrypted IPs.
   * Release 2.3.2.1:
      * Split the DRM Bus IPXact abstract bus definition
      
         * Define a single common DRM Bus section to connect the DRM Controller to all IP Activators.
         * Define a dedicated DRM Bus section (aka. socket) to connect the DRM Controller to each IP Activator (one dedicated socket per IP Activator)