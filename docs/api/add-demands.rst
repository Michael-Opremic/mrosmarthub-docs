Add demands
-----------


Data definition
^^^^^^^^^^^^^^^

.. list-table:: getCurrentInventory return data definition
   :class: tight-table
   :widths: 20 20 40 70
   :header-rows: 1

   * - Field Name
     - Required
     - Field Type
     - Description
   * - ownerDemandId
     - No
     - character
     - Demand ID from owner/customer
   * - pn
     - Yes
     - character
     - Part number
   * - condition
     - Yes
     - condition
     - Minimum condition
   * - maximumPriceUsd
     - No
     - numeric
     - Maximum price in USD
   * - mfr
     - character
     - Desired manufacturer
   * - latestDate
     - No
     - Date
     - Date the part is required latest
|tagDate| |Date|Tag date not older than
|incidentRelated| |boolean|Incident related allowed?
|quantity|Yes|integer|Quantity of parts
|unit|Yes|unit|Unit of quantity
|dateOfManufacture| |Date|Date of manufacture not older than
|timeRemaining| |integer|Minimum remaining life time in days for the current part
|cyclesRemaining| |integer|Minimum remaining cycles for the current part
|shelfLife| |Date|Minimum shelf life expiration date
|location| |character|IATA 3-letter-code of closest airport to actual required material location. An overview of all IATA codes can be found [[here>>https://en.wikipedia.org/wiki/IATA_airport_code]]


Webservice access
^^^^^^^^^^^^^^^^^

The purpose of this service is to add demand to the demand transmitted to the interface.
:Request method: POST
:URL: https:~/~/services.surplusdataconnection.com/postAddDemand
:Testing URL: https:~/~/services.test.surplusdataconnection.com/postAddDemand
:Accepted content type: application/x-www-form-urlencoded
:Parameters encoded in the body: user, key, data
   - **user:** Customer’s individual login name for the platform account, e.g., opr001
   - **key:** Customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
   - **data:** A JSON string containing the complete demand that shall add to the currently uploaded demand.
:Output: A JSON string containing the response status, response message and an empty data field.
Optional fields can be provided otherwise shall be filled with //null.//


Example for body content
^^^^^^^^^^^^^^^^^^^^^^^^^^

-


UI - File upload
^^^^^^^^^^^^^^^^

Additional demand may be added via a file upload. The upload button can be found in the //requests// tab under Buy. The uploaded file needs to be one of the formats described in section 7.2.
Additional demand can also be added manually in the //requests// tab under myTrade.


