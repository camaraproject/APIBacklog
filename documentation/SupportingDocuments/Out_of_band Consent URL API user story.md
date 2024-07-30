# Consent URL API User Story


| **Item** | **Details** |
| ---- | ------- |
| ***Summary*** | As an enterprise application developer, I want my customer (end-user) to provide the consent to access certain CAMARA API before the actual API call is made, taking advantage of, for example, my onboarding process. |
| ***Roles, Actors and Scope*** | **Roles:** Customer:User, Customer:BusinessManager, Customer:Administrator,<br> End-user, Communication Service Provider (CSP), Channel Partner <br> **Actors:** End-user, Communication Service Provider (CSP), Channel Partner <br> **Scope:**  <br> - Retrieves a consent capture URL based on the required services, so end-user can accept/deny consent in a CSP webpage. |
| ***Pre-conditions*** |The preconditions are listed below:<br><ol><li>The Customer:BusinessManager and Customer:Administrator have been onboarded to the CSP's API platform.</li><li>The Customer:Administrator has onboarded the Customer:User to the platform.</li><li>The Customer:User performs an authorization request to CSP</li><li>The Customer:User has the access token allowing a secure access of the API.|
| ***Activities/Steps*** | **Starts when:** The customer application makes a request to the Consent URL API, including the end-user identifier whose consent will be retrieved, the scope(s) of the services requested and the purpose associated to them.<br>**Ends when:** The CSP provides the CSP's consent webpage URL to the customer application. |
| ***Post-conditions*** | The customer application can show the provided CSP's webpage to the end-user, where end-user will introduce CSP's end-user credentials to provide the required consent (or refuse it). |
| ***Exceptions*** | Several exceptions might occur during the Consent URL API operations<br>- Unauthorized: Not valid credentials (e.g., use of already expired access token).<br>- Invalid input: Not valid input data to invoke operation (e.g., improperly formatted end-user identifier).<br>- Scopes or purpose not compatible.|
