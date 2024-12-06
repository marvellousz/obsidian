## 1. **What is DNS?**
- DNS acts as the **internet's phonebook**, translating **human-readable domain names** (e.g., `example.com`) into **IP addresses** (e.g., `192.168.1.1`), which computers use to locate each other on a network.

---

## 2. **How DNS Works:**
1. **User Request:** A user types a domain name (e.g., `example.com`) into their browser.
2. **DNS Resolver:** The Internet Service Provider (ISP) forwards the query to a DNS resolver.
3. **Root Server:** The resolver queries the DNS root server for the domain's **Top-Level Domain (TLD)** (e.g., `.com`).
4. **TLD Server:** The TLD server points to the **authoritative nameserver** for the domain.
5. **Authoritative Nameserver:** Provides the **IP address** for the domain name.
6. **Result:** The resolver returns the IP address to the user's device, which connects to the website.

---

## 3. **Key DNS Components:**
- **ISP (Internet Service Provider):** Provides DNS resolvers to translate domain names into IP addresses for end-users.
- **ICANN (Internet Corporation for Assigned Names and Numbers):** Governs the global DNS system, domain name policies, and IP address allocations.
- **Registrar:** Organizations authorized by ICANN to manage domain registrations (e.g., GoDaddy, Namecheap).

---

## 4. **Common DNS Records:**
1. **A Record (Address Record):**
   - Maps a domain name to an IPv4 address.
   - Example: `example.com -> 192.168.1.1`.
   
2. **AAAA Record:**
   - Maps a domain name to an IPv6 address.
   - Example: `example.com -> 2001:0db8:85a3::8a2e:0370:7334`.

3. **CNAME Record (Canonical Name):**
   - Points a domain or subdomain to another domain.
   - Example: `www.example.com -> example.com`.

4. **MX Record (Mail Exchange):**
   - Specifies mail servers for email delivery.
   - Example: `mail.example.com`.

5. **TXT Record:**
   - Stores arbitrary text, often used for verification or security (e.g., SPF, DKIM).

6. **NS Record (Name Server):**
   - Specifies the authoritative nameservers for the domain.

7. **PTR Record:**
   - Used for reverse DNS, mapping IP addresses to domain names.

---

## 5. **Top-Level Domains (TLDs):**
- **TLD:** The last segment of a domain name (e.g., `.com`, `.org`, `.net`).
- Types of TLDs:
  - **Generic TLDs (gTLDs):** `.com`, `.org`, `.net`.
  - **Country Code TLDs (ccTLDs):** `.uk`, `.in`, `.us`.
  - **Sponsored TLDs (sTLDs):** `.edu`, `.gov`.

---

## 6. **DNS Tools:**
- **nslookup:**
  - A command-line tool to query DNS and retrieve information about DNS records for a domain.
  - Example:
    ```
    nslookup example.com
    ```
    Output: Shows the IP address or other DNS details of the domain.

