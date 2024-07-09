# Notes

To add custom sound to notification in ios
 1.open ios folder in xcode form vscode . create a folder inside Runner named Resources then past abcd.aiff sound file in that Resources folder continue . rerun the app
2.optional => abcd.aiff sound file to flutterproject/ios folder and open info.plist, add- 
      <!-- //Custom Sound -->
	<key>UIAppFonts</key>
	<array>
		<string>slow_spring_board.aiff</string>
	</array>

3.and in dart code
 const DarwinNotificationDetails darwinNotificationDetails =
        DarwinNotificationDetails(
      sound: 'slow_spring_board.aiff',
    );

      final NotificationDetails notificationDetails = NotificationDetails(
      android: androidNotificationDetails,
      iOS: darwinNotificationDetails,
      macOS: darwinNotificationDetails,
    );
    await flutterLocalNotificationsPlugin.show(
      id++,
      'custom sound notification title',
      'custom sound notification body',
      notificationDetails,
    );
