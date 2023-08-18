

---
tags: review
---

what is an Intent
?
 messaging object to request action from another app component.

what is difference between explicit intent and implicit intent
?
Explicit intents specify which application will satisfy the intent, by supplying either the target app's package name or a fully-qualified component class name.
Implicit intents do not name a specific component, but instead declare a general action to perform, which allows a component from another app to handle it. For example, if you want to show the user a location on a map, you can use an implicit intent to request that another capable app show a specified location on a map.

What happens when you use an implicit Intent
?
When you use an implicit intent, the Android system finds the appropriate component to start by comparing the contents of the intent to the _intent filters_ declared in the [manifest file](https://developer.android.com/guide/topics/manifest/manifest-intro) of other apps on the device. If the intent matches an intent filter, the system starts that component and delivers it the `[Intent](https://developer.android.com/reference/android/content/Intent)` object. If multiple intent filters are compatible, the system displays a dialog so the user can pick which app to use.

Why we should use explicit intent to start service
?
To ensure that your app is secure, always use an explicit intent when starting a `[Service](https://developer.android.com/reference/android/app/Service)` and do not declare intent filters for your services. Using an implicit intent to start a service is a security hazard because you can't be certain what service will respond to the intent, and the user can't see which service starts. Beginning with Android 5.0 (API level 21), the system throws an exception if you call `[bindService()](https://developer.android.com/reference/android/content/Context#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int))` with an implicit intent.

What does the Intent object contain
?
An `[Intent](https://developer.android.com/reference/android/content/Intent)` object carries information that the Android system uses to determine which component to start (such as the exact component name or component category that should receive the intent), plus information that the recipient component uses in order to properly perform the action (such as the action to take and the data to act upon).
The primary information contained in an `[Intent](https://developer.android.com/reference/android/content/Intent)` is the following:

which are the primary information contained in intent
?
component name
action
data
category
extras
flags

if component name is not specified in intent , then how does system decide which intent to start
?
by action , data , category

How to specify action for intent
?
You can specify the action for an intent with setAction() or with an Intent constructor.

give examples of Intent Actions
?
ACTION_VIEW
ACTION_SEND - to share data 

How to specify data for Intent
?
To set only the data URI, call setData(). To set only the MIME type, call setType(). If necessary, you can set both explicitly with setDataAndType().
Caution: If you want to set both the URI and MIME type, don't call setData() and setType() because they each nullify the value of the other. Always use setDataAndType() to set both URI and MIME type.

What are Extras in Intent
?
Key-value pairs that carry additional information required to accomplish the requested action. Just as some actions use particular kinds of data URIs, some actions also use particular extras.

Why to not use Parcelable or Serializable data when sending an Intent that you expect another app to receive
?
**Caution**: Do not use `[Parcelable](https://developer.android.com/reference/android/os/Parcelable)` or `[Serializable](https://developer.android.com/reference/java/io/Serializable)` data when sending an intent that you expect another app to receive. If an app attempts to access data in a `[Bundle](https://developer.android.com/reference/android/os/Bundle)` object but does not have access to the parceled or serialized class, the system raises a `[RuntimeException](https://developer.android.com/reference/java/lang/RuntimeException)`.

what are flags in Intent
?
Flags are defined in the `[Intent](https://developer.android.com/reference/android/content/Intent)` class that function as metadata for the intent.

Give example of explicit Intent
?
val downloadIntent = Intent(this, DownloadService_colonclass.java).apply {    data = `[Uri.parse](https://developer.android.com/reference/android/net/Uri#parse(java.lang.String))`(fileUrl)  
}  
startService(downloadIntent)

Give example of implicit Intent
?
// Create the text message with a string.  
val sendIntent = Intent().apply {    action = Intent.ACTION_SEND  
    putExtra(Intent.EXTRA_TEXT, textMessage)    type = "text/plain"  
}  
  // Try to invoke the intent.  
try {    startActivity(sendIntent)  
} catch (e: ActivityNotFoundException) {    // Define what your app should do if no activity can handle the intent.  
}
When `[startActivity()](https://developer.android.com/reference/android/content/Context#startActivity(android.content.Intent))` is called, the system examines all of the installed apps to determine which ones can handle this kind of intent (an intent with the `[ACTION_SEND](https://developer.android.com/reference/android/content/Intent#ACTION_SEND)` action and that carries "text/plain" data). If there's only one app that can handle it, that app opens immediately and is given the intent. If no other apps can handle it, your app can catch the [`ActivityNotFoundException`](https://developer.android.com/reference/android/content/ActivityNotFoundException) that occurs. If multiple activities accept the intent, the system displays a dialog such as the one shown in Figure 2, so the user can pick which app to use.

what is chooser dialog
?
user cannot choose default app for the action and has to choose an intent every time.

How to create chooser
?
val chooser colon  Intent = Intent.createChooser(sendIntent, title)  
  // Verify the original intent will resolve to at least one activity  
if (sendIntent.resolveActivity(packageManager) != null) {    startActivity(chooser)  
}

What is nested Intent
?
Intent that is passed as an extra in another Intent

When does a StrictMode violation occur
?
1. Your app unparcels a nested intent from the extras of a delivered intent.
2. Your app immediately starts an [app component](https://developer.android.com/guide/components/fundamentals#Components) using that nested intent, such as passing the intent into [`startActivity()`](https://developer.android.com/reference/android/content/Context#startActivity(android.content.Intent)), [`startService()`](https://developer.android.com/reference/android/content/Context#startService(android.content.Intent)), or [`bindService()`](https://developer.android.com/reference/android/content/Context#bindService(android.content.Intent,%20android.content.ServiceConnection,%20int)).
3. To check for unsafe intent launches in your app, call [`detectUnsafeIntentLaunch()`](https://developer.android.com/reference/android/os/StrictMode.VmPolicy.Builder#detectUnsafeIntentLaunch())

How to use intents more responsibly
?
**Copy only the essential extras within intents, and perform any necessary sanitation and validation.**
**Don't export your app's components unnecessarily.**
**Use a [`PendingIntent`](https://developer.android.com/reference/android/app/PendingIntent) instead of a nested intent**








