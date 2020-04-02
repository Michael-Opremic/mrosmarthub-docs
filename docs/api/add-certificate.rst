Add certificate
---------------

Certificate information will currently be handled as PDF files. If available, the certificates will be displayed individually for each inventory item via a clickable certificate link. To make certificate information available, the customer may upload the corresponding PDF file to the platform by using the certificate upload functionality in the //listings// tab or use an FTP upload. Due to file size limitations, these are the only options available for certificate uploads.


FTP - File upload
^^^^^^^^^^^^^^^^^

Certificate information has to be provided as zip files. The zip can only contain PDF files. Naming conventions for the PDF files are based on the internal IDs of the platform. The customer may obtain these IDs via the current inventory download. Therefore, the file name has to be “[internalMaterialId].pdf”, where [internalMaterialId] has to be replaced by the internal IDs of the inventory. These files will then be attached to the corresponding inventory items. The zip itself has to be named “certificates-YYYY-MM-DD.zip”.
Customers must only upload one certificate PDF file per ID. Therefore, all certificates for the corresponding inventory item must be included in a single PDF file. All duplicates will be overwritten with the newest upload.
Files will be scanned every 15 minutes. Therefore, there is a short time gap between uploading and accessibility of the data on the platform.


UI - File upload
^^^^^^^^^^^^^^^^

In the tab //listings// under myTrade, customers can find an upload button for individual certificate information for specific stock items.
