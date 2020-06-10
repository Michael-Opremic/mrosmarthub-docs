Demands
=======

The following interfaces allow customers on the platform to access and manipulate their own demand data.


Get demands
-----------

This interface enables customers to download their uploaded demands.


Data definition
^^^^^^^^^^^^^^^

.. list-table:: 
   :class: tight-table
   :widths: 20 10 70
   :header-rows: 1

   * - Field Name
     - Field Type
     - Description
   * - ownerDemandId
     - character
     - Demand ID from stock owner/customer
   * - connectorDemandId
     - character(36)
     - Internal platform ID
   * - pn
     - character
     - Part number
   * - condition
     - condition
     - Minimum condition
   * - maximumPriceUsd
     - numeric
     - Maximum price in USD
   * - mfr
     - character
     - Desired manufacturer
   * - latestDate
     - Date
     - Date the part is required latest
   * - tagDate
     - Date
     - Tag date not older than
   * - incidentRelated
     - boolean
     - Incident related allowed?
   * - quantity
     - integer
     - Quantity of parts
   * - unit
     - unit
     - Unit of quantity
   * - dateOfManufacture
     - Date
     - Date of manufacture not older than
   * - timeRemaining
     - integer
     - Minimum remaining life time in days for the current part
   * - cyclesRemaining
     - integer
     - Minimum remaining cycles for the current part
   * - shelfLife
     - Date
     - Minimum shelf life expiration date
   * - location
     - character
     - IATA 3-letter-code of closest airport to actual required material location.


Webservice access
^^^^^^^^^^^^^^^^^

The purpose of this service is to allows customers to get a complete list of demands currently uploaded to the platform.

 - **Request method:** GET
 - **Accepted content type:** application/octet-stream
 - **URL:** https://services.surplusdataconnection.com/getCurrentDemands
 - **Testing URL:** https://services.test.surplusdataconnection.com/getCurrentDemands
 - **URL query parameters:** user, key, filter
    
    - *user:* Customer’s individual login name for the platform account, e.g., opr001
    - *key:* Customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
    - *filter:* Optional. Customer's may filter the returned demands by part number (field: pn).


 - **Return data:** A JSON string containing the response status, response message and a data field with the information given by the data definition.


Example usage
^^^^^^^^^^^^^

.. code-block:: 

    https://services.test.surplusdataconnection.com/getCurrentDemands?user=zzz001&key=keyzzz001&filter={"pn":["PN-1234","PN-2345"]}


UI - File download
^^^^^^^^^^^^^^^^^^

The customer may also review and export this information in the *Settings* tab under Profile.

