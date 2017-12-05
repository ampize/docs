---
$title@: Push Notifications
$order: 15
isDraft: 1
$date: 2017-12-05
$dates:
  published: 2017-12-05
description: >

href: /docs/guides/notifications
---

Notifications and subscribers are website-specific and require a published website. 
In order to configure push notifications on your website simply access it in the Site Builder and open the Site Settings from the left menu. All you need to do is switch on "Enable subscriptions to push notifications" in the "Notifications" tab. Optionally you can choose a "Notification default icon" which will be added to all notifications you send to subscribers from that website. One you save the changes don't forget to publish your website. Please note that these changes have no effect on the preview : only the live version is affected once the website is published.

Your website now contains a notification subscription icon which will appear in the bottom right corner of any compatible browser. Your users can use this icon to subscribe and unsubscibe from push notifications from your website.

The left menu in the Site Builder now contains a "Push notifications" tool which allows you to send insnat and scheduled notifications to your subscribers as well as view stats for sent notifications. These stats are specific toa aprticular notification. If you wish to view general information such as the number of subsribed users you can find those in the Usage Statistics for that particular website. 

## Instant notifications

The first tab of the "Push notifications" tool handles instant notifications. It displays a list of sent instant notifications and allows you to view their stats. To send a new notification simply click "Add". This will display a form where you can configure and send your Notification. The URL field is optional and represents the url that the browser will open when a user clicks on the notification.

Once you click "Send notification" it will be sent to all users subrcibed to push notifications on your website and will be added to the list so that you can view its stats. The stats show delivery and conversion (how many users clicked on the notification) rates and can be refreshed in order to follow results.

## Scheduled notifications

The second tab of the "Push notifications" tool handles scheduled notifications. The displayed list no longer handles stats directly but shows all currently configured scheduled notifications and allows you to edit or delete them. As a scheduled notification can be repeated you can view the history of sent notifications as well as their individual stats. The "Add" form for scheduled notifications is far more powerfull than the one for instant notifications. The contents of a scheduled notification depend on its type. The manual ones have the same settings as instant notifications whereas the automatic ones draw their title, text and URL directly from a data query. All scheduled notifications have a "send at" as well as a "repeat" setting which will resend every n hours. The repeat setting is most usefull for automatic scheduled notifications as the results of the query change and thus a new content is sent via this notification each time. Keep in mind that the result of the query must change between notifications (either by crawl or updates in your database or API) as the same notification could be sent twice so please configure the repeat delay accordingly. The query itself is accompanied by a detail page setting and follows the same mechanic as a list page to detail page configuration. As a result the detail page must contain an "Detail" component with the correspondint detail query. In this case the the first result of the list query will be used so be sure to use sorting (descendant sort on publication date for example). The fields which will be used for the title and text fields are the same as the ones used for the heading and description in JSON-LD. 
