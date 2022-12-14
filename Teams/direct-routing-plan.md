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
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Découvrez comment Microsoft routage direct vous permet de connecter un contrôleur de frontière de session (SBC) fourni par le client pris en charge au système téléphonique.
ms.openlocfilehash: 811115c23d88ff3ce1b7fa6af8f8757afb33fecf
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392324"
---
# <a name="plan-direct-routing"></a>Planifier le routage direct

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du routage direct, comment le planifier et comment le déployer : [Routage direct dans Microsoft Teams](https://aka.ms/teams-direct-routing)

Le routage direct vous permet de connecter un contrôleur de frontière de session (SBC) fourni par le client au système téléphonique. Avec cette fonctionnalité, vous pouvez configurer la connectivité RTC (Public Switched Telephone Network) local avec Microsoft client Teams, comme illustré dans le diagramme suivant : 

![Diagramme montrant la configuration de la connectivité RTC locale.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration de la connectivité RTC locale avec Microsoft client Teams")

  > [!NOTE]
  > Skype Entreprise Online vous permet également de coupler un SBC fourni par le client, mais cela nécessite un déploiement Skype Entreprise Server local ou une édition spéciale de Skype Entreprise, appelée Cloud Connector, entre le SBC et le cloud Microsoft. Ce scénario est appelé voix hybride. En revanche, le routage direct permet une connexion directe entre le SBC pris en charge et le cloud Microsoft.

> [!Important]
> Cloud Connector Edition sera mis hors service le 31 juillet 2021 avec Skype Entreprise Online. Une fois que votre organisation a effectué la mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide [du routage direct](direct-routing-landing-page.md). 

Avec le routage direct, vous pouvez connecter votre SBC à presque n’importe quelle jonction de téléphonie ou interconnecter avec un équipement RTC tiers. Le routage direct vous permet de : 

- Utilisez pratiquement n’importe quelle jonction RTC avec le système téléphonique. 

- Configurez l’interopérabilité entre l’équipement de téléphonie appartenant au client, tel qu’un pbX tiers, des appareils analogiques et Teams.

Microsoft propose également des solutions vocales tout-dans-le-cloud, telles que forfait d’appels. Toutefois, une solution de voix hybride peut être idéale pour votre organisation dans les cas suivants : 

- Microsoft forfait d’appels n’est pas disponible dans votre pays. 

- Votre organisation nécessite une connexion à des appareils analogiques tiers, des centres d’appels, etc. 

- Votre organisation a un contrat existant avec un opérateur RTC.

Le routage direct prend également en charge les utilisateurs qui disposent de la licence supplémentaire pour le forfait d’appels Microsoft. Pour plus d’informations, consultez [Système téléphonique et forfaits d’appels](calling-plan-landing-page.md). 

Avec le routage direct, lorsque les utilisateurs participent à une conférence planifiée, le numéro de connexion est fourni par Microsoft service d’audioconférence, qui nécessite une licence appropriée.  Lors de la numérotation sortante, le service d’audioconférence Microsoft passe l’appel à l’aide des fonctionnalités d’appel en ligne, ce qui nécessite des licences appropriées. (Notez que si un utilisateur n’a pas de licence d’audioconférence Microsoft, l’appel est acheminé via le routage direct.) Pour plus d’informations, consultez [Réunions en ligne avec Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
La planification de votre déploiement de routage direct est essentielle à la réussite de l’implémentation. Cet article décrit les exigences en matière d’infrastructure et de licence et fournit des informations sur la connectivité SBC : 

- [Conditions requises pour l'infrastructure](#infrastructure-requirements)
- [Licences et autres exigences](#licensing-and-other-requirements)
- [Noms de domaine SBC](#sbc-domain-names)
- [Certificat approuvé public pour le SBC](#public-trusted-certificate-for-the-sbc)
- [Signalisation SIP : noms de domaine complets](#sip-signaling-fqdns)
- [Signalisation SIP : Ports](#sip-signaling-ports)
- [Trafic multimédia : plages de ports](#media-traffic-port-ranges)
- [Contrôleurs de bordure de session (SBC) pris en charge](#supported-session-border-controllers-sbcs)

Pour plus d’informations sur la configuration du routage direct, consultez [Configurer le routage direct](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Conditions d’infrastructure requises
Les exigences d’infrastructure pour les SBC, domaines et autres exigences de connectivité réseau prises en charge pour déployer le routage direct sont répertoriées dans le tableau suivant :  

|Configuration requise pour l’infrastructure|Vous avez besoin des éléments suivants|
|:--- |:--- |
|Contrôleur de bordure de session (SBC)|SBC pris en charge. Pour plus d’informations, consultez [SBC pris en charge](#supported-session-border-controllers-sbcs).|
|Jonctions de téléphonie connectées au SBC|Une ou plusieurs jonctions de téléphonie connectées au SBC. À une extrémité, le SBC se connecte au système téléphonique via le routage direct. Le SBC peut également se connecter à des entités de téléphonie tierces, telles que des PBX, des adaptateurs de téléphonie analogique, etc. Toute option de connectivité RTC connectée au SBC fonctionne. (Pour la configuration des jonctions RTC vers le SBC, reportez-vous aux fournisseurs SBC ou aux fournisseurs de jonctions.)|
|organisation Microsoft 365|Une organisation Microsoft 365 que vous utilisez pour abriter vos utilisateurs Microsoft Teams, ainsi que la configuration et la connexion au SBC.|
|Bureau d’enregistrement d’utilisateurs|L’utilisateur doit être hébergé dans Microsoft 365.<br/>Si votre entreprise dispose d’un environnement local Skype Entreprise ou Lync avec une connectivité hybride à Microsoft 365, vous ne pouvez pas activer la voix dans Teams pour un utilisateur hébergé localement.<br/><br/>Pour vérifier le bureau d’enregistrement d’un utilisateur, utilisez l’applet de commande PowerShell Skype Entreprise Online suivante :<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>La sortie de l’applet de commande doit afficher :<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domaines|Un ou plusieurs domaines ajoutés à vos organisations Microsoft 365 ou Office 365.<br/><br/>Notez que vous ne pouvez pas utiliser le domaine par défaut, \*.onmicrosoft.com, créé automatiquement pour votre locataire.<br/><br/>Pour afficher les domaines, vous pouvez utiliser l’applet de commande PowerShell Skype Entreprise Online suivante :<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Pour plus d’informations sur les domaines et les organisations Microsoft 365 ou Office 365, consultez [FAQ sur les domaines](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Adresse IP publique du SBC|Adresse IP publique qui peut être utilisée pour se connecter au SBC. En fonction du type de SBC, le SBC peut utiliser NAT.|
|Nom de domaine complet (FQDN) pour le SBC|Nom de domaine complet pour le SBC, où la partie domaine du nom de domaine complet est l’un des domaines inscrits dans votre organisation Microsoft 365 ou Office 365. Pour plus d’informations, consultez [Noms de domaine SBC](#sbc-domain-names).|
|Entrée DNS publique pour le SBC |Entrée DNS publique mappant le nom de domaine complet SBC à l’adresse IP publique. |
|Certificat approuvé public pour le SBC |Certificat pour le SBC à utiliser pour toutes les communications avec le routage direct. Pour plus d’informations, consultez [Certificat approuvé public pour le SBC](#public-trusted-certificate-for-the-sbc).|
|Points de connexion pour le routage direct |Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :<br/><br/>`sip.pstnhub.microsoft.com` : le nom de domaine complet global doit d’abord être essayé.<br/>`sip2.pstnhub.microsoft.com` : nom de domaine complet secondaire, mappe géographiquement à la deuxième région de priorité.<br/>`sip3.pstnhub.microsoft.com` – FQDN tertiaire, mappe géographiquement à la troisième région prioritaire.<br/><br/>Pour plus d’informations sur la configuration requise, consultez [Signalisation SIP : FQDN](#sip-signaling-fqdns).|
|Adresses IP et ports de pare-feu pour le support de routage direct |Le SBC communique avec les services suivants dans le cloud :<br/><br/>Proxy SIP, qui gère la signalisation<br/>Processeur multimédia, qui gère les médias, sauf lorsque la déviation du trafic multimédia est activée<br/><br/>Ces deux services ont des adresses IP distinctes dans Microsoft Cloud, décrites plus loin dans ce document.<br/><br/>Pour plus d’informations, consultez la [section Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) dans [URL et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Profil de transport de média|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Adresses IP et ports de pare-feu pour Microsoft média Teams |Pour plus d’informations, consultez [URL et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licences et autres exigences 

Les utilisateurs de routage direct doivent disposer des licences suivantes attribuées dans Microsoft 365 : 

- système téléphonique Microsoft
- Microsoft Teams + Skype Entreprise Plan 2, s’il est inclus dans les licences
- Microsoft audioconférence (Lisez les notes et le paragraphe ci-dessous pour obtenir des exemples spécifiques sur les cas où cette licence est requise.)

> [!NOTE]
> Skype Entreprise Plan ne doit pas être supprimé d’un contrat de licence où il est inclus. 
> 
> [!IMPORTANT]
> Les utilisateurs GCC High et DoD doivent désactiver toute licence d’audioconférence incluse dans G5 et attendre d’activer l’audioconférence jusqu’à ce que le routage direct ait été entièrement configuré. Les utilisateurs doivent disposer de numéros de téléphone d’appel configurés et d’un pavé de numérotation opérationnel avant d’activer les licences d’audioconférence. Pour plus d’informations [, consultez Audioconférence avec routage direct pour GCC High et DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) .


> [!IMPORTANT]
>  Si vous souhaitez ajouter des participants externes à des réunions planifiées, soit en les appelant, soit en fournissant le numéro de connexion, la licence d’audioconférence est requise.
> Pour GCC High et DoD, n’attribuez pas de licence d’audioconférence pour les utilisateurs G5. Pour les utilisateurs G3, n’attribuez pas de licence d’audioconférence tant que le routage direct n’est pas entièrement configuré et que l’utilisateur dispose d’un pavé de numérotation opérationnel.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Réaffectation d’appel ad hoc et licence d’audioconférence

Un utilisateur Teams peut démarrer un appel Teams-à-un Teams-to-PSTN ou Teams-to-Teams et y ajouter un participant RTC. Ce scénario est appelé conférence ad hoc. Le chemin d’accès à l’appel varie selon qu’une licence d’audioconférence Microsoft a été attribuée ou non à l’utilisateur qui effectue l’escalade de l’appel :

- **Si une licence d’audioconférence Microsoft est attribuée à l’utilisateur Teams qui effectue l’escalade de l’appel**, l’escalade se produit via le service d’audioconférence Microsoft. Le participant RTC distant qui est invité à l’appel existant reçoit une notification concernant l’appel entrant et voit le numéro du pont Microsoft affecté à l’utilisateur Teams qui a initié l’escalade.

- **Si l’utilisateur Teams qui escalade l’appel n’a pas la licence d’audioconférence Microsoft affectée**, l’escalade se produit par le biais d’un contrôleur de bordure de session connecté à l’interface de routage direct. Le participant RTC distant qui est invité à l’appel reçoit une notification concernant l’appel entrant et voit le numéro de l’utilisateur Teams qui a initié l’escalade. Le SBC spécifique utilisé pour l’escalade est défini par la stratégie de routage de l’utilisateur. 

Vous devez vérifier ce qui suit :
 
- CsOnlineVoiceRoutingPolicy est attribué à l’utilisateur.

- Autoriser les appels privés est activé au niveau du locataire pour Microsoft Teams.

Le routage direct prend également en charge les utilisateurs disposant d’une licence pour Microsoft forfait d’appels. Le système téléphonique avec forfait d’appels peut acheminer certains appels à l’aide de l’interface de routage direct. Toutefois, les numéros de téléphone des utilisateurs doivent être acquis en ligne ou transférés vers Microsoft.  

La combinaison d’un forfait d’appels et d’une connectivité de routage direct pour le même utilisateur est facultative, mais peut être utile. Par exemple, lorsque l’utilisateur se voit attribuer un Microsoft forfait d’appels, mais qu’il souhaite router certains appels à l’aide du SBC. L’un des scénarios les plus courants est les appels à des PBX tiers.  Avec les PBX tiers, tous les appels, à l’exception des téléphones connectés à ce PBX, sont acheminés à l’aide de Microsoft forfait d’appels, mais les appels aux téléphones connectés à des PBX tiers sont acheminés vers le SBC et restent donc dans le réseau d’entreprise et non dans le réseau RTC.

Pour plus d’informations sur les licences de système téléphonique, voir [Tirer le meilleur parti d’Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) et [options de plan](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) et [Microsoft licences du module complémentaire Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="supported-end-points"></a>Points de terminaison pris en charge

Vous pouvez utiliser comme point de terminaison :

- N’importe quel client Teams.

- Téléphones de zone commune. Consultez [Configurer des téléphones de zone commune pour Microsoft Teams](./set-up-common-area-phones.md). Vous n’avez pas besoin d’une licence de forfait d’appels lors de la configuration d’un téléphone de zone commune avec le routage direct.

- Skype Entreprise téléphones 3PIP. Consultez [la prise en charge des téléphones Skype Entreprise (3PIP) avec Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)

## <a name="sbc-domain-names"></a>Noms de domaine SBC

Le nom de domaine SBC doit provenir de l’un des noms inscrits dans Domaines du locataire. Vous ne pouvez pas utiliser le \*locataire .onmicrosoft.com pour le nom de domaine complet du SBC.

Le tableau suivant présente des exemples de noms DNS inscrits pour le locataire, indique si le nom peut être utilisé comme nom de domaine complet pour le SBC, ainsi que des exemples de noms de nom de domaine complet valides :

|Nom DNS|Peut être utilisé pour le nom de domaine complet SBC|Exemples de noms de domaine complet|
|:--- |:--- |:--- |
contoso.com|Oui|**Noms valides :**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Non|L’utilisation de domaines *.onmicrosoft.com n’est pas prise en charge pour les noms SBC

Supposons que vous souhaitiez utiliser un nouveau nom de domaine. Par exemple, votre locataire a contoso.com en tant que nom de domaine inscrit dans votre locataire et vous souhaitez utiliser sbc1.sip.contoso.com. Avant de pouvoir coupler un SBC avec le nom sbc1.sip.contoso.com, vous devez inscrire le nom de domaine sip.contoso.com dans Domaines dans votre locataire. Si vous essayez de coupler un SBC avec sbc1.sip.contoso.com avant d’inscrire le nom de domaine, vous obtenez l’erreur suivante : « Impossible d’utiliser le domaine « sbc1.sip.contoso.com », car il n’a pas été configuré pour ce locataire. »

Après avoir ajouté le nom de domaine, vous devez également créer un utilisateur avec upn user@sip.contoso.com et attribuer une licence Teams. Le provisionnement complet du nom de domaine peut prendre jusqu’à 24 heures après son ajout aux domaines de votre locataire, la création d’un utilisateur avec un nouveau nom et l’attribution d’une licence à l’utilisateur.

Il est possible qu’une entreprise ait plusieurs espaces d’adressage SIP dans un seul locataire. Par exemple, une entreprise peut avoir contoso.com comme espace d’adressage SIP et fabrikam.com comme deuxième espace d’adressage SIP. Certains utilisateurs ont des user@contoso.com d’adresses et d’autres ont des user@fabrikam.com d’adresses. 

Le SBC n’a besoin que d’un seul nom de domaine complet et peut traiter les utilisateurs à partir de n’importe quel espace d’adressage dans le locataire jumelé. Par exemple, un SBC portant le nom sbc1.contoso.com peut recevoir et envoyer le trafic RTC pour les utilisateurs ayant des adresses user@contoso.com et user@fabrikam.com tant que ces espaces d’adressage SIP sont inscrits dans le même locataire.  

 > [!NOTE]
 > Le nom de domaine complet SBC dans Azure Communication Services routage direct doit être différent du nom de domaine complet SBC dans le routage direct Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificat approuvé public pour le SBC

Microsoft vous recommande de demander le certificat pour le SBC en générant une demande de signature de certification (CSR). Pour obtenir des instructions spécifiques sur la génération d’un CSR pour un SBC, reportez-vous aux instructions d’interconnexion ou à la documentation fournie par vos fournisseurs SBC.

> [!NOTE]
> La plupart des autorités de certification exigent que la taille de la clé privée soit d’au moins 2 048. Gardez cela à l’esprit lors de la génération de la csr.

Le certificat doit avoir le nom de domaine complet SBC comme champ nom commun (CN) ou autre nom d’objet (SAN).

Le routage direct prend également en charge un caractère générique dans le CN et/ou le SAN, et le caractère générique doit être conforme à [la norme RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).

Par exemple, vous pouvez utiliser \*.contoso.com qui correspondrait au nom de domaine complet SBC sbc.contoso.com, mais ne correspondrait pas à sbc.test.contoso.com.

L’interface SIP de routage direct approuve uniquement les certificats signés par des autorités de certification qui font partie du programme de certificat racine approuvé Microsoft. Assurez-vous que votre certificat SBC est signé par une autorité de certification qui fait partie du programme et que l’extension Utilisation étendue de la clé (EKU) de votre certificat inclut l’authentification du serveur.
En savoir plus : [Configuration requise du programme - Microsoft programme racine approuvé](/security/trusted-root/program-requirements)
  
[Liste de certificats d’autorité de certification incluses](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Pour le routage direct dans Office 365 environnements GCCH et DoD, le certificat doit être généré par l’une des autorités de certification racine suivantes :

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> Si la prise en charge du protocole TLS mutuel (MTLS) est activée pour la connexion Teams sur le SBC, vous devez installer les certificats Baltimore CyberTrust Root et DigiCert Global Root G2 dans le magasin racine de confiance SBC du contexte TLS Teams. (Cela est dû au fait que les certificats de service Microsoft utilisent l’un de ces deux certificats racines.) Pour télécharger ces certificats racines, consultez [Office 365 Chaînes de chiffrement](/microsoft-365/compliance/encryption-office-365-certificate-chains). Pour plus d’informations, voir [Modifications des certificats TLS Office](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Signalisation SIP : noms de domaine complets

Le routage direct est proposé dans les environnements suivants :

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

En savoir plus sur [les environnements Office 365 et us Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) tels que GCC, GCC High et DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 environnements GCC

Les points de connexion pour le routage direct sont les trois noms de domaine complets suivants :

- **sip.pstnhub.microsoft.com** (nom de domaine complet global) doit d’abord être essayé. Lorsque le SBC envoie une demande de résolution de ce nom, le Microsoft serveurs Azure DNS retourne une adresse IP pointant vers le centre de données Azure principal affecté au SBC. L’affectation est basée sur les métriques de performances des centres de données et la proximité géographique du SBC. L’adresse IP retournée correspond au nom de domaine complet principal.

- **sip2.pstnhub.microsoft.com** ( nom de domaine complet secondaire) est mappé géographiquement à la deuxième région de priorité.

- **sip3.pstnhub.microsoft.com** ( nom de domaine complet tertiaire) correspond géographiquement à la troisième région prioritaire.

Il est nécessaire de placer ces trois noms de domaine complets dans l’ordre pour :

- Fournir une expérience optimale (moins chargé et le plus proche du centre de données SBC affecté en interrogeant le premier nom de domaine complet).

- Fournir un basculement lorsque la connexion d’un SBC est établie à un centre de données qui rencontre un problème temporaire. Pour plus d’informations, consultez [Mécanisme de basculement](#failover-mechanism-for-sip-signaling) ci-dessous.  

Les noms de domaine complets (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com et sip3.pstnhub.microsoft.com) seront résolus en adresses IP à partir des sous-réseaux suivants :

- 52.112.0.0/14
- 52.122.0.0/15

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

### <a name="office-gcc-dod-environment"></a>Environnement Office GCC DoD

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.dod.teams.microsoft.us** : nom de domaine complet global. Étant donné que l’environnement Office 365 DoD n’existe que dans les centres de données américains, il n’y a pas de FQDN secondaires et tertiaires.

Le nom de domaine complet sip.pstnhub.dod.teams.microsoft.us sera résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.64.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

### <a name="office-365-gcc-high-environment"></a>Office 365 environnement GCC High

Le point de connexion pour le routage direct est le nom de domaine complet suivant :

**sip.pstnhub.gov.teams.microsoft.us** : nom de domaine complet global. Comme l’environnement GCC High existe uniquement dans les centres de données américains, il n’existe pas de noms de domaine complets secondaires et tertiaires.

Le nom de domaine complet sip.pstnhub.gov.teams.microsoft.us sera résolu en adresse IP à partir du sous-réseau suivant :

- 52.127.88.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu afin d’autoriser le trafic entrant et sortant vers et depuis les adresses pour la signalisation.

## <a name="sip-signaling-ports"></a>Signalisation SIP : Ports

Vous devez utiliser les ports suivants pour les environnements Microsoft 365 ou Office 365 où le routage direct est proposé :

- Microsoft 365 ou Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Trafic|De|À|Port source|Port de destination|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Défini sur le SBC (Pour Office 365 GCC High/DoD, seul le port 5061 doit être utilisé)|
SIP/TLS|SBC|SIP Proxy|Défini sur le SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mécanisme de basculement pour la signalisation SIP

Le SBC effectue une requête DNS pour résoudre sip.pstnhub.microsoft.com. En fonction de l’emplacement SBC et des métriques de performances du centre de données, le centre de données principal est sélectionné. Si le centre de données principal rencontre un problème, le SBC essaiera la sip2.pstnhub.microsoft.com, qui se résout en deuxième centre de données attribué et, dans les rares cas où les centres de données de deux régions ne sont pas disponibles, le SBC réessaye le dernier nom de domaine complet (sip3.pstnhub.microsoft.com), qui fournit l’adresse IP du centre de données tertiaire.

Le tableau ci-dessous récapitule les relations entre les centres de données primaires, secondaires et tertiaires :

|Si le centre de données principal est|EMEA|NOAM|ASIE|
|:--- |:--- |:--- |:--- |
|Centre de données secondaire (sip2.pstnhub.microsoft.com)|NOUS|UE|NOUS|
|Centre de données tertiaire (sip3.pstnhub.microsoft.com)|ASIE|ASIE|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Trafic multimédia : plages de ports

Notez que les exigences ci-dessous s’appliquent si vous souhaitez déployer le routage direct sans contournement de média. Pour connaître les exigences de pare-feu pour la déviation du trafic multimédia, reportez-vous à [Planifier la déviation du trafic multimédia avec le routage direct](./direct-routing-plan-media-bypass.md).

Le trafic multimédia circule vers et depuis un service distinct dans le cloud Microsoft. Les plages d’adresses IP pour le trafic multimédia sont les suivantes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 environnements GCC

- 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254).
- 52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 environnement DoD

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

Le trafic multimédia circule via des composants appelés processeurs multimédias. Les processeurs multimédias sont placés dans les mêmes centres de données que les proxys SIP :

- NOAM (USA Centre Sud, deux dans les centres de données USA Ouest et USA Est)
- Europe (centres de données Royaume-Uni Sud, France Centre, Amsterdam et Dublin)
- Asie (centre de données de Singapour)
- Japon (centres de données JP Est et Ouest)
- Australie (centres de données Est et Sud-Est de l’UA)
- LATAM (Brésil Sud)

## <a name="media-traffic-codecs"></a>Trafic multimédia : Codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Étape entre SBC et le processeur multimédia cloud ou Microsoft client Teams

S’applique aux cas de contournement de média et aux cas de non-contournement.

L’interface de routage direct située entre le contrôleur de bordure de session et le processeur multimédia cloud (sans déviation du trafic multimédia) ou entre le client Teams et le SBC (si la déviation du trafic multimédia est activée) peut utiliser les codecs suivants :

- Contournement non multimédia (SBC vers processeur multimédia cloud) : SILK, G.711, G.722, G.729
- Contournement du trafic multimédia (SBC vers le client Teams) : SILK, G.711, G.722, G.729

Vous pouvez forcer l’utilisation du codec spécifique sur le contrôleur de bordure de session en excluant les codecs indésirables de l’offre.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Étape entre le client Microsoft Teams et le processeur multimédia cloud

S’applique uniquement au cas de contournement de média. Avec la déviation du trafic multimédia, le média circule directement entre le client Teams et le SBC.

Sur la jambe entre le processeur multimédia cloud et Microsoft client Teams, SILK ou G.722 est utilisé. Le choix des codecs sur cette étape est basé sur des algorithmes Microsoft, qui prennent en compte plusieurs paramètres.

  > [!NOTE]
  > Le nouveau ciblage multimédia n’est pas pris en charge. Lors d’un appel Routage direct, si le SBC envoie une nouvelle adresse IP multimédia au Routage direct Teams, bien qu’il soit négocié dans la signalisation SIP, le multimédia n’est jamais envoyé à la nouvelle adresse IP à partir du Routage direct Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Contrôleurs de bordure de session (SBC) pris en charge

Microsoft prend uniquement en charge les SBC certifiés à coupler avec le routage direct. Étant donné que Téléphonie – Grandes entreprises est essentiel pour les entreprises, Microsoft effectue des tests intensifs avec les SBC sélectionnés et collabore avec les fournisseurs SBC pour s’assurer que les deux systèmes sont compatibles.

Les appareils qui ont été validés sont répertoriés comme certifiés pour le routage direct Teams. Les appareils certifiés sont garantis pour fonctionner dans tous les scénarios.

Pour plus d’informations sur les contrôleurs SBC pris en charge, consultez [Contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>Limites de prise en charge

Microsoft ne prend en charge le système téléphonique avec routage direct que lorsqu'il est utilisé avec des périphériques certifiés. En cas de problème, vous devez d'abord contacter le support client de votre fournisseur de SBC. Si nécessaire, le fournisseur SBC transmettra le problème à Microsoft par les canaux internes. Microsoft se réserve le droit de rejeter les cas de support où un appareil non certifié est connecté au système téléphonique par le biais du Direct Routing. Si Microsoft détermine que le problème de routage direct d’un client concerne l’appareil SBC d’un fournisseur, le client devra contacter de nouveau le fournisseur SBC pour obtenir de l’aide.

## <a name="see-also"></a>Voir aussi

[Configurer le routage direct](direct-routing-configure.md)
