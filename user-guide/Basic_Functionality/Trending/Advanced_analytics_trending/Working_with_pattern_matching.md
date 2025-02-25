---
uid: Working_with_pattern_matching
---

# Working with pattern matching

From DataMiner 10.0.7 onwards, on systems using a Cassandra and Elasticsearch database, DataMiner Analytics can automatically recognize recurring patterns in trend data. For this purpose, patterns need to be marked with so-called tags.

If you are viewing a trend graph for a single parameter, and it contains patterns matching existing tags, these will be highlighted in orange when you hover the mouse pointer over the button representing a tag, or if the option *Expand tags* is selected in the right-click menu. Matches found for the same element/parameter as the one for which a tag was defined will be shown in bright orange, while matches associated with tags created for another element/parameter will be shown in lighter orange.

> [!NOTE]
> - If a protocol is deleted, all patterns defined for parameters of that protocol will also be deleted the first time the SLAnalytics service restarts.
> - Patterns must have a size between 8 and 50,000 data points and should not have more than 5 percent missing values.
> - Pattern matching can only be performed on trended parameters containing numeric values.
> - If pattern matching is performed on a trend graph showing more than 100,000 data points, an aggregated level of detail will be used to improve performance at the cost of accuracy. If, at the most aggregated level, the number of data points exceeds 100,000 data points, no pattern matching will be performed.
> - You can enable or disable this feature via *System Center* > *System settings* > *analytics config.*

> [!TIP]
> See also: [Monitoring of trend patterns](xref:Advanced_analytics_features_in_the_Alarm_Console#monitoring-of-trend-patterns)

## Defining a tag

To define a tag for pattern matching:

1. In a trend graph showing trend information for one single parameter, select the section of the graph that you identify as a recurring pattern.

   The way you can select a section of a graph depends on the configuration of the trending user settings. See [Trending settings](xref:User_settings#trending-settings).

1. Click the tag icon and enter a tag name.

1. From DataMiner 10.0.13 onwards, for a table parameter, optionally clear the checkbox *\[Display key instance\] only* if you do not want the display key of the parameter to be taken into account to match the tag.

   > [!NOTE]
   > Prior to DataMiner 10.0.13, patterns can only be detected in the trending for a specific parameter ID, without taking any possible table index into account. Clearing the *\[Display key instance\] only* checkbox therefore results in the behavior of DataMiner versions prior to 10.0.13.

1. From DataMiner 10.0.13 onwards, optionally select *Generate an alarm when detected* to have DataMiner generate a “suggestion event” type of alarm whenever the pattern is detected. For more information, see [Monitoring of trend patterns](xref:Advanced_analytics_features_in_the_Alarm_Console#monitoring-of-trend-patterns).

1. Click the check mark to save the tag.

## Editing a tag

To edit an existing tag for pattern matching:

1. Click the tag button above the (highlighted) pattern you want to edit.

1. To edit the tag name, click the pencil icon and change the name.

1. To activate or deactivate alarm monitoring on the pattern, toggle the option *Generate an alarm when detected*. For more information, see [Monitoring of trend patterns](xref:Advanced_analytics_features_in_the_Alarm_Console#monitoring-of-trend-patterns).

1. To redefine the pattern, adjust its boundaries.

1. To save any modifications, click the check mark.

## Deleting a tag

To delete a tag for pattern matching:

1. Click the tag button above the (highlighted) pattern you want to delete.

1. Click the delete icon.

1. In the confirmation box, click Yes.

> [!NOTE]
> If you delete a tag, all pattern matches associated with that tag will also be removed.
>
