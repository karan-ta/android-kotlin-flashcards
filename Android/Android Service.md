
---
tags: review
---

what is a service
?
Once started, a service might continue running for some time, even after the user switches to another application.
<!--SR:!2023-09-14,24,270-->

Give example of Foreground service
?
an audio app would use a foreground service to play an audio track.

Can service be started and bound 
?
, your service can work both ways—it can be started (to run indefinitely) and also allow binding.

In a service, which callback method we have to implement to allow components to start it 
?
onStartCommand

In a service , which callback method we have to implement to allow binding
?
onBind()

what is background service
?
A background service performs an operation that isn't directly noticed by the user

Give example of background service
?
if an app used a service to compact its storage, that would usually be a background service.

when is a service bound 
?
A service is _bound_ when an application component binds to it by calling bindService

What is a bound service
?
A bound service offers a client - server interface that allows components to interact with the 
service , send requests , receive results , do so across processes with interprocess communication.

when is the bound service destroyed
?
A bound service runs only as long as another application component is bound to it.
Multiple components can bind to the service at once.
when all bound components unbind , the service is destroyed.

How to allow components to start your service
?
implement onStartCommand method in service.
component will call startService method and onStartCommand will be called

How to allow component to bind to your service
?
Implement onBind method in service.
Component calls bindService method and onBind method is called.

How can any application component use the Service 
?
by starting it with an Intent 

How to block access of service from other applications
?
By declaring the service as private in the manifest file.

BY default, which thread does the service run in 
?
The service runs in the applications Main thread by default.

what to do if service performs blocking or intensive operations
?
create a new thread within the service if it performs intensive or blocking operations.
<!--SR:!2023-08-25,4,270-->

How to create a Service
?
To create a service, you must create a subclass of Service or use one of its existing subclasses

Which callback methods should we override when we create a service
?
onStartCommand, onBind, onCreate, onDestroy

if we implement onStartCommand which other method should we call 
?
call stopSelf or stopService to stop the service

when does the system invoke onStartCommand
?
The system invokes this method by calling `[startService()](https://developer.android.com/reference/android/content/Context#startService(android.content.Intent))` when another component (such as an activity) requests that the service be started.

when does system invoke onBind
?
The system invokes this method by calling `[bindService()](https://developer.android.com/reference/android/content/Context#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int))` when another component wants to bind with the service (such as to perform RPC). In your implementation of this method, you must provide an interface that clients use to communicate with the service by returning an `[IBinder](https://developer.android.com/reference/android/os/IBinder)`

when do we dont need to implement onStartCommand
?
If you only want to provide binding, you don't need to implement this method.

when to implement onBind method
?
You must always implement this method; however, if you don't want to allow binding, you should return null.

when is a service rarely killed
?
when it is declared to run in the foreground

when is service highly susceptible to being killed
?
If the service is started and is long-running, the system lowers its position in the list of background tasks over time, and the service becomes highly susceptible to killing

how to add service in manifest 
?
service android:name=".ExampleService"
<!--SR:!2023-08-25,4,270-->

Which intent to use to start a service 
?
To ensure that your app is secure, always use an explicit intent when starting a `[Service](https://developer.android.com/reference/android/app/Service)` and don't declare intent filters for your services. Using an implicit intent to start a service is a security hazard because you cannot be certain of the service that responds to the intent, and the user cannot see which service starts. Beginning with Android 5.0 (API level 21), the system throws an exception if you call `[bindService()](https://developer.android.com/reference/android/content/Context#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int))` with an implicit intent.

How to ensure that service is only accessed by our app 
?
You can ensure that your service is available to only your app by including the [`android:exported`](https://developer.android.com/guide/topics/manifest/service-element#exported) attribute and setting it to `false`

Why to add android:description to service
?
Users can see what services are running on their device. If they see a service that they don't recognize or trust, they can stop the service. In order to avoid having your service stopped accidentally by users, you need to add the [`android:description`](https://developer.android.com/guide/topics/manifest/service-element#desc) attribute to the [`<service>`](https://developer.android.com/guide/topics/manifest/service-element) element in your app manifest. In the description, provide a short sentence explaining what the service does and what benefits it provides.

How does service receive Intent
?
An application component such as an activity can start the service by calling `[startService()](https://developer.android.com/reference/android/content/Context#startService(android.content.Intent))` and passing an `[Intent](https://developer.android.com/reference/android/content/Intent)` that specifies the service and includes any data for the service to use. The service receives this `[Intent](https://developer.android.com/reference/android/content/Intent)` in the `[onStartCommand()](https://developer.android.com/reference/android/app/Service#onStartCommand(android.content.Intent,%20int,%20int))` method.

Why to start a new thread inside the service 
?
A service runs in the same process as the application in which it is declared and in the main thread of that application by default. If your service performs intensive or blocking operations while the user interacts with an activity from the same application, the service slows down activity performance. To avoid impacting application performance, start a new thread inside the service.

why background limitations are imposed on service 
?
Whenever an app runs in the background, it consumes some of the device's limited resources, like RAM. This can result in an impaired user experience, especially if the user is using a resource-intensive app, such as playing a game or watching video

what are background service limitations
?
While an app is idle, there are limits to its use of background services.

How to solve background service limitations
?
Use Job Scheduler jobs

which android version placed background service limitations
?
android 8 api 26
With Android 8.0, there is a complication; the system doesn't allow a background app to create a background service
 For this reason, Android 8.0 introduces the new method startForegroundService() to start a new service in the foreground.

Why Broadcast limitations were placed
?
If an app registers to receive broadcasts, the app's receiver consumes resources every time the broadcast is sent. This can cause problems if too many apps register to receive broadcasts based on system events; a system event that triggers a broadcast can cause all of those apps to consume resources in rapid succession, impairing the user experience.

which android version placed broadcast limitations
?
To mitigate this problem, Android 7.0 (API level 24) placed limitations on broadcasts, as described in Background Optimization.
<!--SR:!2023-08-24,1,210-->

what is an implicit broadcast
?
An implicit broadcast is a broadcast that does not target that app specifically.
<!--SR:!2023-09-01,9,250-->

which apps can no longer register broadcast receivers for implicit broadcast
?
Apps that target Android 8.0 or higher can no longer register broadcast receivers for implicit broadcasts in their manifest.
Apps can continue to register for explicit broadcasts in their manifests.

How to register a receiver for any broadcast
?
Apps can use Context.registerReceiver() at runtime to register a receiver for any broadcast, whether implicit or explicit.

How does foreground service affect app lifecycle
?
Consider a case in which a foreground service starts while an activity from the app is visible to the user. The user subsequently navigates away from the app and returns to the home screen. In such cases, the app is running in the foreground until the service's lifecycle ends.

from android 12 - how to launch foreground services
?
Android 12 restricts launching foreground services from the background. For most cases, you should use setForeground() from WorkManager rather than handle foreground services yourself. This allows WorkManager to manage the lifecycle of the foregound service, ensuring efficiency.

How to create a bound service
?
To create a bound service, you must define the interface that specifies how a client can communicate with the service. This interface between the service and a client must be an implementation of `[IBinder](https://developer.android.com/reference/android/os/IBinder)` and is what your service must return from the `[onBind()](https://developer.android.com/reference/android/app/Service#onBind(android.content.Intent))` callback method. After the client receives the `[IBinder](https://developer.android.com/reference/android/os/IBinder)`, it can begin interacting with the service through that interface.

how to stop bound service
?
The service is created when another component (a client) calls `[bindService()](https://developer.android.com/reference/android/content/Context#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int))`. The client then communicates with the service through an `[IBinder](https://developer.android.com/reference/android/os/IBinder)` interface. The client can close the connection by calling `[unbindService()](https://developer.android.com/reference/android/content/Context#unbindService(android.content.ServiceConnection))`. Multiple clients can bind to the same service and when all of them unbind, the system destroys the service. The service does _not_ need to stop itself.

With Api level 21 , how can you start a service.
?
With JobScheduler
<!--SR:!2023-08-31,8,250-->

what is a broadcast
?
A broadcast is a message that any app can receive. The system delivers various broadcasts for system events, such as when the system boots up or the device starts charging.

how to deliver a broadcast to other apps 
?
You can deliver a broadcast to other apps by passing an Intent to sendBroadcast() or sendOrderedBroadcast().












   <service android:name=".ExampleService" />






