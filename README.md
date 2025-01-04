# b00gle
A TypoSquatting Minefield


b00gle is a proof-of-concept tool designed to create a ‘minefield’ of malicious domains based on misspellings of popular Google services. The tool starts up an Apache httpd server which runs continuously in the background, while the system’s hosts file is modified to include the extensive list of malicious domain. The tool relies on the user typing a domain or URL incorrectly – if this mistyped name matches one of the malicious domains created by the tool, the user is redirected to a malicious Google sign-in page. Username and password data gathered from the sign-in page is stored in the browser’s cookies and sent to either a server, or email address controlled by the attacker.
