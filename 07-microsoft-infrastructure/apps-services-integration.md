# Applications & Services to Integrate with


## Microsoft 365
_Access users, mail, calendars via MS Graph_

## Microsoft Teams
_Bots, messaging, Teams Graph API_

- Separate directory, but hard dependent on Office Groups  
- Various cloud services integrated  
- Main pain points  

## Microsoft Intune
_Device status, compliance APIs_

*   Text: [Microsoft Intune product and capabilities documentation | Microsoft Learn](https://learn.microsoft.com/en-us/mem/ "https://learn.microsoft.com/en-us/mem/") `Beginner` `3 month`

## Microsoft Graph API
_Unified API for everything M365-related_

- [Overview of Microsoft Graph - Microsoft Graph | Microsoft Docs ](https://docs.microsoft.com/en-us/graph/overview)
- MSOL (oldest) vs Azure AD Graph (old) vs MS Graph (new) 
    - [Discussion](https://www.reddit.com/r/PowerShell/comments/9kjt73/connectazuread_vs_connectmsolservice/)
    - [MSOL](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)
    - Azure AD [Graph](https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)
- Beyond users and groups 

## Microsoft Exchange Online
_Mailbox data, calendars via EWS or Graph_

- Separate directory, delays  
- DL-s vs Office Groups  
- PS Session threshold  
- Exchange Online pain points  
    - Provisioning automation (delayed mailbox creation)  
    - Deprovisioning automation (preserve mailbox w/o keeping the license assigned)  
    - Single console for Hybrid  
    - Single console to manage on-prem and cloud DL-s  

## Exchange Server On-prem

- Org, servers, mailboxes  
- AD as a recipient directory (briefly [here](https://docs.microsoft.com/en-us/exchange/plan-and-deploy/active-directory/active-directory?view=exchserver-2019)) -> one Exchange services per forest 
    - Expands schema 
    - http://www.selfadsi.org/attributes-e2k3.htm 
- Mailbox-enabled vs mail-enabled ([here](https://searchwindowsserver.techtarget.com/tutorial/Part-1-Exchange-Server-mailbox-enabled-and-mail-enabled-recipients)) 
- Shared and Resource mailboxes  
- DL-s (Distribution lists)
- [Linked mailbox](http://technet.microsoft.com/en-us/library/bb123524.aspx) scenario (multi-forest environment) (in depth on multi-forest Exchange [here](http://techgenix.com/deep-dive-into-rich-coexistence-between-exchange-forests-part1/)) 
- PS Exchange module and remoting  
- Main pain points  
    - Provisioning automation  
    - Deprovisioning automation (suspend)  
    - Single Help Desk console to combine AD, Exchange and other account management admin centers  
    - Field format and consistency  
    - DL administration delegation, down to self-service 


## 2.7 Microsoft Hybrid / Exchange Hybrid

*   Azure AD Sync (briefly [here](https://www.youtube.com/watch?v=ieSlu6uUFGE), deep look [here](https://www.youtube.com/watch?v=1rhI3Ngjp4I))
*   [Synced vs cloud-only accounts  ](https://docs.microsoft.com/en-us/office365/enterprise/about-office-365-identity)
*   [ImmutableID ](https://blogs.perficient.com/2015/04/01/office-365-why-you-need-to-understand-immutableid/)
