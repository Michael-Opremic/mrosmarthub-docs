Inventory
=========

All inventory interfaces are related to data that is either listed by the customer itself or is made available as external inventory by other platform users.

Receive own inventory
---------------------

This interface allows customers to download their own listings that are currently available on the platform. 

Data definition
^^^^^^^^^^^^^^^

The data that is provided by the platform is comprised of the following fields:

.. list-table:: getCurrentInventory return data definition
   :class: tight-table
   :widths: 20 10 70
   :header-rows: 1

   * - Field Name
     - Field Type
     - Description
   * - materialId
     - character
     - Internal platform material ID, i.e., part number stripped of any special characters
   * - connectorStockId
     - character(36)
     - Internal platform stock ID
   * - ownerStockId
     - character
     - Stock ID from stock owner/customer
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
     - Lead time in days
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
     - Quantity of parts
   * - unit
     - unit
     - See chapter "Valid values" section "Unit of Measure"
   * - dateOfManufacture
     - date
     - Date of manufacture of current part
   * - timeRemaining
     - integer
     - Remaining life time in days for affected part
   * - cyclesRemaining
     - integer
     - Remaining cycles for affected part
   * - shelfLife
     - date
     - Shelf life expiration date
   * - location
     - character
     - IATA 3-letter-code of closest airport to actual material location. An overview of all IATA codes can be found here
   * - company
     - character
     - In this service your own company name on SmartHub
   * - timeStampEntry
     - dateTime
     - Time of database entry


Web service access
^^^^^^^^^^^^^^^^^^

The getCurrentInventory web service provides the possibility to request the company's own inventory data via an automated interface. 

:Request method: GET
:URL: https://services.surplusdataconnection.com/getCurrentInventory
:Testing URL: https://services.test.surplusdataconnection.com/getCurrentInventory
:Accepted content type: application/octet-stream
:Parameters encoded in URL:
  - **user:** The customer’s login individual name for the platform account, e.g., zzz001
  - **key:** The customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
  - **filter:** Optional. Customers may filter the returned inventory by part number (field: pn) and/or condition (field: condition).
  - **Return data:** A JSON string containing the response status, response message and the stock data as defined above

Example
^^^^^^^

Usage

.. code-block:: none

  http://services.test.surplusdataconnection.com/getCurrentInventory?user=zzz001&key=keyzzz001

Result body

.. code-block:: JSON

  {
    "status": ["success"],
    "message": ["Uploaded inventory returned."],
    "data": {
      "materialId": ["PN1234"],
      "connectorStockId": ["6f95cd10-c8bb-4381-8b68-a255571aa2f0"],
      "ownerStockId": ["extStockId001"],
      "pn": ["PN-1234"],
      "description": ["Fuel pump"],
      "condition": ["OH"],
      "priceUsd": [1000],
      "sn": ["SN 001"],
      "mfr": ["MFR001"],
      "mroApprovalNo": [null],
      "mroName": ["OPREMIC SOLUTIONS"],
      "leadTime": [1],
      "tagDate": ["2018-01-lastOperator"],
      "lastOperator": ["TEST AIR"],
      "lastMsn": ["MSN001"],
      "incidentRelated": [false],
      "quantity": [1],
      "unit": ["each"],
      "dateOfManufacture": ["2017-01-01"],
      "timeRemaining":[2000],
      "cyclesRemaining":[100],
      "shelfLife": [2000],
      "location": ["Germany"],
      "company": ["OPREMIC SOLUTIONS"],
      "timeStampEntry":["2018-01-01 14:56:23"]
     }
   }


UI - File download
^^^^^^^^^^^^^^^^^^

For internal purposes, it is possible to download the provided inventory information manually from the platform by using the manual download functionality on the platform. The export format is a CSV file.

