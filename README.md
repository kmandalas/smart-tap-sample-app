# Google Wallet Smart Tap sample app

The Smart Tap sample app is a simple Android application that invokes the
[`get smart tap data`](https://developers.google.com/wallet/smart-tap/reference/apdu-commands/get-data)
flow with the Smart Tap 2.1 protocol. The app reads the
`smartTapRedemptionValue` property of a Google Wallet pass object stored on an
Android-powered device. This includes the cryptographic operations needed to
authenticate the terminal and decrypt the payload.

For more information on the different data flows, see
[Data flow](https://developers.google.com/wallet/smart-tap/guides/implementation/data-flow).

## Prerequisites

You will need two different Android-powered devices to test the sample app. The
devices are listed below for reference.

* **Terminal device:** On this device, you will install the sample app
* **User device:** On this device, you will add a sample pass to the Google
  Wallet app
  * Make sure the device supports NFC (see this
    [support article](https://support.google.com/wallet/answer/12200245?visit_id=638060357507089968-2256101247&rd=1)
    for additional troubleshooting tips)

You will also need the latest version of
[Android Studio](https://developer.android.com/studio) on your local
workstation.

## About the sample app

This application contains the needed configuration to retrieve the demo pass
added to the user device:

* Private key
* Key version
* Collector ID

## User device setup

On the user device, open the following link to add the demo loyalty pass to the
Google Wallet app:

[Demo pass **Add to Google Wallet** link](https://pay.google.com/gp/v/save/eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdWQiOiJnb29nbGUiLCJvcmlnaW5zIjpbImh0dHA6Ly9sb2NhbGhvc3Q6ODA4MCJdLCJpc3MiOiJnb29nbGUtcGF5LWZvci1wYXNzZXMtZ3RlY2hAcGF5LXBhc3Nlcy1zbWFydC10YXAtc2FtcGxlLmlhbS5nc2VydmljZWFjY291bnQuY29tIiwiaWF0IjoxNTI5OTU2MDcwLCJ0eXAiOiJzYXZldG9hbmRyb2lkcGF5IiwicGF5bG9hZCI6eyJsb3lhbHR5T2JqZWN0cyI6W3siY2xhc3NJZCI6IjMyNjUzMjAxMTE2NDE5NTYxODMuMDYxOV9nb29nbGVEZW1vVGVzdCIsInN0YXRlIjoiYWN0aXZlIiwiaWQiOiIzMjY1MzIwMTExNjQxOTU2MTgzLjA2MTlfZ29vZ2xlRGVtb1Rlc3Qtb2JqMDEifV19fQ.MjUBdBtGyQwcE3xI-q6tVNBiApZppLMp0Op0XvB-c31Ri-JttJCzGXZvURNvKFDGXTNQQDqVBgQziuBMR_ZL0_lp7q8B5nwfSR32I0Kr220n3CezAsikaM5rKVf83UXT9fvqagnRn0QVVuS7fyLLc9nBDxRhRnkqEz2dQPgrNZ1u2AEJBPSoM6sLTeHssOWUMp7dgW6REJg7NUcczXJgLSOpAmD08G14q1qfS5T4Jb4knwPeIMnggNMjHcSBmz0z6W4DGD5Ld16nKOty4TvoDh4EevEJF7U7UQcOwIpozIXRVKs8rlqEXMObGsrk4hPM-I2p6H4DBrVcpyG8HD6Iug)

## Run the sample app

1. Clone this repository
2. Open Android Studio and import the repository folder
3. Connect your terminal device for debugging (for instructions on how to do so, 
   see the [Android Studio documentation](https://developer.android.com/studio/run/device))
5. Run the sample app in debugging mode on the terminal device
6. Gently tap the user device to the terminal device
   * The tap location may depend on the location of the NFC antenna on each
    device, so you may need to try tapping in several different locations

Once the devices connect via NFC, the terminal device will display the flow of
Smart Tap commands and responses, as well as the decrypted payload (`2018`).
This is the value stored in the pass object's `smartTapRedemptionValue`
property. The user device will show that the pass was successfully transmitted
to the terminal device.

**Note:** If you would like to inspect the flow further, set several breakpoints
at different locations in the sample terminal app and restart debugging.

### Support

Feel free to
[submit an issue](https://github.com/google-pay/smart-tap-sample-app/issues/new)
to this repository with any questions.
