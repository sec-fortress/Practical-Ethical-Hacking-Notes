Understanding what subdomains are is essential in performing web application penetration tests  . It's important to note that hunting subdomains can help eliminate unnecessary noise and focus on finding data ex-filtration.

*Tools used:*
- Sublist3r `CLI tool`
	- You can always install it with `apt-get install sublist3r` in Kali Linux
	- Then you can now run `sublist3r --help` to see how the tool works

- [Crt.sh](https://crt.sh) `domain` - crt.sh is a certificate search tool that allows users to search for certificates by domain name, organization name, fingerprint, or crt.sh ID.
	- Navigate to the site and make sure to denote `%` for subdomains e.g:
	-  Here are list of possible subdomains after our search result

- Amass `domain`  - Amass is a very powerful tool, That focuses more on attacking subdomains, if you are not sure on what to do visit https://github.com/owasp-amass/amass for full installation guide, but a simple `amass enum -passive -d tesla.com` should scan all subdomains on tesla.com