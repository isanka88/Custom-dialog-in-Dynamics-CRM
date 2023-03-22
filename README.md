# Register a custom dialog in Dynamics CRM

#### To register a custom dialog in Dynamics CRM, you can follow these steps:

- Navigate to the Settings area in Dynamics CRM.
- Click on "Processes" under the Process Center section.
- Click on the "New" button to create a new process.
- Choose the "Dialog" process type and click on the "OK" button.
- Give the dialog process a name and description.
- Add the required steps to the dialog process using the "Add Step" button.
- Configure each step as required, such as adding prompts and responses.
- Save and activate the dialog process.
- Once you have created and activated the custom dialog process, you can use the Xrm.Navigation.openDialog method to open the dialog in your Dynamics CRM application.

To open the custom dialog using Xrm.Navigation.openDialog, you will need to specify the name of the dialog as the first parameter of the method, followed by any additional parameters that you want to pass to the dialog.

## 🛠 For example, if you created a custom dialog with the name "My Custom Dialog", you could open the dialog using the following code:

```bash
var dialogOptions = {
    height: 400,
    width: 600,
    position: 1 , 
    title: "Custom dialog title"
};

var dialogParameters = {};
dialogParameters["QuoteId"] = quoteId;
dialogParameters["OpportunityId"] = ClientUtility.DataUtil.isNullOrEmptyString(opportunityId) ? ClientUtility.Guid.Empty : ClientUtility.Guid.create(opportunityId);
dialogParameters["CanCloseOpportunity"] = canCloseOpportunity;
dialogParameters["ClosedState"] = Sales.QuoteState.Won;
dialogParameters["TimeZoneOffsetMinutes"] = Xrm.Utility.getGlobalContext().userSettings.getTimeZoneOffsetMinutes();


Xrm.Navigation.openDialog("My Custom Dialog", dialogOptions, dialogParameters).then(
    function (result) {
        // Perform action on success
    },
    function (error) {
        // Perform action on error
    }
);
```

In this example, the dialogOptions object is used to specify the height and width of the dialog. You can customize these options as needed for your custom dialog.
