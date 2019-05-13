# How to add a new notification

### Step 1

- In directory `/v2/features/Dashboard/NotificationsPanel/components/`, create a new component with the layout for the new notification. 

- If needed, use the NotificationWrapper component, which provides the basic layout for existing notifications (`/v2/features/Dashboard/NotificationsPanel/components/NotificationWrapper.tsx`)

### Step 2

- Open `/v2/providers/NotificationsProvider/constants.ts` and Import the layout component that was created in step one.

- In the `NotificationTemplates` object create a new entry with a name for your notification (e.g. `newNotification: "new-notification"`)

- In the `notificationsConfigs` object create a new configuration for your notification.

### Configuration example:

```
[NotificationTemplates.newNotification]: {
 analyticsEvent: 'Description of new notification',
 layout: NewNotificationBodyLayout,
 repeatInterval: 60,
 condition: newNotificationCheck
}
```

### List of parameters to use in the notification configuration:

**`analyticsEvent` (required)**
- Name of the event that will be tracked in the analytics when the notification is displayed

**`layout` (required)**
- The layout of the notification body

**`showOneTime` (optional, false by default) **
- If true, the notification will be automatically dismissed after the user leaves or refreshes the page. If false, the notification will be displayed until it is dismissed.

**`dismissOnOverwrite` (optional, false by default)**
- If true, the notification will be automatically dismissed when another notification is displayed over it

**`repeatInterval` (optional, not defined by default)**
- Time in seconds. If this is set to 60, the notification will be displayed 60 seconds after the notification was last dismissed.

**`condition` (optional, not defined by default)**
- Any function that returns true/false. If condition is false, the notification won't be displayed.
- Note: Condition functions for all notifications should be added to `/v2/providers/NotificationsProvider/helpers.ts`

**`dismissForever` (optional, false by default)**
- If set to true, this notification will never be displayed again after it is dismissed (even if displayNotification is called).





# How to display a notification

Notifications can be added using the `displayNotification()` function that is part of the `NotificationsContext`.

### `displayNotification()` takes two arguments:

1. **`templateName` (required)**
- template name of your notification (NotificationTemplates in "/v2/providers/NotificationsProvider/constants.ts")

2. **`templateData` (optional)**
- An object that contains any additional data for your notification. Values in the templateData will be automatically passed to your notification layout component as props.
- Note: templateData is saved in local storage, therefore no sensitive info should be stored here.

### Example:

```
<NotificationsContext.Consumer>
      {({ displayNotification }) => (
          <button
            onClick={() => {
              displayNotification(NotificationTemplates.newNotification, {publicAddress:"0x32nfniw30fdsfsefesfs"});
            }}
          >
      )}
</NotificationsContext.Consumer>
```

### Using `displayNotification()` with repeating notifications:

- When `displayNotification()` is called for the first time, the repeating notification will be displayed instantly.
- After that, the notification will be only triggered after the set period of time (even if `displayNotification` is called in the meantime).












