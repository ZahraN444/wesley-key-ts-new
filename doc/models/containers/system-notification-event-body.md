
# System Notification Event Body

## Class Name

`SystemNotificationEventBody`

## Cases

| Type |
|  --- |
| [`SystemAlertNotificationEvent`](../../../doc/models/system-alert-notification-event.md) |
| [`SystemMaintenanceNotificationEvent`](../../../doc/models/system-maintenance-notification-event.md) |
| [`SystemPerformanceNotificationEvent`](../../../doc/models/system-performance-notification-event.md) |

## SystemAlertNotificationEvent

### Initialization Code

#### Example

```ts
const value: SystemNotificationEventBody = {
  systemAlertNotificationEventType: 'system.alert',
};
```

## SystemMaintenanceNotificationEvent

### Initialization Code

#### Example

```ts
const value: SystemNotificationEventBody = {
  systemMaintenanceNotificationEventType: 'system.maintenance',
};
```

## SystemPerformanceNotificationEvent

### Initialization Code

#### Example

```ts
const value: SystemNotificationEventBody = {
  systemPerformanceNotificationEventType: 'system.performance',
};
```

