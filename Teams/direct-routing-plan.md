---
title: Planifier le routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Découvrez comment le routage direct du système Microsoft Phone vous permet de connecter un contrôleur de bordure de session fourni par le client (SBC) au système Microsoft Phone.
ms.openlocfilehash: 0140e4d2cfae95531602daec5a859a85888e9d15
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780693"
---
# <a name="plan-direct-routing"></a>Planifier le routage direct

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du routage direct, la planification et le déploiement : [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)

Le routage direct du système Microsoft Phone vous permet de connecter un contrôleur de bordure de session (SBC) fourni par le client au système Microsoft Phone.  Grâce à cette fonctionnalité, vous pouvez par exemple configurer une connectivité PSTN (réseau téléphonique commuté) locale avec le client Microsoft Teams, comme indiqué dans le schéma suivant : 

![Diagramme montrant la configuration de la connectivité PSTN locale](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration de la connectivité PSTN locale avec le client Microsoft teams")

  > [!NOTE]
  > Skype entreprise Online vous permet également de jumeler une SBC fournie par l’utilisateur, mais cela nécessite un déploiement sur site de Skype entreprise Server ou une édition spéciale de Skype entreprise, appelée Cloud Connector, entre SBC et Microsoft Cloud. Ce scénario est connu sous le nom de voix hybride. En revanche, le routage direct autorise une connexion directe entre SBC et Microsoft Cloud. 

Avec le routage direct, vous pouvez connecter votre SBC à presque n’importe quel Trunk ou interconnexion de téléphonie avec un équipement RTC tiers. Le routage direct vous permet d’effectuer les opérations suivantes : 

- Utilisez virtuellement n’importe quel Trunk RTC avec un système Microsoft Phone. 
- Configurer l’interopérabilité entre les équipements de téléphonie qui appartiennent au client, tels qu’un système PBX tiers, des appareils analogiques et un système Microsoft Phone.

Microsoft propose également une solution vocale tout-en-un, comme un forfait d’appels. Toutefois, une solution vocale hybride peut s’avérer particulièrement adaptée à votre organisation dans les cas suivants : 

- Le plan d’appel Microsoft n’est pas disponible dans votre pays. 
- Votre organisation nécessite une connexion à des appareils analogiques tiers, des centres d’appels, etc. 
- Votre organisation dispose d’un contrat avec un opérateur PSTN.

Le routage direct prend également en charge les utilisateurs dotés de la licence supplémentaire pour le forfait d’appel Microsoft. Pour plus d’informations, consultez la section [système téléphonique et forfaits d’appels](calling-plan-landing-page.md). 

Lorsque les utilisateurs participent à une conférence planifiée, le numéro d’accès est fourni par le service de conférence rendez-vous de Microsoft, qui nécessite des licences appropriées.  Lors d’un appel sortant, le service de conférence rendez-vous de Microsoft passe l’appel à l’aide des fonctionnalités d’appel en ligne, qui nécessitent une gestion appropriée des licences. (Notez que la numérotation n’est pas routée via le routage direct.) Pour plus d’informations, reportez-vous à la rubrique [réunions en ligne avec teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
La planification de votre déploiement du routage direct est essentiel pour une implémentation réussie. Cet article décrit les exigences en matière d’infrastructure et de gestion des licences et fournit des informations sur la connectivité SBC : 

- [Conditions requises pour l'infrastructure](#infrastructure-requirements)
- [Gestion des licences et autres conditions requises](#licensing-and-other-requirements)
- [Noms de domaine SBC](#sbc-domain-names)
- [Certificat de confiance public pour l’SBC](#public-trusted-certificate-for-the-sbc)
- [Signalisation SIP : noms de domaine complets](#sip-signaling-fqdns)
- [Signalisation SIP : ports](#sip-signaling-ports)
- [Trafic multimédia : plages de ports](#media-traffic-port-ranges)
- [Contrôleurs de bordure de session pris en charge (SBCs)](#supported-session-border-controllers-sbcs)

Pour plus d’informations sur la configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Conditions d’infrastructure requises
Les exigences d’infrastructure pour les domaines SBCs et de connectivité réseau pris en charge pour le déploiement du routage direct sont indiquées dans le tableau suivant :  

|**Exigence d’infrastructure**|**Vous avez besoin des éléments suivants :**|
|:--- |:--- |
|Contrôleur de bordure de session (SBC)|SBC pris en charge. Pour plus d’informations, voir [SBCS prises en charge](#supported-session-border-controllers-sbcs).|
|Lignes de téléphonie connectées à l’SBC|Un ou plusieurs Trunks de téléphonie connectés à l’SBC. À la fin, l’SBC se connecte au système Microsoft Phone via le routage direct. Les SBC peuvent également se connecter à des entités de téléphonie tierces, telles que des PBX, des adaptateurs de téléphonie analogique, etc. Toute option de connectivité PSTN qui est connectée à l’SBC fonctionne. (Pour la configuration des Trunks RTC auprès de l’SBC, veuillez consulter les fournisseurs ou les fournisseurs de lignes SBC.)|
|Organisation Office 365|Une organisation Office 365 que vous utilisez pour les utilisateurs de Microsoft Teams, ainsi que la configuration et la connexion au SBC.|
|Bureau d’enregistrement de noms d’utilisateur|L’utilisateur doit être hébergé dans Office 365.<br/>Si votre entreprise possède un environnement Skype entreprise ou Lync local avec une connectivité hybride à Office 365, vous ne pouvez pas activer la voix dans teams pour un utilisateur hébergé sur site.<br/><br/>Pour vérifier le Bureau d’enregistrement d’un utilisateur, utilisez l’applet de commande PowerShell Skype entreprise Online suivante :<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>La sortie de l’applet de cmdlet doit afficher les éléments suivants :<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domaines|Un ou plusieurs domaines ajoutés à vos organisations Office 365.<br/><br/>Notez que vous ne pouvez pas utiliser le domaine \*par défaut,. onmicrosoft.com, qui est automatiquement créé pour votre client.<br/><br/>Pour afficher les domaines, vous pouvez utiliser l’applet de commande PowerShell de Skype entreprise Online suivante :<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Pour plus d’informations sur les domaines et les organisations 365 d’Office, voir [FAQ sur les domaines](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Adresse IP publique de l’SBC|Une adresse IP publique qui peut être utilisée pour se connecter à l’SBC. En fonction du type de SBC, l’SBC peut utiliser la traduction d’adresses réseau (NAT).|
|Nom de domaine complet (FQDN) pour l’SBC|Nom de domaine complet pour l’SBC, où la partie Domain du nom de domaine complet (FQDN) est l’un des domaines inscrits dans votre organisation Office 365. Pour plus d’informations, consultez la section [noms de domaine SBC](#sbc-domain-names).|
|Entrée DNS publique pour l’SBC |Une entrée DNS publique qui mappe le nom de domaine complet du SBC à l’adresse IP publique. |
|Certificat de confiance public pour l’SBC |Certificat de l’SBC à utiliser pour toutes les communications avec le routage direct. Pour plus d’informations, voir [certificat de confiance public pour l’SBC](#public-trusted-certificate-for-the-sbc).|
|Points de connexion pour le routage direct |Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :<br/><br/>`sip.pstnhub.microsoft.com`-Nom de domaine complet (FQDN) global, doit d’abord être essayé.<br/>`sip2.pstnhub.microsoft.com`– Nom de domaine complet secondaire, géographiquement correspond à la deuxième région de priorité.<br/>`sip3.pstnhub.microsoft.com`– Nom de domaine complet (FQDN), qui correspond à la troisième région de priorité.<br/><br/>Pour plus d’informations sur la configuration requise, reportez-vous à la section [signalisation SIP : FQDN](#sip-signaling-fqdns).|
|Adresses IP et ports du pare-feu pour le média de routage direct |Le SBC communique avec les services suivants dans le Cloud :<br/><br/>Proxy SIP, qui gère le signalement<br/>Processeur multimédia, qui gère les éléments multimédias, sauf lorsque la dérivation multimédia est activée<br/><br/>Ces deux services ont des adresses IP distinctes dans le Cloud Microsoft, décrites plus loin dans ce document.<br/><br/>Pour plus d’informations, reportez-vous à la [section Microsoft teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) dans les [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Profil de transport de média|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Adresses IP et ports pour le pare-feu pour les éléments multimédias de Microsoft teams |Pour plus d’informations, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Gestion des licences et autres conditions requises 

Les utilisateurs du routage direct doivent avoir les licences suivantes affectées dans Office 365 : 

- Système Microsoft Phone. 
- Microsoft teams + Skype entreprise plan 2, s’il est inclus dans la gestion des licences.
- Audioconférence Microsoft (Merci de lire les remarques et le paragraphe ci-dessous pour obtenir des exemples spécifiques de la nécessité d’une licence).

> [!NOTE]
> L’offre Skype entreprise ne doit pas être supprimée du contrat de licence dans lequel elle est incluse. 


> [!IMPORTANT]
>  Dans le cas où vous aimeriez ajouter des participants externes à des réunions planifiées, vous devez les appeler ou en fournissant un numéro de connexion, la licence de conférence audio est requise.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Augmentation d’une licence d’appel ad hoc et audioconférence

Un utilisateur d’équipes peut lancer une équipe en tête-à-tête pour appeler des équipes RTC et ajouter un participant PSTN. Ce scénario est appelé une conférence ad hoc. Le chemin d’accès utilisé par l’utilisateur dépend de l’attribution d’une licence d’audioconférence Microsoft ou non à l’utilisateur qui transfère l’appel.

- Si l’utilisateur teams qui a escaladé l’appel a été affecté d’une licence de conférence rendez-vous, la réaffectation intervient via le service Microsoft audio Conferencing. Le participant RTC distant qui est invité à l’appel en cours reçoit une notification concernant l’appel entrant et voit le numéro de Microsoft Bridge attribué à l’utilisateur de teams à l’origine de la progression.
- Si l’utilisateur teams qui transmet l’appel n’a pas de licence de conférence rendez-vous Microsoft, la réaffectation intervient par le biais d’un contrôleur de bordure de session connecté à l’interface de routage directe. Le participant RTC distant invité à l’appel reçoit une notification concernant l’appel entrant et voit le numéro de l’utilisateur d’équipe ayant lancé la redirection. L’objet SBC particulier utilisé pour la réaffectation est défini par la stratégie de routage de l’utilisateur. 


Par ailleurs, vous devez vous assurer que les suivants :
 
- CsOnlineVoiceRoutingPolicy est affectée à l’utilisateur. 
- L’option autoriser les appels privés est activée au niveau du client de Microsoft Teams. 

Le routage direct prend également en charge les utilisateurs disposant d’une licence pour un forfait d’appel Microsoft. Le système Microsoft Phone avec un plan d’appels peut acheminer certains appels à l’aide de l’interface de routage directe. Toutefois, les numéros de téléphone des utilisateurs doivent être acquis en ligne ou transférés vers Microsoft.  

Le mélange d’un plan d’appel et de la connectivité de routage directe pour le même utilisateur est facultatif, mais peut être utile (par exemple, lorsque l’utilisateur dispose d’un plan d’appel Microsoft et veut diriger certains appels à l’aide de la SBC). L’un des scénarios les plus courants est l’appel vers des PBX tiers.  Avec les PBX tiers, tous les appels, à l’exception de ceux qui sont connectés à ces PBX, sont routés à l’aide d’un forfait d’appel Microsoft, mais les appels vers les téléphones connectés à des PBX tiers sont dirigés vers l’SBC et ne sont donc pas du réseau d’entreprise. 

Pour plus d’informations sur les licences de système téléphonique, voir [tirer le meilleur parti d’Office avec les options de](https://products.office.com/compare-all-microsoft-office-products?tab=2) Plan Office 365 et [Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx). 

Pour plus d’informations sur la gestion des licences de système téléphonique, voir [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Points de terminaison pris en charge 

Vous pouvez utiliser un point de terminaison :

- Un client Teams. 
- Téléphones communs. Reportez-vous [à la rubrique Configuration de la licence de téléphone de zone commune de Microsoft teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones). Remarque vous n’avez pas besoin d’une licence de plan d’appel lorsque vous configurez un numéro de téléphone commun avec le routage direct.
- Téléphones 3PIP Skype entreprise. [Pour plus d’aide sur la prise en charge des téléphones Skype entreprise (3PIP), voir Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Noms de domaine SBC

Le nom de domaine SBC doit être issu de l’un des noms inscrits dans les domaines du client. Vous ne pouvez pas \*utiliser le client. onmicrosoft.com pour le nom de domaine complet de l’SBC.

Le tableau suivant montre des exemples de noms DNS enregistrés pour le client, que le nom puisse être utilisé comme nom de domaine complet pour l’SBC et des exemples de noms de domaine complets valides :

|**Nom DNS**|**Peut être utilisé pour le nom de domaine complet SBC**|**Exemples de noms de FQDN**|
|:--- |:--- |:--- |
contoso.com|Oui|**Noms valides :**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Non|L’utilisation des domaines *. onmicrosoft.com n’est pas prise en charge pour les noms SBC

Supposons que vous vouliez utiliser un nouveau nom de domaine. Par exemple, votre locataire a contoso.com comme nom de domaine enregistré dans votre client et vous souhaitez utiliser sbc1.sip.contoso.com. Avant de pouvoir coupler une SBC avec le nom sbc1.sip.contoso.com, vous devez inscrire le nom de domaine sip.contoso.com dans les domaines de votre client. Si vous essayez de jumeler une SBC avec sbc1.sip.contoso.com avant d’inscrire le nom de domaine, vous obtiendrez le message d’erreur suivant : « impossible d’utiliser le domaine «sbc1.sip.contoso.com » tel qu’il n’a pas été configuré pour ce client».
Après avoir ajouté le nom de domaine, vous devez également créer un utilisateur avec UPN user@sip.contoso.com et attribuer une licence d’équipe. Il peut s’écouler jusqu’à 24 heures pour pouvoir mettre en service le nom de domaine après son ajout aux domaines de votre client, un utilisateur avec un nouveau nom est créé et une licence lui est affectée. 

Il est possible qu’une entreprise puisse avoir plusieurs espaces d’adresse SIP au sein d’un client. Par exemple, une société peut avoir contoso.com en tant qu’espace d’adressage SIP et fabrikam.com comme second espace d’adressage SIP. Certains utilisateurs ont l’adresse user@contoso.com et certains utilisateurs ont l’adresse user@fabrikam.com. 

Le SBC a uniquement besoin d’un nom de domaine complet et peut faire service aux utilisateurs de tout espace d’adresse dans le client couplé. Par exemple, un SBC doté du nom sbc1.contoso.com peut recevoir et envoyer le trafic RTC pour les utilisateurs disposant d’adresses user@contoso.com et user@fabrikam.com tant qu’ils sont enregistrés dans le même client.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificat de confiance public pour l’SBC

Microsoft vous recommande de demander le certificat pour la SBC en générant une demande de signature de certification (CSR). Pour obtenir des instructions spécifiques sur la génération d’un CSR pour une SBC, voir les instructions ou la documentation d’interconnexion fournie par vos fournisseurs d’SBC. 

  > [!NOTE]
  > La plupart des autorités de certification doivent avoir une taille de clé privée d’au moins 2048. Gardez à l’esprit ce qui suit lors de la génération du conseiller.

Le certificat doit contenir le nom de domaine complet de l’SBC dans les champs objet, nom usuel ou nom de substitution de l’objet.

Par ailleurs, le routage direct prend en charge un caractère générique dans le SAN et le caractère générique doit se conformer au standard [RFC http sur TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Par exemple, l’utilisation \*de. contoso.com dans le San, qui correspondait à l’élément de nom de domaine complet SBC SBC.contoso.com, mais ne correspondait pas à SBC.test.contoso.com.

Le certificat doit être généré par l’une des autorités de certification racines suivantes :

- AffirmTrust
- Racine de l’autorité de certification externe AddTrust
- Certificat racine de CyberTrust Baltimore
- Buypass
- Cybertrust
- Autorité de certification principale publique de classe 3
- Comodo de l’autorité de certification racine sécurisée
- Deutsche Telekom 
- Autorité de certification racine globale DigiCert
- CA racine EV haute garantie DigiCert
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- VeriSign, Inc. 
- SSL.com
- Starfield
- Racine de l’application mobile Symantec entreprise pour Microsoft 
- SwissSign
- Autorité de certification Thawte d’horodatage
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft travaille actuellement à l’ajout d’autorités de certification basées sur les demandes des clients. 

## <a name="sip-signaling-fqdns"></a>Signalisation SIP : noms de domaine complets 

Le routage direct est fourni dans les environnements Office 365 suivants :
- Office 365
- GCC Office 365
- Office 365 (GCC High)
- Office 365 DoD

Apprenez-en davantage sur [Office 365 et les environnements gouvernementaux des États-Unis](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Environnements Office 365 et Office 365 GCC

Le point de connexion pour le routage direct est le trois noms de domaine complets suivants :

- **SIP.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) global, doit d’abord être essayé. Lorsque le SBC envoie une demande pour résoudre ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de noms principal Azure attribué à l’SBC. Cette affectation est basée sur les métriques de performance des centres de donnes et de proximité géographique de l’SBC. L’adresse IP renvoyée correspond au FQDN principal.
- **sip2.pstnhub.Microsoft.com** -nom de domaine complet (FQDN) : il correspond à la deuxième région de priorité.
- nom de domaine complet (FQDN) **sip3.pstnhub.Microsoft.com** : il correspond géographiquement à la troisième région de priorité.

Il est nécessaire de placer ces trois noms de domaine complets dans l’ordre suivant :

- Offrir une plus meilleure version (moins chargée et la plus proche du centre de divertissement SBC attribué en interrogeant le premier nom de domaine complet).
- Faire basculer lorsque la connexion à partir d’un SBC est établie à un centre de donne-établi qui rencontre un problème temporaire. Pour plus d’informations, consultez la section [mécanisme de basculement](#failover-mechanism-for-sip-signaling) ci-dessous.  

Les noms de domaine complets – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com et sip3.pstnhub.microsoft.com, sont résolus à l’une des adresses IP suivantes :

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip-all.pstnhub.microsoft.com est résolu sur toutes les adresses IP suivantes. 


### <a name="office-365-gcc-dod-environment"></a>Environnement DoD DoD dans Office 365

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**SIP.pstnhub.DoD.Teams.Microsoft.us** : FQDN global. Comme l’environnement Office 365 DoD existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.

Le nom de domaine complet (FQDN sip.pstnhub.dod.teams.microsoft.us) sera résolu vers l’une des adresses IP suivantes :

- 52.127.64.33
- 52.127.68.34

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us est résolu sur toutes les adresses IP suivantes. 

### <a name="office-365-gcc-high-environment"></a>Environnement de grande qualité dans Office 365

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**SIP.pstnhub.gov.Teams.Microsoft.us** : FQDN global. Dans la mesure où l’environnement de grande qualité n’existe qu’aux centres de données américains, il n’y a pas de noms de domaine complets secondaires et tertiaires.

Le nom de domaine complet (FQDN sip.pstnhub.gov.teams.microsoft.us) sera résolu vers l’une des adresses IP suivantes :

- 52.127.88.59
- 52.127.92.64

Pour autoriser le trafic entrant et sortant vers et à partir de l’adresse de signalisation, vous devez ouvrir les ports pour toutes ces adresses IP sur votre pare-feu.  Si votre pare-feu prend en charge les noms DNS, le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us est résolu sur toutes les adresses IP suivantes. 

## <a name="sip-signaling-ports"></a>Signalisation SIP : ports

Vous devez utiliser les ports suivants pour les environnements Office 365 dans lesquels le routage direct est disponible :
- Office 365
- GCC Office 365
- Office 365 (GCC High)
- Office 365 DoD

|**Trafic**|**De**|**À**|**Port source**|**Port de destination**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024 – 65535|Défini sur le SBC (pour Office 365 (au port de DoD de la France uniquement) 5061 doit être utilisé)|
SIP/TLS|SBC|Proxy SIP|Définie sur l’SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mécanisme de basculement pour la signalisation SIP

L’SBC crée une requête DNS pour résoudre sip.pstnhub.microsoft.com. Le centre de donnees principal est sélectionné en fonction de l’emplacement de l’SBC et des métriques de performances du centre de donnees. Si le centre de donnes principal rencontre un problème, le SBC essaiera le sip2.pstnhub.microsoft.com, qui se résout au deuxième centre de noms attribué et, dans le cas rares, que les centres de noms dans deux régions ne sont pas disponibles, l’SBC tente de relancer le nom de domaine complet (sip3.pstnhub.microsoft.com), qui fournit l’adresse IP du troisième Datacenter.

Le tableau ci-dessous résume les relations entre les centres de donneaux principal, secondaire et tertiaire :

|**Si le centre de donnees principal est**|**EMEA**|**NOAM**|**RÉGIONS**|
|:--- |:--- |:--- |:--- |
|Centre de la secondaire (sip2.pstnhub.microsoft.com)|Nous|COMMUNAUTAIRES|Nous|
|Le troisième centre de sip3.pstnhub.microsoft.com|RÉGIONS|RÉGIONS|COMMUNAUTAIRES|
|||||

## <a name="media-traffic-port-ranges"></a>Trafic multimédia : plages de ports
Notez que les conditions suivantes s’appliquent si vous souhaitez déployer le routage direct sans dérivation multimédia. Pour connaître la configuration requise pour le pare-feu, consultez [la rubrique planification pour le contournement du média avec le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).



Le trafic de média est acheminé vers et à partir d’un service distinct dans le Cloud Microsoft. La plage d’adresses IP pour le trafic multimédia se présente comme suit.

### <a name="office-365-and-office-365-gcc-environments"></a>Environnements Office 365 et Office 365 GCC

- 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Environnement DoD DoD dans Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Environnement de grande qualité dans Office 365

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Plage de ports (applicable à tous les environnements)
Le tableau suivant indique la portée de port des processeurs multimédias : 

|**Trafic**|**De**|**À**|**Port source**|**Port de destination**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processeur de média|SBC|49152 – 53247|Définie sur l’SBC|
|UDP/SRTP|SBC|Processeur de média|Définie sur l’SBC|49152 – 53247|

  > [!NOTE]
  > Microsoft recommande au moins deux ports par appel simultané sur l’SBC.


## <a name="media-traffic-media-processors-geography"></a>Trafic multimédia : géographie pour les processeurs multimédias

Le trafic multimédia passe par des composants appelés processeurs multimédias. Les processeurs multimédias sont placés dans les mêmes centres de fichiers que les proxys SIP. Par ailleurs, il existe d’autres processeurs multimédias pour optimiser le flux multimédia. Par exemple, il n’y a pas de composant proxy SIP dès maintenant en Australie (le SIP est transmis via Singapour ou Hong Kong), mais nous avons le processeur média en Australie. La nécessité d’utiliser les processeurs multimédias localement dépend de la latence que nous utilisons en envoyant le trafic longue distance (par exemple, de l’Australie à Singapour ou à Hong Kong). En temps réel, il n’y a pas de réponse à Hong Kong ou à Singapour pour garantir une qualité d’appel optimale pour le trafic SIP en temps réel.

Emplacement des processeurs multimédias :

Emplacements dans lesquels les composants proxy SIP et processeur multimédia sont déployés :
- Les États-Unis (2 aux centres des États-Unis et aux États-Unis)
- Europe (les centres de centres d’Amsterdam et de Dublin)
- Asie des centres de reversions de Singapour et de Hong Kong

Emplacements dans lesquels seuls les processeurs multimédias sont déployés (flux SIP via le centre de média le plus proche indiqué ci-dessus) :
- Japon (JP East et West)
- Australie (datacenters au-orientale et West)




## <a name="media-traffic-codecs"></a>Trafic multimédia : codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Jambe entre le processeur de médias SBC et Cloud ou le client Microsoft Teams.
S’applique aux cas de contournement de média et de non-contournement.

L’interface de routage directe sur la jambe entre le contrôleur de bordure de session et le processeur de média Cloud (sans contournement de média), ou entre le client teams et l’SBC (si le contournement de média est activé) peut utiliser les codecs suivants :

- Contournement non multimédia (SBC pour le processeur de média Cloud) : soie, G. 711, G. 722, G. 729
- Contournement multimédia (SBC vers le client Teams) : soie, G. 711, G. 722, G. 729

Vous pouvez forcer l’utilisation du codec spécifique sur le contrôleur de bordure de session en excluant les codecs indésirables de l’offrant.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg entre le client Microsoft teams et le processeur de média Cloud
S’applique uniquement aux cas de contournement non multimédia. Par le biais du contournement du média, le média multimédia passe directement entre le client teams et l’SBC.

Sur la jambe entre le processeur Cloud Cloud et le client Microsoft Teams, la soie ou G. 722 est utilisée. Le choix du codec sur cette jambe repose sur les algorithmes Microsoft, qui prennent en compte plusieurs paramètres. 


## <a name="supported-session-border-controllers-sbcs"></a>Contrôleurs de bordure de session pris en charge (SBCs)

Microsoft ne prend en charge que la certification SBCs pour jumeler le routage direct. Dans la mesure où Enterprise Voice est essentiel pour les entreprises, Microsoft exécute des tests intensifs avec l’option SBCs sélectionnée et utilise les fournisseurs de SBC pour vérifier la compatibilité de ces deux systèmes. 

Les appareils qui ont été validés apparaissent comme certifiés pour le routage direct de teams. Les appareils certifiés sont assurés de fonctionner dans tous les scénarios. 

Pour plus d’informations sur les éléments SBCs pris en charge, voir [liste des contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Voir aussi

[Configurer le routage direct](direct-routing-configure.md)
