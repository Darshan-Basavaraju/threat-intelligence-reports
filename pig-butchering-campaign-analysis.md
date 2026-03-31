# Pig Butchering Fraud Campaign — Multi-Platform Brand Impersonation Analysis

**Date:** March 2024  
**Author:** Darshan Basavaraju  
**TLP:** WHITE — Cleared for public distribution  
**Classification:** Threat Intelligence Report  

---

## Executive Summary

A domain alert flagged a typosquatted domain impersonating a well-known digital 
intelligence brand as part of a coordinated pig butchering fraud campaign. 
Investigation revealed a multi-platform operation consisting of typosquatted 
domains using the .pk country code TLD and a network of 5-10 YouTube channels 
publishing hundreds of promotional videos designed to lure victims into a fake 
investment application promising high financial returns. Threat actor infrastructure 
was attributed across multiple platforms, takedown actions were initiated, and the 
client was notified with full findings and remediation recommendations.

---

## Investigation Background

During routine threat monitoring activities, a domain alert was triggered identifying 
a typosquatted domain impersonating a well-known digital intelligence brand owned by 
a multinational PR and media intelligence company. The domain utilized a .pk country 
code TLD — a common technique used by threat actors to create convincing lookalike 
domains that appear legitimate to victims unfamiliar with domain structure.

The initial alert indicated the domain was hosting a fake login page for an investment 
application fraudulently using the brand's identity to establish credibility. Given the 
nature of the impersonation and the financial fraud indicators, a full OSINT investigation 
was initiated to understand the scope of the campaign, identify related infrastructure, 
and attribute the operation to a coordinated threat actor.

---

## Technical Analysis

The investigation began with analysis of the flagged domain itself. The domain followed 
a classic typosquatting pattern — incorporating the target brand name with minor 
modifications and appending a .pk country code TLD to create a convincing lookalike. 
This naming convention is commonly used in brand impersonation campaigns to deceive 
victims who may not scrutinize the full domain carefully.

To understand how the fraudulent domain was being distributed and promoted, Google 
dorking techniques and open source intelligence methodology were applied to trace the 
campaign's reach across the open web. The following Google dork was used to identify 
pages and platforms referencing the fraudulent application by its brand-impersonating name:
```
"[brand name] earning app"
```

This search surfaced multiple results linking to YouTube channels actively promoting 
the fraudulent investment application — revealing a distribution network that extended 
well beyond the initial domain alert.

Investigation of the domain revealed it was hosting a fraudulent investment application 
interface — impersonating the target brand to establish legitimacy and trust with 
potential victims. The fake application promised high financial returns to lure victims 
into depositing real funds into attacker-controlled accounts — a hallmark characteristic 
of pig butchering fraud campaigns.

Pivoting from the domain to broader infrastructure via the Google dork results revealed 
a coordinated YouTube-based promotion network. Between 5 and 10 YouTube channels were 
identified publishing hundreds of promotional videos designed to drive traffic to the 
fraudulent domains. The videos presented fabricated investment success stories and return 
promises consistent with pig butchering social engineering tactics — building victim trust 
over time before directing them to the fake application.

The combination of typosquatted domains and a large-scale YouTube promotion network 
indicated a well-resourced, coordinated threat actor operation rather than an 
opportunistic individual attack.

---

## Infrastructure Analysis

The threat actor infrastructure identified during this investigation consisted of two 
primary components — typosquatted domains and a YouTube-based promotion network — 
working in coordination to execute the fraud campaign.

### Domain Infrastructure

The initial alert flagged a typosquatted domain utilizing the .pk country code TLD — 
Pakistan's ccTLD — to impersonate the target brand. The use of a country code TLD 
rather than a generic TLD such as .com or .net is a deliberate technique used by 
threat actors to register convincing lookalike domains at lower cost while evading 
brand monitoring tools that primarily focus on generic TLDs.

The domain hosted a fraudulent investment application login page designed to visually 
mimic the target brand's legitimate interface — leveraging brand recognition to establish 
victim trust before harvesting credentials and financial deposits.

### YouTube Promotion Network

OSINT investigation and Google dorking revealed a coordinated network of 5-10 YouTube 
channels operating in support of the fraudulent domain infrastructure. The channels 
collectively published hundreds of videos promoting the fake investment application — 
presenting fabricated testimonials, manufactured profit screenshots, and false return 
promises to attract potential victims.

The scale of the YouTube operation — multiple channels with hundreds of videos — 
indicates significant threat actor investment in the campaign. Building and maintaining 
this volume of content requires sustained effort and resources, suggesting an organized 
criminal operation rather than an individual actor.

### Infrastructure Correlation

The connection between the typosquatted domains and the YouTube promotion network was 
established through Google dorking — searching for keywords associated with the 
fraudulent application name revealed the YouTube channels actively directing victims 
to the malicious domains. This multi-platform coordination is consistent with pig 
butchering campaign tradecraft where threat actors build victim trust through multiple 
touchpoints before executing the fraud.

---

## MITRE ATT&CK Mapping

The pig butchering campaign identified during this investigation maps across three 
MITRE ATT&CK tactics — Resource Development, Initial Access, and Impact — reflecting 
the full lifecycle of the fraud operation from infrastructure setup through victim 
targeting to financial theft.

| Tactic | Technique ID | Technique Name | How It Applied |
|--------|-------------|----------------|----------------|
| Resource Development | T1583.001 | Acquire Infrastructure: Domains | Threat actor registered typosquatted domains using .pk ccTLD to impersonate the target brand |
| Resource Development | T1585.001 | Establish Accounts: Social Media | Threat actor created 5-10 YouTube channels to build a promotion network driving victims to fraudulent domains |
| Initial Access | T1566.003 | Phishing: Spearphishing via Service | Victims were approached and directed to the fraudulent application through YouTube — a third party service — rather than direct email phishing |
| Impact | T1657 | Financial Theft | The end objective of the campaign was luring victims into depositing real funds into attacker-controlled accounts under the premise of high investment returns |

The campaign's primary activity was concentrated in the Resource Development stage — 
the threat actor invested significantly in building convincing infrastructure before 
approaching any victims. This early-stage activity represents the highest value 
disruption point — identifying and dismantling attacker infrastructure before victims 
are contacted prevents fraud losses entirely rather than responding after the fact.

---

## Indicators of Compromise

The following indicators of compromise were identified during the investigation. 
Organizations are advised to block these indicators at perimeter defenses and monitor 
for any historical connections to this infrastructure.

*Note: Specific domain names, URLs, and YouTube channel identifiers have been redacted 
from this public report to protect client confidentiality. The IOC formats and types 
are documented below for reference.*

### Domain Indicators

| Type | Description | Notes |
|------|-------------|-------|
| Domain | Typosquatted domain — brand name + .pk ccTLD | Hosted fraudulent investment application login page |
| URL | Login page URL hosted on typosquatted domain | Credential harvesting and financial fraud interface |

### Network Indicators

| Type | Description | Notes |
|------|-------------|-------|
| ccTLD Pattern | .pk country code TLD | Used across identified fraudulent domains in this campaign |
| Naming Pattern | [Brand Name] + earning/investment keywords | Consistent typosquatting pattern used for domain registration |

### Content Indicators

| Type | Description | Notes |
|------|-------------|-------|
| YouTube Channels | 5-10 channels promoting fraudulent application | Hundreds of videos published across identified channels |
| Keywords | "[Brand Name] earning app" | Google dork search term used to identify promotion network |
| Content Type | Fabricated investment testimonials and profit screenshots | Consistent pig butchering social engineering content |

### Behavioral Indicators

| Type | Description | Notes |
|------|-------------|-------|
| TTP | Multi-platform brand impersonation | Domain + YouTube network operating in coordination |
| TTP | Typosquatting using ccTLD | .pk TLD used to evade brand monitoring tools |
| TTP | Google-indexed promotion network | YouTube content indexed by search engines to maximize victim reach |

---

## Recommended Actions

Based on the findings of this investigation the following actions are recommended 
for organizations whose brands may be targeted by similar pig butchering campaigns.

### Immediate Actions

**1. Takedown Initiation**  
Submit abuse reports to domain registrars for all identified typosquatted domains — 
specifically targeting .pk ccTLD registrations impersonating the brand. Simultaneously 
submit content removal requests to YouTube for all identified channels and videos 
promoting the fraudulent application.

**2. Brand Monitoring Enhancement**  
Expand brand monitoring coverage to include country code TLDs — particularly .pk, 
.in, .cn, and other ccTLDs commonly used in fraud campaigns — in addition to generic 
TLDs such as .com and .net.

**3. Threat Intelligence Sharing**  
Share identified IOCs with relevant industry threat intelligence sharing communities 
and brand protection partners to accelerate detection and takedown across the broader 
security ecosystem.

### Short Term Actions

**4. Google Dorking Monitoring**  
Implement regular Google dorking using brand name combined with investment and earning 
keywords to proactively identify new fraudulent applications and promotion networks 
before they reach significant victim scale.

**5. YouTube Monitoring**  
Establish ongoing monitoring of YouTube for brand impersonation content — specifically 
fake investment testimonials and earning application promotions using the brand name. 
YouTube's reporting API and brand monitoring tools can automate this process at scale.

**6. Customer Advisory**  
Issue a public advisory informing customers that the organization does not operate any 
investment or earning applications — and that any application claiming affiliation with 
the brand offering financial returns is fraudulent.

### Long Term Actions

**7. Defensive Domain Registration**  
Register common typosquatting variations of key brand domains across high-risk ccTLDs 
— including .pk — to prevent threat actors from registering them for future campaigns.

**8. Threat Intelligence Integration**  
Integrate pig butchering campaign indicators into existing threat intelligence feeds 
to improve automated detection of similar campaigns targeting the brand in future.

---

## Conclusion

This investigation demonstrates the evolving sophistication of pig butchering fraud 
campaigns — moving beyond simple phishing domains to coordinated multi-platform 
operations that combine typosquatted brand infrastructure with large-scale social 
media promotion networks to maximize victim reach and credibility.

The threat actor's decision to invest in 5-10 YouTube channels publishing hundreds 
of promotional videos alongside typosquatted domains indicates a well-resourced, 
organized criminal operation with a high victim acquisition budget. The use of .pk 
ccTLD registrations reflects deliberate evasion of brand monitoring tools that 
primarily focus on generic TLDs — a technique that will likely become more prevalent 
as brand protection coverage improves.

The key takeaway for threat intelligence practitioners is that pig butchering campaigns 
are no longer confined to direct social media outreach. Threat actors are increasingly 
building search-engine-indexed content ecosystems — YouTube channels, fake review sites, 
and social media pages — to create an illusion of legitimacy before victims ever interact 
with the fraudulent application directly. Detecting these campaigns requires proactive 
OSINT hunting beyond platform alert queues — specifically Google dorking and 
cross-platform infrastructure correlation.

Early detection and disruption of attacker infrastructure in the Resource Development 
stage — before victims are contacted — remains the highest value intervention point 
in pig butchering campaigns. This investigation resulted in successful takedown of the 
identified infrastructure before significant victim losses could occur.

---
