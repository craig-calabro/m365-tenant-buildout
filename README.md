# CalabroCorp Manufacturing M365 Tenant Buildout

## The Business Problem 
CalabroCorp Manufacturing is a fictional 50 Person manufacturing company that needed a complete Microsoft 365 environment configured from scratch. As the incoming M365 admin, I was responsible for setting up users, security policies, collaboration sites, and mail flow controls that a real company at this size would need. 

## What I Built
A M365 tenant with:
- 20 users across 5 departments (Executive, Finance, HR, Sales, Operations)
- 5 security groups aligned to departments
- 4 conditional access policies covering MFA and geographic restrictions 
- 4 SharePoint sites with department-appropriate access controls 
- Teams governence policies with naming conventions and external access rules
- Exchange mail flow rules for external email warnings and financial content protection

## Technology Used 
- Microsoft 365 admin center
- Microsoft Entra ID 
- Exchange Online admin center 
- SharePoint admin center
- Microsoft Teams admin center 
- Microsoft Purview complience portal

## Screenshots 
![Empty starting tenant](screenshots/00-empty-tenant.png)
![Empty users](screenshots/01-empty-users.png)
![First user](screenshots/02-first-user.png)
![User list pt 1](screenshots/03-user-list.png)
![User list pt 2](screenshots/04-user-list.png)
![User list pt 3](screenshots/05-user-list.png)
![Pre group creation](screenshots/06-before-groups-creation.png)
![Provisioned groups](screenshots/07-new-groups.png)
![group list example](screenshots/08-operations-team-grouplist.png)
![MFA for admins policy](screenshots/09-MFA-for-admins-policy.png)
![MFA for all users policy](screenshots/10-MFA-for-all-users-policy.png)
![Block legacy authentication policy](screenshots/11-block-legacy-authentication-policy.png)
![Blocked sign-in from blocked countries policy](screenshots/13-block-sign-in-from-blocked-countries-policy.png)
![Provisioned CalabroCorp Intranet SharePoint site](screenshots/14-calabrocorp-sharepoint-intranet-site.png)
![CalabroCorp Sharepoint site settings](screenshots/15-calabrocorp-sharepoint-settings.png)
![Provisioned Finance Hub SharePoint site](screenshots/16-Finance-hub-sharepoint.png)
![Finance Hub Sharepoint site settings](screenshots/17-finance-hub-sharepoint-settings.png)
![Provisioned HR portal SharePoint site](screenshots/18-HR-portal-sharepoint-site.png)
![HR portal SharePoint site settings](screenshots/19-HR-portal-sharepoint-settings.png)
![Provisioned sales team SharePoint site](screenshots/20-sales-team-sharepoint-site.png)
![Sales team SharePoint site settings](screenshots/21-sales-team-sharepoint-settings.png)
![CalabroCorp default teams policy](screenshots/22-default-teams-policy.png)
![Naming convention settings](screenshots/23-naming-policy-settings.png)
![External access settings](screenshots/24-external-access-settings.png)
![Exchange external email rule pt 1](screenshots/25-exchange-external-email-rule-1.png)
![Exchange external email rule pt 2](screenshots/26-exchange-external-email-rule-2.png)
![Provisioned shared mailbox](screenshots/27-shared-mailbox.png)
![Block auto-forwarding of financial content rule](screenshots/28-block-auto-forward-of-financial-content-policy.png)

## Design Decisions
- Chose to require MFA for all users, not just admins, because credential theft is the most common breach vector. 
- Blocked sign-in from countries where CalabroCorp doesn't operate, because attack traffic disproportionately comes from the regionsCountries I chose to block.
- Set Teams naming conventions with department prefixes to make future audit and cleanup easier.

## Lessons Learned
  - I realized that creating users one at a time in the admin center was painfully slow. This directly motivated my second project using PowerShell automation. 
  - 