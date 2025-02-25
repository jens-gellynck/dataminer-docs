---
uid: DashboardButton
---

# Button

> [!WARNING]
> This feature is currently still in preview. For more information, see [Soft-launch options](https://community.dataminer.services/documentation/soft-launch-options/).

This dashboard component is available in soft launch from DataMiner 10.0.3 onwards, if the soft-launch option *ReportsAndDashboardsButton* is enabled.

The component can be linked to one or more button parameters, so that users can click a button to execute a particular action.

To configure the component:

1. Apply a parameter data feed. See [Applying a data feed](xref:Configuring_dashboard_components#applying-a-data-feed).

   You will only be able to select button parameters for the data feed. Several parameters can be added in the same component.

1. Fine-tune the component layout. In the *Component* > *Layout*, tab the following options are available:

   - The default options available for all components. See [Customizing the component layout](xref:Configuring_dashboard_components#customizing-the-component-layout).

   - In case the component displays more than one parameter, in the *Advanced* > *Layout* section, you can adjust the way the different items are displayed:

     - *Layout*: Determines whether the different items are displayed next to each other or below each other. However, note that when the dashboard is used on a small screen, they will always be displayed below each other.

     - *Maximum rows per page*: Determines how many items can at most be displayed below each other on a single page.

     - *Maximum columns per page*: Determines how many items can at most be displayed next to each other on a single page.

   - The *Button text* option allows you to customize the text that should be displayed on the button. By default, the button displays the same text as in Cube.

1. Optionally, configure the following settings in the *Settings* tab:

   - To use a different polling interval for this component than the standard interval configured for the dashboard, in the *WebSocket settings* section, clear the checkbox and specify a different polling interval (in seconds).

   - In case the component displays more than one parameter, configure how the parameters should be grouped: by parameter, by element, by table index (if relevant) or by all the above together.

   - In case the button triggers an Automation script, additional settings will also be available related to this script.

     - Depending on the script configuration, it may be possible to configure the parameters and/or dummies used in the script. For each of the parameters and dummies, a checkbox allows you to select whether these are required, i.e. whether the script can be executed only if these are filled in.

       > [!NOTE]
       > The input for an interactive Automation script in a dashboard can be specified by the user or retrieved via linked feeds. In case both are possible for the same component, user input always takes precedence.
       >
       > In case several feeds are linked to the component, they are considered in the order they were added. For example, if 2 feeds are used and the feed that was first added is applicable, the second feed will be ignored.

     - The standard options for script execution can be configured. See [Script execution options](xref:Script_execution_options).

     - The following additional options are available:

       - *Ask for confirmation*: Determines whether the user will be asked for confirmation before the script is executed.

       - *Show success popup*: Determines whether a pop-up message is displayed when the script has been successfully executed. By default enabled.

       - *Custom success message*: Allows you to configure a custom message to be displayed when the script has been successfully executed.
