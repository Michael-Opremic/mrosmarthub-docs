Replace inventory
-----------------

This interface is designed to update the complete inventory in one process. The inventory data sent is compared to the current data on the platform and add, delete, or update operations are performed as required for each individual position.


Data definition
^^^^^^^^^^^^^^^

.. list-table:: getCurrentInventory return data definition
   :class: tight-table
   :widths: 20 10 20 70
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
     - Nodate
     - Date of manufacture of current part
   * - timeRemaining
     - No
     - integer
     - Remaining life time in days for the current part
   * - cyclesRemaining
     - No
     - integer
     - Remaining cycles for the current part
   * - shelfLife
     - No
     - date
     - Shelf life expiration date
   * - location
     - No
     - character
     - IATA 3-letter-code of closest airport to actual material location.


Web service access
^^^^^^^^^^^^^^^^^^

The purpose of this service is to completely replace the currently uploaded inventory with the inventory transmitted to the interface. It is accessed by a POST request.

:Request method: POST
:URL: https:~/~/services.surplusdataconnection.com/postReplaceStock
:Testing URL: https:~/~/services.test.surplusdataconnection.com/postReplaceStock
:Accepted content type: application/x-www-form-urlencoded
:Parameters encoded in the body:
   - **user:** The customer’s individual login name for the platform account, e.g., zzz001
   - **key:** The customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
   - **visibility:** A JSON string containing your internal company IDs for which the newly uploaded stock shall be visible. These will be matched to the platforms internal IDs automatically.
   - **data:** A JSON string containing the complete stock that shall replace the currently uploaded stock. The required fields can be found in the table below.
:Output: A JSON string containing the response status, response message and an empty data field.
Optional fields can be provided otherwise shall be filled with null.


Example for body content
^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: JSON

  {
	“ownerStockId”:[“MYCOMP001”],
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

Since uploads of complete inventories are usually large files, a FTP upload is also available. Access will be provided during the integration project. The uploaded file needs to be one of the formats described in section "File uploads". The file name needs to be “replaceInventory-YYYY-MM-DD”. Uploaded files will be scanned every 15 minutes. Therefore, there is a short time gap between uploading and accessibility of the data on the platform.


UI - File upload
^^^^^^^^^^^^^^^^

Under myTrade on the platform, customers have the opportunity to replace the current stock by first removing their complete stock in the //settings// tab and then uploading a new file in the //add listings// tab. The uploaded file needs to be one of the formats described in section "File uploads".
