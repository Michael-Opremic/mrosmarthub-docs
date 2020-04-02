Remove inventory
----------------

This interface allows customers to remove listed stock from the platform. To this end, the customers have to provide the stock IDs of the part that they want to remove. The IDs used can either be the connectorStockId defined by the platform or the ownerStockId assigned and uploaded by the customer. The connectorStockId may be collected by using the getCurrentInventory web service.


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
   * - connectorStockId
     - Yes (but may be empty)
     - character
     - Internal platform stock ID
   * - ownerStockId
     - Yes (but may be empty)
     - character
     - Stock ID from stock owner/customer


The interface always expects a JSON including both fields, but only one field must be filled. The other field has to be provided but shall be filled with null.


Web service access
^^^^^^^^^^^^^^^^^^

The purpose of this service is to remove specific parts of the currently uploaded inventory.

:Request method: POST
:URL: https:~/~/services.surplusdataconnection.com/postRemoveStock
:Testing URL: https:~/~/services.test.surplusdataconnection.com/postRemoveStock
:Accepted content type: application/x-www-form-urlencoded
:Parameters encoded in the body:
 - **user:** The customer’s individual login name for the platform account, e.g., zzz001
 - **key:** The customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
 - **data:** A JSON string containing the stock IDs that shall be removed from the currently uploaded inventory.
:Output: A JSON string containing the response status, response message and an empty data field.


Example for body content
^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: JSON

  { 
	“ownerStockId”:[“owner_stock_01”,
	”owner_stock_02”],
	“connectorStockId”:[null,null]
  }


UI - Manual removal
^^^^^^^^^^^^^^^^^^^

Inventory may be manually removed by using the corresponding removal button in the //listings// tab under myTrade on the platform. The complete inventory can also be removed by using the removal button in the //settings// tab under myTrade.
