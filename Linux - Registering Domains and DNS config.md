---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: March
day: 13
creation date: 2024-03-13 10:53
modification date: Wednesday 13th March 2024 10:53:51
---

#internetContent  #computerScience/networking
## Article link:
[How to Use the dig Command on Linux](https://www.howtogeek.com/663056/how-to-use-the-dig-command-on-linux/)
related notes: 
- [[]]
_____
## Content

resources:
- [intoDNS: checks DNS and mail servers health](https://intodns.com/)
- [Managing a custom domain for your GitHub Pages site - GitHub Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Đăng nhập | Domain Controller](https://domain.tenten.vn)

For the DNS inspect 

> sudo pacman -Sy bind-tools

using `dig` to inspect DNS record of a domain 

> dig single-core-pentium.id.vn  +noall +answer -t A

## DNS config 

**Understanding DNS:**

- **Domain Name System (DNS):** Acts like a phonebook for the internet, translating domain names (e.g., single-core-pentium.id.vn) into IP addresses that computers can understand.
- **Apex Domain:** The main domain name you register (single-core-pentium.id.vn).
- **Subdomain:** Any domain name created under the apex domain (e.g., www.single-core-pentium.id.vn).

**Registering a Domain:**

- You likely registered "single-core-pentium.id.vn" through a domain registrar like Tenten.vn.
- This gives you ownership of the domain name and allows you to configure its DNS settings.

**Configuring DNS Records:**

- DNS records specify how your domain name translates to different services.
- Common record types you encountered:
    - **A Record:** Maps a domain name (e.g., single-core-pentium.id.vn or www.single-core-pentium.id.vn) to an IP address (e.g., GitHub Pages server IP).
    - **TXT Record:** Used for verification purposes (e.g., verifying your domain ownership for GitHub Pages).
    - **MX Record:** Directs emails sent to your domain (e.g., [email address removed]) to a specific email server.

**Key Points Learned:**

- **DNS Propagation:** Changes to DNS records can take up to 24 hours to propagate globally. Be patient after making changes!
- **Tenten.vn DNS Interface:** Your specific interface for adding and managing DNS records might differ slightly from the general examples provided here. Refer to Tenten.vn's documentation for details.
- **Duplicate RecordSet:** When creating A records, ensure they have unique combinations of "Name," "Type," and "Value." Multiple A records with the same settings can cause errors.
- **Automatic Conversion (Tenten.vn):** Tenten.vn might automatically convert the "Name" field entry for the apex domain to "@" symbol. This is a common shorthand in DNS.
- **Multiple A Records (GitHub Pages):** While technically possible, creating multiple A records with different IP addresses is not necessary for most setups with GitHub Pages. A single A record pointing to any of the provided IP addresses should be sufficient.

**Using Your Domain with GitHub Pages:**

- You can configure your domain (single-core-pentium.id.vn) to work with GitHub Pages.
- Verify your domain ownership with GitHub Pages by adding a TXT record to your DNS configuration.
- Create an A record pointing your domain name (or www subdomain) to the IP address provided by GitHub Pages.
- Consider creating an A record for the "www" subdomain (www.single-core-pentium.id.vn) to ensure access with and without the "www" prefix.
- You can use subfolders within a single GitHub repository to deploy multiple projects under your main domain (e.g., single-core-pentium.id.vn/page1).
- For more complex setups, CNAME records can be used to create additional subdomains (e.g., page1.single-core-pentium.id.vn) pointing to separate GitHub repositories.

**Additional Resources:**

- Tenten.vn DNS Management Documentation
- GitHub Pages Custom Domain Documentation ([https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site))
- intoDNS Tool for DNS record inspection ([https://www.intodns.com/](https://www.intodns.com/))

By understanding these concepts and following the steps outlined, you should be able to register and configure your domain's DNS for various purposes, including using it with GitHub Pages.

## CNAME 

**CNAME Records:**

- A CNAME record is a type of DNS record that points a subdomain to another domain name.
- Instead of directly mapping to an IP address, the subdomain inherits the IP address of the target domain.

**Using CNAME Records with GitHub Pages:**

- You can leverage CNAME records to create custom subdomains for your GitHub Pages deployments.
- This allows you to have separate URLs for different projects hosted under your main domain.

**Benefits of Subdomains with CNAME Records:**

- **Clean and Organized URLs:**
    - Example: "blog.yourdomain.com" for your blog and "[invalid URL removed]" for your web application.
- **Independent Project Management:**
    - Each subdomain can point to a separate GitHub repository, allowing independent version control and deployment.
- **Flexibility:**
    - You can manage subdomains and their content separately.

**Steps to Configure Subdomains with CNAME Records:**

1. **Create a Subdomain:** Choose a subdomain name relevant to your project (e.g., "blog" or "app").
2. **Set Up a GitHub Pages Repository:** Create a new repository on GitHub for your subdomain project.
3. **Enable GitHub Pages for the Repository:** In your repository settings, navigate to the "Pages" section and activate GitHub Pages.
4. **Add a CNAME Record:**
    - Access your domain's DNS management panel on Tenten.vn.
    - Create a new CNAME record.
    - Set the "Name" field to your subdomain (e.g., "blog" or "app").
    - Set the "Value" field to the custom domain provided by GitHub Pages for your repository (e.g., "username.github.io").
5. **Verify and Wait for Propagation:** Save the CNAME record. It can take up to 24 hours for the changes to propagate globally.

**Important Considerations:**

- **Conflicting CNAME Records:** Avoid creating multiple CNAME records for the same subdomain as it can lead to errors.
- **Apex Domain vs. Subdomain:** You cannot use a CNAME record for the apex domain ([invalid URL removed]) with GitHub Pages. It requires an A record pointing to the GitHub Pages IP addresses.
- **Alternatives to CNAME Records:** Subfolders within a single GitHub repository offer a simpler approach for deploying multiple projects under your main domain, but without separate URLs.

**Example Scenario:**

- You want separate URLs for your blog and portfolio hosted on GitHub Pages under your domain single-core-pentium.id.vn.
- Create a CNAME record for "blog.single-core-pentium.id.vn" pointing to the custom domain provided by GitHub Pages for your blog repository.
- Similarly, create another CNAME record for "portfolio.single-core-pentium.id.vn" pointing to your portfolio repository's custom domain.

**Additional Resources:**

- GitHub Pages Custom Domain Documentation ([https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site))
- CNAME Records Explained ([https://www.godaddy.com/help/add-a-cname-record-19236](https://www.godaddy.com/help/add-a-cname-record-19236))

By understanding CNAME records and their application with GitHub Pages, you can create well-structured and organized URLs for your various projects, enhancing the user experience and managing them independently.

### example of adding subdomain on github pages using CNAME record 

apex site: `single-core-pentium.id.vn` - github repo: potatomat0/potatomat0.github.io

subdomain site: `resume.single-core-pentium.id.vn` - guthub repo: potatomat0/resume 

CNAME record that would be applied on tenten.vn's DNS config for custom domains: 

Type: CNAME - DNS record name: `resume.single-core-pentium.id.vn ` - DNS record value: potatomat0.github.io 

> [!NOTE]
> whenever you need a new subdomain, just add a different CNAME row in the domain registar `subName.example.com` and type the same custom domain in the github pages custom domain 

