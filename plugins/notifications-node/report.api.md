## API Report File for "@backstage/plugin-notifications-node"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
import { AuthService } from '@backstage/backend-plugin-api';
import { DiscoveryService } from '@backstage/backend-plugin-api';
import { ExtensionPoint } from '@backstage/backend-plugin-api';
import { Notification as Notification_2 } from '@backstage/plugin-notifications-common';
import { NotificationPayload } from '@backstage/plugin-notifications-common';
import { NotificationProcessorFilters as NotificationProcessorFilters_2 } from '@backstage/plugin-notifications-common';
import { ServiceRef } from '@backstage/backend-plugin-api';

// @public (undocumented)
export class DefaultNotificationService implements NotificationService {
  // (undocumented)
  static create(
    options: NotificationServiceOptions,
  ): DefaultNotificationService;
  // (undocumented)
  send(notification: NotificationSendOptions): Promise<void>;
}

// @public
export interface NotificationProcessor {
  getName(): string;
  getNotificationFilters?(): NotificationProcessorFilters;
  postProcess?(
    notification: Notification_2,
    options: NotificationSendOptions,
  ): Promise<void>;
  preProcess?(
    notification: Notification_2,
    options: NotificationSendOptions,
  ): Promise<Notification_2>;
  processOptions?(
    options: NotificationSendOptions,
  ): Promise<NotificationSendOptions>;
}

// @public @deprecated (undocumented)
export type NotificationProcessorFilters = NotificationProcessorFilters_2;

// @public (undocumented)
export type NotificationRecipients =
  | {
      type: 'entity';
      entityRef: string | string[];
      excludeEntityRef?: string | string[];
    }
  | {
      type: 'broadcast';
    };

// @public (undocumented)
export type NotificationSendOptions = {
  recipients: NotificationRecipients;
  payload: NotificationPayload;
};

// @public (undocumented)
export interface NotificationService {
  // (undocumented)
  send(options: NotificationSendOptions): Promise<void>;
}

// @public (undocumented)
export const notificationService: ServiceRef<
  NotificationService,
  'plugin',
  'singleton'
>;

// @public (undocumented)
export type NotificationServiceOptions = {
  auth: AuthService;
  discovery: DiscoveryService;
};

// @public (undocumented)
export interface NotificationsProcessingExtensionPoint {
  // (undocumented)
  addProcessor(
    ...processors: Array<NotificationProcessor | Array<NotificationProcessor>>
  ): void;
}

// @public (undocumented)
export const notificationsProcessingExtensionPoint: ExtensionPoint<NotificationsProcessingExtensionPoint>;

// Warnings were encountered during analysis:
//
// src/extensions.d.ts:73:1 - (ae-undocumented) Missing documentation for "NotificationsProcessingExtensionPoint".
// src/extensions.d.ts:74:5 - (ae-undocumented) Missing documentation for "addProcessor".
// src/extensions.d.ts:79:22 - (ae-undocumented) Missing documentation for "notificationsProcessingExtensionPoint".
// src/extensions.d.ts:84:1 - (ae-undocumented) Missing documentation for "NotificationProcessorFilters".
// src/lib.d.ts:3:22 - (ae-undocumented) Missing documentation for "notificationService".
// src/service/DefaultNotificationService.d.ts:5:1 - (ae-undocumented) Missing documentation for "NotificationServiceOptions".
// src/service/DefaultNotificationService.d.ts:10:1 - (ae-undocumented) Missing documentation for "NotificationRecipients".
// src/service/DefaultNotificationService.d.ts:26:1 - (ae-undocumented) Missing documentation for "NotificationSendOptions".
// src/service/DefaultNotificationService.d.ts:31:1 - (ae-undocumented) Missing documentation for "DefaultNotificationService".
// src/service/DefaultNotificationService.d.ts:35:5 - (ae-undocumented) Missing documentation for "create".
// src/service/DefaultNotificationService.d.ts:36:5 - (ae-undocumented) Missing documentation for "send".
// src/service/NotificationService.d.ts:3:1 - (ae-undocumented) Missing documentation for "NotificationService".
// src/service/NotificationService.d.ts:4:5 - (ae-undocumented) Missing documentation for "send".
```