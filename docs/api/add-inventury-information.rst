Add inventory information
--------------------------

This interface allows customers to add new listings that will be available on the platform immediately after uploading.

Data definition
^^^^^^^^^^^^^^^

.. list table:: getCurrentInventory data definition
   :class: tight-table
   :widths: 20 10 10 70
   :header-rows: 1

   * - Field Name
     - Required
     - Field Type
     - Description
   * - ownerStockId
     - No
     - character
     - Stock ID from stock owner/customer   
   * - pn
     - Yes
     - character
     - Part number
   * - description
     - No
     - character
     - Part description
   * - condition
     - Yes
     - condition
     - See chapter "Valid values" section "Condition"
   * - priceUsd
     - Yes
     - numeric
     - Price in USD
   * - sn
     - No
     - character
     - Serial number
   * - mfr
     - Yes
     - character
     - Manufacturer
   * - mroApprovalNo
     - No
     - character
     - MRO approval number
   * - mroName
     - No
     - character
     - MRO name
   * - leadTime
     - No
     - integer
     - Lead time in days
   * - tagDate
     - No
     - date
     - Tag date
   * - lastOperator
     - No
     - character
     - Last Operator
   * - lastMsn
     - No
     - character
     - Last MSN
   * - incidentRelated
     - Yes
     - boolean
     - Was the corresponding aircraft incident related?
   * - quantity
     - Yes
     - integer
     - Quantity of parts
   * - unit
     - Yes
     - unit
     - See chapter "Valid values" section "Unit of Measure"
   * - dateOfManufacture
     - No
     - date
     - Date of manufacture of affected part
   * - timeRemaining
     - No
     - integer
     - Remaining life time in days of affected part
   * - cyclesRemaining
     - No
     - integer
     - Remaining cycles of affected part
   * - shelfLife
     - No
     - date
     - Shelf life expiration date
   * - location
     - character
     - IATA 3-letter-code of closest airport to actual material location.


Web service access
^^^^^^^^^^^^^^^^^^

The purpose of this service is to add new inventory items. It is accessed by a POST request.


:Request method: POST
:URL: https:~/~/services.surplusdataconnection.com/postAddStock
:Testing URL: https:~/~/services.test.surplusdataconnection.com/postAddStock
:Accepted content type: application/x-www-form-urlencoded
:Parameters encoded in the body:
   - **user:** The customer’s individual login name for the platform account, e.g., zzz001
   - **key:** The customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
   - **visibility:** A JSON string containing your internal company IDs for which the newly uploaded stock shall be visible. These will be matched to the platform's internal IDs automatically.
   - **data:** A JSON string containing the stock that shall be added to the currently uploaded stock. The required fields can be found in the table below.

:Output: A JSON string containing the response status, response message and an empty data field.
Optional fields can be provided but shall otherwise be filled with null.


Example for body content
^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: JSON

   {
      “ownerStockId”:[”ownStock01”],
      “pn”:[”PN‑1234”],
      ”description”:[”Fuel pump”],
      ”condition”:[”OH”],
      ”priceUsd”:[1000],
      ”sn”:[”SN001”],
      ”mfr”:[”MFR001”],
      ”mroApprovalNo”:[null],
      ”mroName”:[”OPREMIC SOLUTIONS”],
      ”leadTime”:[1],
      ”tagDate”:[”2018‑01‑01”],
      ”lastOperator”:[”TEST AIR”],
      ”lastMsn”:[”MSN001”],
      ”incidentRelated”:[false],
      "quantity":[1],
      "unit":["each"],
      "dateOfManufacture":["2017‑01‑01"],
      "timeRemaining":[100],
      "cyclesRemaining":[2000],
      "shelfLife":["2020‑01‑01"],
      "location":["Germany"]
    }


FTP - File upload
^^^^^^^^^^^^^^^^^

The additional stock can be provided via FTP. Login information will be provided during the integration project. The uploaded file needs to be one of the formats described in section "File uploads". The filename needs to be “addStock-YYYY-MM-DD”. Uploaded files will be scanned every 15 minutes. Therefore, there is a short time gap between uploading and accessibility of the data on the platform.


UI - File upload
^^^^^^^^^^^^^^^^

Additional inventory may be uploaded using the manual upload functionality on the platform. The uploaded file needs to be one of the formats described in section "File uploads". Existing inventory may be updated via the listing interface.
