Remove demands
--------------


Data definition
^^^^^^^^^^^^^^^

.. list-table:: 
   :class: tight-table
   :widths: 20 20 40 70
   :header-rows: 1

   * - Field Name
     - Required
     - Field Type
     - Description
   * - connectorDemandId
     - Yes (but may be empty)
     - character (36)
     - Internal platform ID
   * - ownerDemandId
     - Yes (but may be empty)
     - character
     - Demand ID from owner/customer

The interface always expects a JSON including both fields, but only one filled must be filled. The other field has to be provided but shall be filled with //null.


Web service access
^^^^^^^^^^^^^^^^^^

The purpose of this service is to remove specific parts of the currently uploaded demand.

- **Request method:** POST
- **URL:** https://services.test.surplusdataconnection.com/postRemoveDemand
- **Accepted content type:** application/x-www-form-urlencoded
- **Parameters encoded in the body:** *user, key, data*
   - *user:* Customer’s individual login name for the platform account, e.g., opr001
   - *key:* Customer’s individual web service security key for the platform account. This key can be changed in the parameters section under Settings on the platform.
   - *data:* A JSON string containing the demand IDs that shall be removed from the currently uploaded demand.
- **Output:** A JSON string containing the response status, response message and an empty data field.


Example for body content
^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: 

    user=zzz001&key=keyzzz001&data={"ownerDemandId":["MYCOMP001","MYCOMP002"],"connectorDemandId":[null,null]}


UI - Manual input
^^^^^^^^^^^^^^^^^

Demands can be manually removed by using the remove button in the *Requests* tab under menu *Buy*.



