# Custom-dialog-in-Dynamics-CRM
Register a custom dialog in Dynamics CRM

To register a custom dialog in Dynamics CRM, you can follow these steps:

1 - Navigate to the Settings area in Dynamics CRM.
2 - 1 - Click on "Processes" under the Process Center section.
3 - Click on the "New" button to create a new process.
4 - 1 - Choose the "Dialog" process type and click on the "OK" button.
5 - Give the dialog process a name and description.
6 - Add the required steps to the dialog process using the "Add Step" button.
7 - Configure each step as required, such as adding prompts and responses.
8 - Save and activate the dialog process.
9 - Once you have created and activated the custom dialog process, you can use the Xrm.Navigation.openDialog method to open the dialog in your Dynamics CRM application.

To open the custom dialog using Xrm.Navigation.openDialog, you will need to specify the name of the dialog as the first parameter of the method, followed by any additional parameters that you want to pass to the dialog.

For example, if you created a custom dialog with the name "My Custom Dialog", you could open the dialog using the following code:

var dialogOptions = {
    height: 400,
    width: 600,
    position: 1 , 
    title: "Custom dialog title"
};

Xrm.Navigation.openDialog("My Custom Dialog", dialogOptions).then(
    function (result) {
        // Perform action on success
    },
    function (error) {
        // Perform action on error
    }
);


In this example, the dialogOptions object is used to specify the height and width of the dialog. You can customize these options as needed for your custom dialog.
