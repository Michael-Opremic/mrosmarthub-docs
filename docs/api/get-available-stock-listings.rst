Stock listings
==============

Get available stock listings
----------------------------

The purpose of this service is to return all currently uploaded parts that are available for purchase for the requesting company.


Data definition
^^^^^^^^^^^^^^^

.. list-table:: getCurrentInventory return data definition
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
     - Internal platform material ID. Currently part number stripped of any special characters
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
     - Quantity of units
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


Web service access
^^^^^^^^^^^^^^^^^^

:Request method: GET
:URL: https:~/~/services.surplusdataconnection.com/getAvailableStock
:Testing URL: https:~/~/services.test.surplusdataconnection.com/getAvailableStock
:URL query parameters: user, key
   - **user:** The login name of the user's account, e.g., zzz001
   - **key:** The customer's web service security key associated with the user's account. This key can be changed in the parameters section of customer's settings in SC.
:Response: A JSON string containing the response status, response message and data with all parts that are visible to the requesting company, excluding own uploaded stock. The return fields are given in the table below. Empty fields will be returned as null.
:Example usage: https:~/~/services.test.surplusdataconnection.com/getAvailableStock?user=zzz001&key=keyzzz001


Example for result body
^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: JSON

   {
     "status":["success"],
     "message":["Available stock returned."],
     "data":  {
	"connectorStockId":["6f95cd10-c8bb-4381-8b68-a255571aa2f0"],
	materialId":["PN1234"],
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
	"timeStampEntry":["2018‑01‑01 14:56:23"]	
     }
   }



