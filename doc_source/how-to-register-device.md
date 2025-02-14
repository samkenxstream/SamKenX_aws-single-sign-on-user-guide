# Register an MFA device<a name="how-to-register-device"></a>

Use the following procedure to set up a new MFA device for access by a specific user in the IAM Identity Center console\. You must have physical access to the user's MFA device in order to register it\. For example, you might configure MFA for a user who will use an MFA device running on a smartphone\. In that case, you must have the smartphone available in order to finish the wizard\. For this reason, you might want to let users configure and manage their own MFA devices\. For details on how to set this up, see [Allow users to register their own MFA devices](how-to-allow-user-registration.md)\.

**To register an MFA device**

1. Open the [IAM Identity Center console](https://console.aws.amazon.com/singlesignon)\.

1. In the left navigation pane, choose **Users**\. Choose a user in the list\. Don't select the checkbox next to the user for this step\.

1. On the user details page, choose the **MFA devices** tab, and then choose **Register MFA device**\.

1. On the **Register MFA device** page, select one of the following MFA device types, and follow the instructions:
   + **Authenticator app**

     1. On the **Set up the authenticator app** page, IAM Identity Center displays configuration information for the new MFA device, including a QR code graphic\. The graphic is a representation of the secret key that is available for manual entry on devices that do not support QR codes\.

     1. Using the physical MFA device, do the following:

        1. Open a compatible MFA authenticator app\. For a list of tested apps that you can use with MFA devices, see [Authenticator apps](mfa-types-apps.md)\. If the MFA app supports multiple accounts \(multiple MFA devices\), choose the option to create a new account \(a new MFA device\)\.

        1. Determine whether the MFA app supports QR codes, and then do one of the following on the **Set up the authenticator app** page:

           1. Choose **Show QR code**, and then use the app to scan the QR code\. For example, you might choose the camera icon or choose an option similar to **Scan code**\. Then use the device's camera to scan the code\.

           1. Choose **show secret key**, and then type that secret key into your MFA app\.
**Important**  
When you configure an MFA device for IAM Identity Center, we recommend that you save a copy of the QR code or secret key *in a secure place*\. This can help if the assigned user loses the phone or has to reinstall the MFA authenticator app\. If either of those things happen, you can quickly reconfigure the app to use the same MFA configuration\. This avoids the need to create a new MFA device in IAM Identity Center for the user\.

     1. On the **Set up the authenticator app** page, under **Authenticator code**, type the one\-time password that currently appears on the physical MFA device\.
**Important**  
Submit your request immediately after generating the code\. If you generate the code and then wait too long to submit the request, the MFA device is successfully associated with the user\. But the MFA device is out of sync\. This happens because time\-based one\-time passwords \(TOTP\) expire after a short period of time\. If this happens, you can resync the device\.

     1. Choose **Assign MFA**\. The MFA device can now start generating one\-time passwords and is now ready for use with AWS\.
   + **Security key**

     1. On the **Register your user's security key** page, follow the instructions given to you by your browser or platform\.
**Note**  
The experience here varies based on the different operating systems and browsers, so please follow the instructions displayed by your browser or platform\. After your user's device has been successfully registered, you will be given the option to associate a friendly display name to your user's newly enrolled device\. If you want to change this, choose **Rename**, enter the new name, and then choose **Save**\. If you have enabled the option to allow users to manage their own devices, the user will see this friendly name in the AWS access portal\.