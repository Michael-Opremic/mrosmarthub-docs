User administration
-------------------
The company administration tool provides all functionalities to manage user accounts on IATA MRO SmartHub.

User list
=========
This screen shows an overview of the current user accounts of your company. On the top, aggregated statistics about the total users for each MRO SmartHub module are displayed: Connector accounts, Evaluator accounts and the total number of active and inactive accounts. In the table below, you can find a detailed overview of all user accounts. The color of the "User ID" column will indicate the status of the current user:

:Green: The user account is activated for at least one MRO SmartHub module and can access the platform.
:Yellow: The user account is activated but not activated for any MRO SmartHub module.
:Red: The user account is deactivated for the whole platform.

Within the table, you can activate and deactivate user accounts for specific MRO SmartHub modules or the complete platform by clicking on the respective active / inactive links. The activation and deactivation process underlies specific restrictions:

**Change account status -** You may only toggle the activation status of a user account after a fixed time interval after the last change to this account. This toggle time restriction is separate for each module and the complete user account, meaning you can, e.g., activate a user account for the Connector module and still be able to deactivate the account for the complete platform (given you have not done so in the recent time). The time interval may vary depending on your MRO SmartHub contract. If the contract does not specify a time interval, the default time interval is set to 30 days.

Clicking on the active / inactive links either informs you of the time when the next toggle is allowed or opens a new dialog window if it is currently possible to change the status of the user account. This dialog window will inform you of the consequences of activating / deactivating the access to the MRO SmartHub module or the user account

**Activating users -** This may also result in additional costs to your company according to the user pricing scheme in your MRO SmartHub contract. In that case, the dialog window will indicate this and show you the additional costs incurred by the activation. You have to confirm that you are allowed to perform the activation and accept the additional costs to proceed with the activation. This action is not reversible!

**Deactivating an MRO SmartHub module -** This will remove all authorizations for the respective module from the user account and prevents them from using it. Deactivating a user for the complete platform will remove all authorizations for this user account. The account will be prevented from logging into the platform.

Only user accounts that are activated for a particular module count towards your used user accounts. Inactive accounts are not considered for any limit of user accounts. 

These restrictions were set in place to inform you about any additional costs resulting from activating user account and to prevent the misuse of the user administration.

Authorizations
==============
This screen allows you to change specific authorizations on a user account level. On the left, you can select the user account for which you want to manage the authorizations. Once you have selected an account, a new table will show you all available authorizations and indicate whether the user account is enabled for it or not. You can add, remove or extend authorizations by clicking on the respective buttons within the table.

User authorizations have a dedicated expiry date until they are valid. If less than 6 days remain until an authorization will expire, the user is notified when logging in to MRO SmartHub.

The default expiry date when activating authorizations is set to 180 days from now. 

New user
========
This screen allows you to create new user accounts for your company or one of your subsidiaries. The top panel displays the automatically generated user name that will be used as the login name. You can also provide an account name that is connected to the new account. The account name will be displayed in the user list to allow easy identification of the account. You can select the company or one of your subsidiaries from the drop-down menu. Clicking on the "Create new user" button opens a confirmation dialog. Here, you can enter an initial password for the account or may use the automatically generated one. Make sure you take note of the password, as the password cannot be changed by the company administrator afterwards. The "Cancel" button cancels the creation of the new account, the "Confirm" button will create a deactivated user with the information provided by you. Confirming the dialog will close the dialog window, reset the account name and inform you of the status of the account creation. After a successful addition, you will find the new user account in the overview under "User list".

You may create as many user accounts as you would like. There are no restrictions in place as the users will be deactivated by default and therefore not count towards your used user accounts.