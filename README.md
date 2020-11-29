# NetatmoWeatherStation
LabVIEW project to retrieve data from Netatmo Weather Station.

We call the Weather API provided by Netatmo. The documentation is avialable ![here](https://dev.netatmo.com/apidocumentation/weather#product-details). 

## Usage

1- You need to create an application from [NETATMO Connect: My apps](https://dev.netatmo.com/apps/createanapp#form).

![Application Form](/images/application-form.png | width=100)

2- You will need to generate the <i>client ID</i> and <i>client Secret</i> (Save both values as they are mandatory for authentication.) and set the <i>redirect URI</i> to http://127.0.0.1:8001/OAuth/Redirect.

![Application Technical Parameters](/images/application-technical-parameters.png | width=100)

3- Open the Netatmo Weather Station.lvproj with LabVIEW 2020 or higher. 

4- You need to update the <i>client_id</i> and the <i>client_secret</i>, savec in step 2-, in the Init Globals.vi.

5- Start the Web Server by right clicking on “OAuth” in the Project Window and select <b>Application Web Server>>Start (Debug Server)</b>.

![Start Web Server From LabVIEW Project Explorer](/images/start-web-server.png | width=100)

6- Open and execute the Main VI. This VI performs OAuth2 Authorization and uses the getstationdata request to retrieve data.

OAuth2 authetification steps:
	- Redirect the user to Netatmo OAuth2 dialog
	- The user is prompted to authorize your application
	- The user is redirected to your application
	- Retrieve the access token with the code