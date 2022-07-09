---
title: Planifier le routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Découvrez comment le routage direct Microsoft vous permet de connecter un contrôleur de frontière de session (SBC) fourni par le client pris en charge au système téléphonique.
ms.openlocfilehash: fd5f2733fc11511e6cfc2e646c0bb78aff26b522
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695057"
---
# <a name="plan-direct-routing"></a>Planifier le routage direct

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du routage direct, sa planification et son déploiement : [Routage direct dans Microsoft Teams](https://aka.ms/teams-direct-routing)

Le routage direct vous permet de connecter un contrôleur de frontière de session (SBC) pris en charge et fourni par le client au système téléphonique. Avec cette fonctionnalité, vous pouvez configurer la connectivité du réseau téléphonique commuté (RTC) locale avec le client Microsoft Teams, comme illustré dans le diagramme suivant : 

![Diagramme montrant la configuration de la connectivité RTC locale.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration de la connectivité RTC locale avec le client Microsoft Teams")

  > [!NOTE]
  > Skype Entreprise Online vous permet également d’associer un SBC fourni par le client, mais cela nécessite un déploiement Skype Entreprise Server local ou une édition spéciale de Skype Entreprise, appelée Cloud Connector, entre SBC et Microsoft Cloud. Ce scénario est appelé voix hybride. En revanche, le routage direct permet une connexion directe entre le SBC pris en charge et le cloud Microsoft.

> [!Important]
> Cloud Connector Edition prendra sa retraite le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau de téléphonie local à Teams à l’aide du [routage direct](direct-routing-landing-page.md). 

Avec le routage direct, vous pouvez connecter votre SBC à presque n’importe quelle jonction de téléphonie ou vous connecter à des équipements RTC tiers. Le routage direct vous permet de : 

- Utilisez pratiquement n’importe quelle jonction RTC avec le système téléphonique. 

- Configurez l’interopérabilité entre les équipements de téléphonie appartenant au client, tels qu’un pbX (Private Branch Exchange) tiers, des appareils analogiques et Teams.

Microsoft propose également des solutions vocales tout-dans-le-cloud, telles que le forfait d’appels. Toutefois, une solution de voix hybride peut être la meilleure pour votre organisation si : 

- Le forfait d’appels Microsoft n’est pas disponible dans votre pays. 

- Votre organisation nécessite une connexion à des appareils analogiques tiers, des centres d’appels, et ainsi de suite. 

- Votre organisation a un contrat existant avec un opérateur RTC.

Le routage direct prend également en charge les utilisateurs disposant de la licence supplémentaire pour le plan d’appel Microsoft. Pour plus d’informations, consultez [Systèmes téléphoniques et forfaits d’appels](calling-plan-landing-page.md). 

Avec le routage direct, lorsque les utilisateurs participent à une conférence planifiée, le numéro de connexion est fourni par le service d’audioconférence Microsoft, qui nécessite une licence appropriée.  Lors de la numérotation, le service d’audioconférence Microsoft place l’appel à l’aide des fonctionnalités d’appel en ligne, ce qui nécessite une licence appropriée. (Notez que si un utilisateur n’a pas de licence d’audioconférence Microsoft, l’appel est acheminé via le routage direct.) Pour plus d’informations, consultez [Réunions en ligne avec Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
La planification de votre déploiement du routage direct est essentielle à une implémentation réussie. Cet article décrit les exigences en matière d’infrastructure et de licence et fournit des informations sur la connectivité SBC : 

- [Conditions requises pour l'infrastructure](#infrastructure-requirements)
- [Licences et autres exigences](#licensing-and-other-requirements)
- [Noms de domaine SBC](#sbc-domain-names)
- [Certificat approuvé public pour le SBC](#public-trusted-certificate-for-the-sbc)
- [Signalisation SIP : noms de domaine complets](#sip-signaling-fqdns)
- [Signalisation SIP : ports](#sip-signaling-ports)
- [Trafic multimédia : plages de ports](#media-traffic-port-ranges)
- [Contrôleurs de frontière de session (SBC) pris en charge](#supported-session-border-controllers-sbcs)

Pour plus d’informations sur la configuration du routage direct, consultez [Configurer le routage direct](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Conditions d’infrastructure requises
Les exigences d’infrastructure pour les SBC, domaines et autres exigences de connectivité réseau prises en charge pour déployer le routage direct sont répertoriées dans le tableau suivant :  

|Configuration requise pour l’infrastructure|Vous avez besoin des éléments suivants :|
|:--- |:--- |
|Contrôleur de bordure de session (SBC)|SBC pris en charge. Pour plus d’informations, consultez [SBC pris en charge](#supported-session-border-controllers-sbcs).|
|Jonctions de téléphonie connectées au SBC|Une ou plusieurs jonctions de téléphonie connectées au SBC. D’une part, le SBC se connecte au système téléphonique via le routage direct. Le SBC peut également se connecter à des entités de téléphonie tierces, telles que des PBX, des adaptateurs de téléphonie analogique, etc. Toute option de connectivité RTC connectée au SBC fonctionnera. (Pour la configuration des jonctions RTC au SBC, reportez-vous aux fournisseurs SBC ou aux fournisseurs de jonctions.)|
|Organisation Microsoft 365|Une organisation Microsoft 365 que vous utilisez pour héberger vos utilisateurs Microsoft Teams, ainsi que la configuration et la connexion au SBC.|
|Bureau d’enregistrement d’utilisateurs|L’utilisateur doit être hébergé dans Microsoft 365.<br/>Si votre entreprise dispose d’un environnement Skype Entreprise ou Lync local avec une connectivité hybride à Microsoft 365, vous ne pouvez pas activer la voix dans Teams pour un utilisateur hébergé localement.<br/><br/>Pour vérifier le bureau d’enregistrement d’un utilisateur, utilisez l’applet de commande PowerShell en ligne Skype Entreprise suivante :<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>La sortie de l’applet de commande doit afficher :<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domaines|Un ou plusieurs domaines ajoutés à vos organisations Microsoft 365 ou Office 365.<br/><br/>Notez que vous ne pouvez pas utiliser le domaine par défaut, \*.onmicrosoft.com, qui est automatiquement créé pour votre locataire.<br/><br/>Pour afficher les domaines, vous pouvez utiliser l’applet de commande PowerShell en ligne Skype Entreprise suivante :<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Pour plus d’informations sur les domaines et les organisations Microsoft 365 ou Office 365, consultez faq sur [les domaines](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Adresse IP publique du SBC|Adresse IP publique qui peut être utilisée pour se connecter au SBC. En fonction du type de SBC, le SBC peut utiliser NAT.|
|Nom de domaine complet (FQDN) pour le SBC|Nom de domaine complet pour le SBC, où la partie domaine du nom de domaine complet est l’un des domaines inscrits dans votre organisation Microsoft 365 ou Office 365. Pour plus d’informations, consultez [les noms de domaine SBC](#sbc-domain-names).|
|Entrée DNS publique pour le SBC |Entrée DNS publique mappant le nom de domaine complet SBC à l’adresse IP publique. |
|Certificat approuvé public pour le SBC |Certificat pour le SBC à utiliser pour toutes les communications avec le routage direct. Pour plus d’informations, consultez [le certificat approuvé public pour le SBC](#public-trusted-certificate-for-the-sbc).|
|Points de connexion pour le routage direct |Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :<br/><br/>`sip.pstnhub.microsoft.com` – Le nom de domaine complet global doit être essayé en premier.<br/>`sip2.pstnhub.microsoft.com` – Nom de domaine complet secondaire, mappé géographiquement à la deuxième région prioritaire.<br/>`sip3.pstnhub.microsoft.com` – Nom de domaine complet tertiaire, mappé géographiquement à la troisième région prioritaire.<br/><br/>Pour plus d’informations sur les exigences de configuration, consultez [SIP Signaling: FQDNs](#sip-signaling-fqdns).|
|Adresses IP et ports de pare-feu pour le média de routage direct |Le SBC communique avec les services suivants dans le cloud :<br/><br/>Proxy SIP, qui gère la signalisation<br/>Processeur multimédia, qui gère le média, sauf lorsque le contournement du média est activé<br/><br/>Ces deux services ont des adresses IP distinctes dans Microsoft Cloud, décrites plus loin dans ce document.<br/><br/>Pour plus d’informations, consultez la [section Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) dans [les URL et les plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Profil de transport multimédia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Adresses IP et ports de pare-feu pour les médias Microsoft Teams |Pour plus d’informations, consultez [LES URL et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licences et autres exigences 

Les utilisateurs du routage direct doivent disposer des licences suivantes affectées dans Microsoft 365 : 

- Microsoft Phone System
- Microsoft Teams + Skype Entreprise Plan 2, s’il est inclus dans les licences
- Audioconférence Microsoft (lisez les notes et le paragraphe ci-dessous pour obtenir des exemples spécifiques sur le moment où cette licence est requise.)

> [!NOTE]
> Skype Entreprise plan ne doit pas être supprimé d’un contrat de licence où il est inclus. 
> 
> [!IMPORTANT]
> Les utilisateurs GCC High et DoD doivent désactiver toutes les licences d’audioconférence incluses dans G5 et attendre d’activer l’audioconférence jusqu’à ce que le routage direct ait été entièrement configuré. Les utilisateurs doivent disposer de numéros de téléphone rendez-vous configurés et d’un pavé de numérotation opérationnel avant d’activer les licences d’audioconférence. Pour plus d’informations, consultez [audioconférence avec routage direct pour GCC High et DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) .


> [!IMPORTANT]
>  Si vous souhaitez ajouter des participants externes à des réunions planifiées, soit en les composeant, soit en leur fournissant le numéro d’accès, la licence d’audioconférence est requise.
> Pour GCC High et DoD, n’affectez pas de licence d’audioconférence pour les utilisateurs G5. Pour les utilisateurs G3, n’affectez pas de licence d’audioconférence tant que le routage direct n’est pas entièrement configuré et que l’utilisateur dispose d’un pavé de numérotation fonctionnel.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Réaffectation des appels ad hoc et licence d’audioconférence

Un utilisateur Teams peut démarrer un appel Teams-to-PSTN ou Teams-to-Teams en un seul appel et y ajouter un participant RTC. Ce scénario est appelé conférence ad hoc. Le chemin d’accès de l’appel dépend du fait que l’utilisateur qui effectue l’escalade de l’appel dispose ou non d’une licence d’audioconférence Microsoft :

- **Si une licence d’audioconférence Microsoft est attribuée à l’utilisateur Teams qui effectue l’escalade de l’appel**, l’escalade se produit via le service d’audioconférence Microsoft. Le participant RTC distant qui est invité à l’appel existant reçoit une notification concernant l’appel entrant et voit le numéro du pont Microsoft affecté à l’utilisateur Teams qui a initié l’escalade.

- **Si la licence d’audioconférence Microsoft n’est pas attribuée à l’utilisateur Teams qui effectue l’escalade de l’appel**, l’escalade se produit via un contrôleur de bordure de session connecté à l’interface de routage direct. Le participant RTC distant qui est invité à l’appel reçoit une notification concernant l’appel entrant et voit le numéro de l’utilisateur Teams qui a initié l’escalade. Le SBC spécifique utilisé pour l’escalade est défini par la stratégie de routage de l’utilisateur. 

Vous devez vous assurer que les éléments suivants sont les suivants :
 
- CsOnlineVoiceRoutingPolicy est affecté à l’utilisateur. 

- Autoriser l’appel privé est activé au niveau du locataire pour Microsoft Teams. 

Le routage direct prend également en charge les utilisateurs titulaires d’une licence pour le plan d’appel Microsoft. Le système téléphonique avec forfait d’appels peut acheminer certains appels à l’aide de l’interface de routage direct. Toutefois, les numéros de téléphone des utilisateurs doivent être acquis en ligne ou portés vers Microsoft.  

Le mélange du plan d’appel et de la connectivité de routage direct pour le même utilisateur est facultatif, mais peut être utile. Par exemple, lorsque l’utilisateur se voit attribuer un plan d’appel Microsoft, mais souhaite acheminer certains appels à l’aide du SBC. L’un des scénarios les plus courants est les appels à des PBX tiers.  Avec les PBX tiers, tous les appels, à l’exception des appels aux téléphones connectés à ce PBX, sont routés à l’aide du plan d’appel Microsoft, mais les appels aux téléphones connectés à des PBX tiers sont acheminés vers le SBC, et restent donc au sein du réseau d’entreprise et non du RTC. 

Pour plus d’informations sur les licences système téléphonique, consultez [Tirer le meilleur parti des options Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) et [Plan](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) et [des licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Points de terminaison pris en charge 

Vous pouvez utiliser comme point de terminaison :

- N’importe quel client Teams. 

- Téléphones de zone commune. Voir [Configurer les téléphones de zone commune pour Microsoft Teams](./set-up-common-area-phones.md). Vous n’avez pas besoin d’une licence de forfait d’appels lors de la configuration d’un téléphone de zone commune avec routage direct.

- Skype Entreprise téléphones 3PIP. Consultez [la prise en charge des téléphones Skype Entreprise (3PIP) avec Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Noms de domaine SBC

Le nom de domaine SBC doit être de l’un des noms enregistrés dans les domaines du locataire. Vous ne pouvez pas utiliser le \*locataire .onmicrosoft.com pour le nom de domaine complet du SBC.

Le tableau suivant montre des exemples de noms DNS inscrits pour le locataire, si le nom peut être utilisé comme nom de domaine complet pour le SBC, et des exemples de noms de nom de domaine complet valides :

|Nom DNS|Peut être utilisé pour le nom de domaine complet SBC|Exemples de noms de nom de domaine complet|
|:--- |:--- |:--- |
contoso.com|Oui|**Noms valides :**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Non|L’utilisation de domaines *.onmicrosoft.com n’est pas prise en charge pour les noms SBC

Supposons que vous souhaitez utiliser un nouveau nom de domaine. Par exemple, votre locataire a contoso.com en tant que nom de domaine inscrit dans votre locataire, et vous souhaitez utiliser sbc1.sip.contoso.com. Avant de pouvoir associer un SBC au nom sbc1.sip.contoso.com, vous devez inscrire le nom de domaine sip.contoso.com dans les domaines de votre locataire. Si vous essayez d’associer un SBC à sbc1.sip.contoso.com avant d’inscrire le nom de domaine, vous obtenez l’erreur suivante : « Impossible d’utiliser le domaine « sbc1.sip.contoso.com », car il n’a pas été configuré pour ce locataire. »
Après avoir ajouté le nom de domaine, vous devez également créer un utilisateur avec upn user@sip.contoso.com et attribuer une licence Teams. L’approvisionnement complet du nom de domaine peut prendre jusqu’à 24 heures après son ajout aux domaines de votre locataire, la création d’un utilisateur avec un nouveau nom et l’attribution d’une licence à l’utilisateur. 

Il est possible qu’une entreprise ait plusieurs espaces d’adressage SIP dans un locataire. Par exemple, une entreprise peut avoir contoso.com en tant qu’espace d’adressage SIP et fabrikam.com comme deuxième espace d’adressage SIP. Certains utilisateurs ont des user@contoso.com d’adresses et d’autres des user@fabrikam.com d’adresse. 

Le SBC n’a besoin que d’un seul nom de domaine complet et peut servir les utilisateurs à partir de n’importe quel espace d’adressage dans le locataire jumelé. Par exemple, un SBC portant le nom sbc1.contoso.com peut recevoir et envoyer le trafic RTC pour les utilisateurs ayant des adresses user@contoso.com et user@fabrikam.com tant que ces espaces d’adressage SIP sont inscrits dans le même locataire.  

 > [!NOTE]
 > Le nom de domaine complet SBC dans Azure Communication Services routage direct doit être différent du nom de domaine complet SBC dans le routage direct Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificat approuvé public pour le SBC

Microsoft vous recommande de demander le certificat pour le SBC en générant une demande de signature de certification (CSR). Pour obtenir des instructions spécifiques sur la génération d’une RSE pour un SBC, reportez-vous aux instructions ou à la documentation d’interconnexion fournies par vos fournisseurs SBC. 

> [!NOTE]
> La plupart des autorités de certification exigent que la taille de clé privée soit au moins 2048. Gardez cela à l’esprit lors de la génération de la RSE.

Le certificat doit avoir le nom de domaine complet (FQDN) SBC comme nom commun (CN) ou le champ SAN (Subject Alternative Name).

Sinon, le routage direct prend en charge un caractère générique dans le cn et/ou san, et le caractère générique doit être conforme au [protocole HTTP RFC standard sur TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Par exemple, utilisez \*.contoso.com qui correspondrait au sbc.contoso.com du nom de domaine complet SBC, mais qui ne correspondrait pas à sbc.test.contoso.com.

L’interface SIP de routage direct approuve uniquement les certificats signés par des autorités de certification qui font partie du programme de certificat racine approuvé Microsoft. Assurez-vous que votre certificat SBC est signé par une autorité de certification qui fait partie du programme et que l’extension Utilisation étendue de la clé (EKU) de votre certificat inclut l’authentification serveur.
En savoir plus : [Exigences du programme - Programme racine approuvé Microsoft](/security/trusted-root/program-requirements)
  
[Liste de certificats d’autorité de certification incluse](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Pour le routage direct dans Office 365 environnements GCCH et DoD, le certificat doit être généré par l’une des autorités de certification racines suivantes :

- Autorité de certification racine globale DigiCert
- DigiCert High Assurance EV Root CA

> [!NOTE]
> Si la prise en charge de MTLS (Mutual TLS) est activée pour la connexion Teams sur le SBC, vous devez installer les certificats Baltimore CyberTrust Root et DigiCert Global Root G2 dans le magasin racine approuvé SBC du contexte TLS Teams. (Cela est dû au fait que les certificats de service Microsoft utilisent l’un de ces deux certificats racines.) Pour télécharger ces certificats racines, consultez [Office 365 chaînes de chiffrement](/microsoft-365/compliance/encryption-office-365-certificate-chains). Pour plus d’informations, consultez Les modifications apportées aux [certificats TLS Office](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Signalisation SIP : noms de domaine complets 

Le routage direct est proposé dans les environnements suivants :

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

En savoir plus sur [les environnements Office 365 et le gouvernement des États-Unis](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Environnements Microsoft 365, Office 365 et Office 365 GCC

Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :

- **sip.pstnhub.microsoft.com** – Nom de domaine complet global – doit d’abord être essayé. Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure retournent une adresse IP pointant vers le centre de données Azure principal affecté au SBC. L’affectation est basée sur les métriques de performances des centres de données et la proximité géographique du SBC. L’adresse IP retournée correspond au nom de domaine complet principal.

- **sip2.pstnhub.microsoft.com** – Nom de domaine complet secondaire – mappe géographiquement à la deuxième région prioritaire.

- **sip3.pstnhub.microsoft.com** – Nom de domaine complet tertiaire – mappe géographiquement à la troisième région prioritaire.

Le placement de ces trois noms de domaine complets dans l’ordre est nécessaire pour :

- Offrez une expérience optimale (moins chargée et la plus proche du centre de données SBC affecté en interrogeant le premier nom de domaine complet).

- Fournissez un basculement lorsque la connexion à partir d’un SBC est établie à un centre de données qui rencontre un problème temporaire. Pour plus d’informations, consultez [le mécanisme de basculement](#failover-mechanism-for-sip-signaling) ci-dessous.  

Les noms de domaine complets (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com et sip3.pstnhub.microsoft.com) sont résolus en adresses IP à partir des sous-réseaux suivants :

- 52.112.0.0/14
- 52.120.0.0/14

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

### <a name="office-gcc-dod-environment"></a>Environnement Office GCC DoD

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.dod.teams.microsoft.us** : nom de domaine complet global. Étant donné que l’environnement DoD Office 365 n’existe que dans les centres de données des États-Unis, il n’existe aucun nom de domaine complet secondaire et tertiaire.

Le sip.pstnhub.dod.teams.microsoft.us FQDN est résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.64.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.gov.teams.microsoft.us** : nom de domaine complet global. Étant donné que l’environnement GCC High n’existe que dans les centres de données des États-Unis, il n’existe aucun nom de domaine complet secondaire et tertiaire.

Le sip.pstnhub.gov.teams.microsoft.us FQDN est résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.88.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

## <a name="sip-signaling-ports"></a>Signalisation SIP : ports

Vous devez utiliser les ports suivants pour les environnements Microsoft 365 ou Office 365 où le routage direct est proposé :

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Trafic|De|À|Port source|Port de destination|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Défini sur le SBC (pour Office 365 GCC High/DoD, seul le port 5061 doit être utilisé)|
SIP/TLS|SBC|SIP Proxy|Défini sur le SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mécanisme de basculement pour la signalisation SIP

Le SBC effectue une requête DNS pour résoudre sip.pstnhub.microsoft.com. En fonction de l’emplacement SBC et des métriques de performances du centre de données, le centre de données principal est sélectionné. Si le centre de données principal rencontre un problème, le SBC tente l’sip2.pstnhub.microsoft.com, qui se résout en deuxième centre de données affecté et, dans les rares cas où les centres de données de deux régions ne sont pas disponibles, le SBC tente à nouveau le dernier nom de domaine complet (sip3.pstnhub.microsoft.com), qui fournit l’adresse IP du centre de données tertiaire.

Le tableau ci-dessous récapitule les relations entre les centres de données principaux, secondaires et tertiaires :

|Si le centre de données principal est|EMEA|NOAM|ASIE|
|:--- |:--- |:--- |:--- |
|Centre de données secondaire (sip2.pstnhub.microsoft.com)|NOUS|UE|NOUS|
|Centre de données tertiaire (sip3.pstnhub.microsoft.com)|ASIE|ASIE|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Trafic multimédia : plages de ports
Notez que les exigences ci-dessous s’appliquent si vous souhaitez déployer le routage direct sans contournement multimédia. Pour les exigences de pare-feu pour le contournement des médias, reportez-vous à [Planifier le contournement multimédia avec routage direct](./direct-routing-plan-media-bypass.md).

Le trafic multimédia circule vers et depuis un service distinct dans le cloud Microsoft. Les plages d’adresses IP pour le trafic multimédia sont les suivantes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Environnements Microsoft 365, Office 365 et Office 365 GCC

- 52.112.0.0/14 (adresses IP comprises entre 52.112.0.1 et 52.115.255.254).
- 52.120.0.0/14 (adresses IP comprises entre 52.120.0.1 et 52.123.255.254).

### <a name="office-365-dod-environment"></a>environnement DoD Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Plage de ports (applicable à tous les environnements)
La plage de ports des processeurs multimédias est indiquée dans le tableau suivant : 

|Trafic|De|À|Port source|Port de destination|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processeur multimédia|SBC|3478-3481 et 49152 – 53247|Défini sur le SBC|
|UDP/SRTP|SBC|Processeur multimédia|Défini sur le SBC|3478-3481 et 49152 – 53247|

  > [!NOTE]
  > Microsoft recommande au moins deux ports par appel simultané sur le SBC.


## <a name="media-traffic-media-processors-geography"></a>Trafic multimédia : zone géographique des processeurs multimédias

Le trafic multimédia transite par des composants appelés processeurs multimédias. Les processeurs multimédias sont placés dans les mêmes centres de données que les proxys SIP :

- NOAM (USA Centre Sud, deux centres de données USA Ouest et USA Est)
- Europe (centres de données Royaume-Uni Sud, France Centre, Amsterdam et Dublin)
- Asie (centre de données de Singapour)
- Japon (centres de données JP Est et Ouest)
- Australie (centres de données AU Est et Sud-Est)
- LATAM (Brésil Sud)
- Afrique (Afrique du Sud Nord)

## <a name="media-traffic-codecs"></a>Trafic multimédia : Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Étape entre le client SBC et Cloud Media Processor ou Microsoft Teams

S’applique à la fois aux cas de contournement multimédia et aux cas de non-contournement.

L’interface de routage direct sur le tronçon entre le contrôleur de bordure de session et le processeur multimédia cloud (sans contournement multimédia) ou entre le client Teams et le SBC (si la déviation du trafic multimédia est activée) peut utiliser les codecs suivants :

- Contournement non multimédia (SBC to Cloud Media Processor) : SILK, G.711, G.722, G.729
- Media Bypass (client SBC to Teams) : SILK, G.711, G.722, G.729

Vous pouvez forcer l’utilisation du codec spécifique sur le contrôleur de bordure de session en excluant les codecs indésirables de l’offre.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Étape entre le client Microsoft Teams et le processeur multimédia cloud

S’applique uniquement au cas de contournement non multimédia. Avec media bypass, le média circule directement entre le client Teams et le SBC.

Sur le tronçon entre le processeur multimédia cloud et le client Microsoft Teams, SILK ou G.722 est utilisé. Le choix du codec sur cette étape est basé sur des algorithmes Microsoft, qui prennent en compte plusieurs paramètres. 

  > [!NOTE]
  > Le ciblage multimédia n’est pas pris en charge. Lors d’un appel de routage direct, si le SBC envoie une nouvelle adresse IP multimédia au routage direct Teams, bien qu’il soit négocié dans la signalisation SIP, le média n’est jamais envoyé à la nouvelle adresse IP à partir du routage direct Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Contrôleurs de frontière de session (SBC) pris en charge

Microsoft prend uniquement en charge les SBC certifiés à associer au routage direct. Étant donné que Voix Entreprise est critique pour les entreprises, Microsoft exécute des tests intensifs avec les SBC sélectionnés et collabore avec les fournisseurs SBC pour s’assurer que les deux systèmes sont compatibles. 

Les appareils qui ont été validés sont répertoriés comme certifiés pour le routage direct Teams. Les appareils certifiés fonctionnent dans tous les scénarios. 

Pour plus d’informations sur les SBC prises en charge, consultez [Contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Voir aussi

[Configurer le routage direct](direct-routing-configure.md)
