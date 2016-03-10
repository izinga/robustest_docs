Advanced Recording Concepts
===========================

*Recording a test case involving OTP verification*

In some test cases, the device receives an OTP from the server as a text message or as an email. The user needs to input the secret number into a text field for verification. RobusTest has libraries to support such scenarios and following is a brief idea on how such a test case can be recorded.

Recording a test case with OTP received as text message

1. Proceed to record the test case
2. Once you receive the OTP message on your phone as a text message, pause the recording.
3. Read the message to find the OTP
4. Return to the application sceen
5. Enter the OTP that you have read from the Text message in the OTP text field
6. Proceed to record the rest of the test case
7. Once the test case recording it complete, save the test and exit the test session
8. Go to the Test Script tab in the test details page
9. Look for the step where you requested for an OTP - this is most probably a button click
10. Right below the step where the request to get an OTP is made, paste the following piece of code ::

	#wait for 30 seconds to get SMS. Change it according to your app
	time.sleep(30)
	#invoke the function to get OTP from the device
	#provide the sender name as it appears on the device and a complete sample message
	otp = self.getOTPFromSMS(‘<SENDER>’, '<SAMPLE MESSAGE>')

e.g. If your server sends an OTP message from **TD-SAMPLEAPP** and the message sent is "Thank you for signing up. Your OTP is 234567" then your invocation statement should look like ::

	otp = self.getOTPFromSMS('TD-SAMPLEAPP', 'Thank you for signing up. Your OTP is 234567')

The value of the OTP gets captured in the variable "otp"

In the next statement in the code, where the OTP value is entered in the text field, replace the variable used to enter OTP with the otp variable.

e.g. The statement to enter a value in the text field may look like ::

    Type_123456_in_EditText_vericode1_ = self.getElement("Type_123456_in_EditText_vericode1_", "EditText com.flipkart.android:id/vericod")
    Type_123456_in_EditText_vericode1_.send_keys(self.userData["EditText com.flipkart.android:id/vericod"])

After replacing it with the variable "otp", the statement looks like ::

    Type_123456_in_EditText_vericode1_ = self.getElement("Type_123456_in_EditText_vericode1_", "EditText com.flipkart.android:id/vericod")
    Type_123456_in_EditText_vericode1_.send_keys(otp)
