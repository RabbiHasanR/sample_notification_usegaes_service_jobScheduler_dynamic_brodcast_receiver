# Title 
sample_notification_usegaes_service_jobScheduler_dynamic_brodcast_receiver
# Description
This is a sample hydration reminder app.This app provide otification after 15 minute while mobile charging.Here i use intent service for foreground task.and use FirebaseJobSheduler for provide notification after 15 minute while mobile charging even app is not running.Also use Dynamic broadcast receiver for know when mobile charging or not.
# Usages
### Permissions in mainfest.xml
````````
<uses-permission android:name="android.permission.VIBRATE" />
````````
### create service in mainfest.xml
````````
 <!--This is required for immediate syncs -->
        <service
            android:name=".sync.WaterReminderIntentService"
            android:exported="false"/>

        <!-- This is the Service declaration used in conjunction with FirebaseJobDispatcher -->
        <service
            android:name=".sync.WaterReminderFirebaseJobService"
            android:exported="false">
            <intent-filter>
                <action android:name="com.firebase.jobdispatcher.ACTION_EXECUTE"/>
            </intent-filter>
        </service>
````````
### build.gradle(app)
````````
implementation 'com.firebase:firebase-jobdispatcher:0.5.2'
````````
