---
uid: Clearing_alarms
---

# Clearing alarms

By default, alarms are cleared automatically. However, if you set the AutoClear system setting to “false”, then all alarms will have to be cleared manually.

- [Automatic versus manual alarm clearing](#automatic-versus-manual-alarm-clearing)

- [Manually clearing an alarm](#manually-clearing-an-alarm)

- [System-wide AutoClear setting](#system-wide-autoclear-setting)

- [Overriding the default AutoClear setting on parameter level](#overriding-the-default-autoclear-setting-on-parameter-level)

> [!NOTE]
> - It is possible that because of database issues, duplicate alarms are created for column parameters. In that case, the oldest one will automatically be cleared, and the following comment will be added to the alarm:<br>*Detected duplicate alarm on column parameter. Clearing alarm for PID \[x\] with ROOTKey \[y\] found alarm with other ROOTKey \[z\]*
> - In DataMiner 10.2.0/10.1.6, a protection mode has been added to avoid reduced performance of the system when an alarm storm happens that causes there to be a large number of clearable alarms at the same time. By default, when there are more than 1000 clearable alarm trees on a DMA, the newly generated clearable alarms will be closed instead of clearable. Once the number of clearable alarm trees has dropped to less than 100, this protection mode is lifted and newly generated alarms will be clearable again. Note that these default values can be customized in DataMiner.xml (see [DataMiner.xml](xref:DataMiner_xml#dataminerxml)).

> [!TIP]
> See also: [Alarm Console – Working with clearable alarms](https://community.dataminer.services/video/alarm-console-working-with-clearable-alarms/) on DataMiner Dojo.

## Automatic versus manual alarm clearing

### About automatic alarm clearing

By default, a DataMiner alarm of which the severity returns to normal is automatically cleared by the system.

![](~/user-guide/images/AlarmClearingAuto.jpg)

### About manual alarm clearing

A DataMiner alarm of which the severity returns to normal can also be kept in a “clearable” state until a user clears it by hand. This prevents alarms from disappearing from the system before being explicitly cleared by a user.

![](~/user-guide/images/AlarmClearingManual.jpg)

> [!NOTE]
> Alarms that reoccur before they have been cleared by a user will be linked to the original alarm. In other words, when the same alarm occurs several times in a short period of time, it will only have to be cleared once.

## Manually clearing an alarm

To manually clear an alarm:

1. Right-click the alarm in the Alarm Console and select *Clear alarm*.

1. In the *Clear alarm* window, add a comment if necessary, and click the *Clear alarm* button at the bottom.

Alternatively, if a column with action buttons to clear alarms has been added in the Alarm Console, you can also click the *X* in this column. For more information on how to add action buttons, see [Changing the column layout in an alarm tab](xref:ChangingTheAlarmConsoleLayout#changing-the-column-layout-in-an-alarm-tab).

> [!NOTE]
> - If the alarm is not yet in a clearable state, the *Clear alarm* option is not shown.
> - Clearing a clearable correlated alarm also clears the clearable base alarms. For more information on Correlation, see [DMS Correlation](xref:correlation#dms-correlation).

## System-wide AutoClear setting

The default AutoClear setting can be configured in the *C:\\Skyline DataMiner\\MaintenanceSettings.xml* file.

If you set the AutoClear setting to FALSE, alarms will not be cleared automatically. Instead, they will get into a “clearable” state, and someone will have to manually clear them.

> [!TIP]
> See also: [MaintenanceSettings.xml](xref:MaintenanceSettings_xml#maintenancesettingsxml)

## Overriding the default AutoClear setting on parameter level

When editing an alarm template, you can override the AutoClear system settings for particular alarms.

For more information on how to do this, see [Setting the autoclear options for alarms in an alarm template](xref:Configuring_alarm_templates#setting-the-autoclear-options-for-alarms-in-an-alarm-template).
