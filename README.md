# Experiment 6: Phone Dialer Application with Call and Save Contact

## Aim
To design and develop an Android application that functions like a phone dialer, containing a phone number field with CALL and SAVE buttons. On pressing the CALL button, the application must place a call to the entered phone number, and on pressing the SAVE button, it must save the entered name and phone number to the device's phone contacts.

## Objectives
- To design a simple dialer UI using EditText/OutlinedTextField and Button widgets.
- To place a phone call programmatically using Intent.ACTION_CALL.
- To insert a new contact into the device's Contacts Provider using ContentProviderOperation.
- To request and handle dangerous runtime permissions (CALL_PHONE, WRITE_CONTACTS) using the Activity Result API.
- To validate user input before making a call or saving a contact.
- To handle exceptions that may occur during a call or a contact-save operation.

## Procedure / Algorithm
1. Create a new Android project using Kotlin and Jetpack Compose.
2. Declare the CALL_PHONE, WRITE_CONTACTS and READ_CONTACTS permissions in AndroidManifest.xml.
3. Design the UI in MainActivity.kt with a Name field, a Phone Number field, a CALL button and a SAVE button.
4. Register two permission launchers using registerForActivityResult(ActivityResultContracts.RequestPermission()) — one for CALL_PHONE and one for WRITE_CONTACTS.
5. On clicking CALL, validate that the phone number field is not empty.
6. Check whether the CALL_PHONE permission is already granted; if not, request it at runtime.
7. Once granted, place the call using an Intent with action Intent.ACTION_CALL and data Uri.parse("tel:<number>").
8. On clicking SAVE, validate that both the name and phone number fields are not empty.
9. Check whether the WRITE_CONTACTS permission is already granted; if not, request it at runtime.
10. Once granted, build a list of ContentProviderOperation objects to insert a new raw contact, its display name, and its phone number, then apply them in a batch to the ContactsContract provider.
11. Display a Toast message confirming success or describing the failure for both the CALL and SAVE actions.
12. Run the application on an emulator/device, grant the requested permissions, and verify that CALL dials the entered number and SAVE adds the entered name and number to Contacts.

## Source Code Files
- `app/src/main/AndroidManifest.xml`
- `app/src/main/java/com/example/phonedialer/MainActivity.kt`

## Result
Thus, an Android application resembling a phone dialer with CALL and SAVE buttons was successfully designed and implemented — pressing CALL places a call to the entered number, and pressing SAVE stores the entered name and phone number in the device's contacts.
