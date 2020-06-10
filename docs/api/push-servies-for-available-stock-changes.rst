Push services for available stock changes
-----------------------------------------

To reduce the number of empty responses on scheduled requests for changes in inventory, the platform can proactively send data to a specified endpoint in the customer's IT system that tracks changes in visible stock since the last data transmission.
The endpoint on the customer side has to be set up by the customer. 

Several requirements have to be fulfilled by this endpoint:

- The connection should be SSL encrypted.
- The endpoint should accept HTTP POST requests.
- The endpoint should be secured with credentials. These credentials are provided as header fields.
- The endpoint should accept data in format and scope as defined in the following. The data is provided in the body of the request.

It is highly recommended that the customer stores the **internalStockId** that is provided by the platform to identify the correct stock entries in case multiple lines for the same part number exist.


Data definition
^^^^^^^^^^^^^^^

.. list-table:: 
   :class: tight-table
   :widths: 20 10 70
   :header-rows: 1

   * - Field Name
     - Field Type
     - Description
   * - connectorStockId
     - character(36)
     - Internal platform stock ID
   * - materialId
     - character
     - Internal platform material ID, i.e., part number stripped of any special characters
   * - pn
     - character
     - Part number
   * - description
     - character
     - Part description
   * - condition
     - condition
     - See chapter "Valid values" section "Condition"
   * - priceUsd
     - numeric
     - Price in USD
   * - sn
     - character
     - Serial number
   * - mfr
     - character
     - Manufacturer
   * - mroApprovalNo
     - character
     - MRO approval number
   * - mroName
     - character
     - MRO name
   * - leadTime
     - integer
     - Shipping time in days
   * - tagDate
     - date
     - Tag date
   * - lastOperator
     - character
     - Last Operator
   * - lastMsn
     - character
     - Last MSN
   * - incidentRelated
     - boolean
     - Was the corresponding aircraft incident related?
   * - quantity
     - integer
     - Quantity of parts (used if unit is length)
   * - unit
     - unit
     - See chapter "Valid values" section "Unit of Measure"
   * - dateOfManufacture
     - date
     - Date of manufacture of current part
   * - timeRemaining
     - integer
     - Remaining life time in days for the current part
   * - cyclesRemaining
     - integer
     - Remaining cycles for the current part
   * - shelfLife
     - date
     - Shelf life expiration date
   * - location
     - character
     - IATA 3-letter-code of closest airport to actual material location.
   * - company
     - character
     - Uploading company
   * - timeStampEntry
     - dateTime
     - Time of database entry
   * - dbAction
     - character
     - Action why this entry is considered as updated. For a specification of allowed values see below.


The data that is sent to the customer's endpoint only contains entries that have been changed on the platform since the last transmission. The field *dbAction* contains the specification what has been changed:

.. list-table::
   :class: tight-table
   :widths: 30 70
   :header-rows: 1
   
   * - dbAction code
     - Description
   * - ADD
     - Entry has been added to the database
   * - DEL
     - Entry has been removed from the database
   * - UPD
     - Entry has been updated in the database


The data is provided as a JSON string.


Example for result body
^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: JSON

  {
    "data":  {
	"connectorStockId":["6f95cd10-c8bb-4381-8b68-a255571aa2f0"],
	"materialId":["PN1234"],
	"pn":["PN‑1234"],
	"description":["Fuel pump"],
	"condition":["OH"],
	"priceUsd":[1000],
	"sn":["SN001"],
	"mfr":["MFR001"],
	"mroApprovalNo":[null],
	"mroName":["OPREMIC SOLUTIONS"],
	"leadTime":[1],
	"tagDate":["2018‑01‑01"],
	"lastOperator":["TEST AIR"],
	"lastMsn":["MSN001"],
	"incidentRelated":[false],
	"quantity":[1],
	"unit":["each"],
	"dateOfManufacture":["2017‑01‑01"],
	"timeRemaining":[100],
	"cyclesRemaining":[2000],
	"shelfLife":["2020‑01‑01"],
	"location":["Germany"],
	"company":["OPREMIC SOLUTIONS"],
	"timeStampEntry":["2018‑01‑01 14:56:23"],
	"dbAction":["ADD"]
     }
  }
