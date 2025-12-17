### API family name
Group Management

### API family owner
T-Mobile US

### API summary
The Group Management API enables API Consumers to create and manage named groups of pre-defined entities (e.g. devices or areas). It supports batch membership operations and event-driven notifications, making it ideal for Service APIs (e.g., Geofencing) that need to manage and track sets of entities, and be informed about changes to group member states.
Both Subscription based and not subscription-based Service APIs can make use of the Group concept.
Example scenarios:
-	A logistics company that has thousands of vehicles and hundreds of sorting centers is onboarded as an API consumer with an API Provider (e.g. Operator A) for the use of the Geofencing Subscriptions API. The logistics company wants to receive event notifications, each time their vehicles enter and exit a certain radius of any of their sorting centers.
-	An API Consumer (e.g. Service Provider) partners with an API Provider (e.g. Telco Operator) to deploy IoT devices (e.g., sensors, trackers) across a nationwide cellular network. To ensure prolonged device battery life and operational efficiency, the Service Provider seeks to activate power-saving configurations for part of its IoT fleet (e.g. specific type of device) during periods of low activity or based on predefined thresholds.
In each of the example scenarios above, Groups of Devices are referenced.  In the Geofencing a group of Areas is also mentioned.
Following is a list of Actions with perceived Inputs/Outputs for the Group Management API.

| Action                        | Inputs                                                      | Output                                                                                 |
|-------------------------------|-------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Create Group                  | groupName, groupType, [members], [subscriptionRequest]      | Group details (groupId, groupName, groupType, memberSummary) [failedMembers]           |
| Get specific Group Info       | groupId                                                     | Group summary (groupId, groupName, groupType, memberSummary)                           |
| Get list of Groups Info       | No Input                                                    | Array of Group Summary                                                                 |
| Delete Group                  | groupId                                                     | Success/Accepted (no content)                                                          |
| Add Members to Group          | groupId, members, action=add, [subscriptionRequest]         | MembersBatchResult (groupId, results)                                                  |
| Update/Delete Members in Group| groupId, members (with entityId), action=update/delete, [subscriptionRequest] | MembersBatchResult (groupId, results)                                    |
| List Members by Status        | groupId, status, [limit], [cursor]                          | MembersListPage (groupId, status, members, nextCursor)                                 |
| Subscribe to Group Events     | subscriptionRequest (sink, eventTypes, config)              | CloudEvents (delivered asynchronously)                                                 |
| Handle Subscription Errors    <br>*Note: This may have to be handled in Service API domain.*| (Asynchronous event, no direct input)                       | CloudEvent (subscription-error)                                                        |



### Technical viability
This API doesn’t depend on any core network functionality.  However, it is intended to reduce the burden on the API Consumers by shifting some processing requirements to the API Provider side.
Special Note: The proposal recommends use of ‘new style’ of Subscription API Design (see [Improve CloudEvents Compliance and Consolidate Subscription API Design Across CAMARA subprojects](https://github.com/camaraproject/Commonalities/issues/556))


### Commercial viability
Not known to be available at this time but deemed viable.

### YAML code available?
YES

### Validated in lab/productive environments?
NO


### Validated with real customers?
NO

### Validated with operators?
NO

### Supporters in API Backlog Working Group

