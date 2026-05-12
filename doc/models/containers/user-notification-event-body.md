
# User Notification Event Body

## Class Name

`UserNotificationEventBody`

## Cases

| Type |
|  --- |
| [`UserActionNotificationEvent`](../../../doc/models/user-action-notification-event.md) |
| [`UserStatusNotificationEvent`](../../../doc/models/user-status-notification-event.md) |
| [`UserPreferenceNotificationEvent`](../../../doc/models/user-preference-notification-event.md) |

## UserActionNotificationEvent

### Initialization Code

#### Example

```ts
const value: UserNotificationEventBody = {
  userActionNotificationEventType: 'user.action',
};
```

## UserStatusNotificationEvent

### Initialization Code

#### Example

```ts
const value: UserNotificationEventBody = {
  userStatusNotificationEventType: 'user.status',
};
```

## UserPreferenceNotificationEvent

### Initialization Code

#### Example

```ts
const value: UserNotificationEventBody = {
  userPreferenceNotificationEventType: 'user.preference',
};
```

