---
title: Planifier le routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
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
description: Découvrez comment Téléphone Microsoft routage direct du système vous permet de connecter un contrôleur de session en bordure (SBC) fourni par un client pris en charge à Téléphone Microsoft système.
ms.openlocfilehash: 546a26422ff4f907f88c3a47808ff0f9ea546d00
ms.sourcegitcommit: 5f19df90443810e027085f8b38d22218e4123a16
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59482408"
---
# <a name="plan-direct-routing"></a>Planifier le routage direct

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du routage direct, comment le planifier et comment le déployer : [routage](https://aka.ms/teams-direct-routing) direct dans Microsoft Teams

Téléphone Microsoft Le routage direct du système vous permet de connecter un contrôleur de session en bordure (SBC) pris en charge par le client à Téléphone Microsoft système.  Avec cette fonctionnalité, vous pouvez par exemple configurer une connectivité de réseau téléphonique public commuté (PSTN) sur site avec le client Microsoft Teams, comme illustré dans le diagramme suivant : 

![Diagramme montrant la configuration de la connectivité PSTN sur site.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration de la connectivité PSTN local avec Microsoft Teams client")

  > [!NOTE]
  > Skype Entreprise En ligne vous permet également de coupler un SBC fourni par un client, mais cela nécessite un déploiement Skype Entreprise Server local ou une édition spéciale de Skype Entreprise, appelée Cloud Connector, entre le SBC et Microsoft Cloud. Ce scénario est appelé voix hybride. En revanche, le routage direct permet une connexion directe entre le SBC pris en charge et Microsoft Cloud.

> [!Important]
> La version Cloud Connector prendra fin le 31 juillet 2021 en même temps que Skype Entreprise Online. Une fois que votre organisation a été Teams, découvrez comment connecter votre réseau téléphonique local à Teams’aide du [routage direct.](direct-routing-landing-page.md) 

Avec le routage direct, vous pouvez connecter votre SBC à pratiquement n’importe quelle ligne téléphonique ou connexion entre elles avec un équipement PSTN tiers. Le routage direct vous permet d': 

- Utilisez pratiquement n’importe quelle ligne PSTN avec Téléphone Microsoft System. 
- Configurez l’interopérabilité entre les équipements téléphoniques du client, tels qu’un échange de branches privée (PBX) tiers, des appareils analogiques et Téléphone Microsoft système.

Microsoft propose également des solutions vocales complètes dans le cloud, telles que les forfaits d’appels. Toutefois, une solution vocale hybride peut être idéale pour votre organisation si : 

- Le forfait d’appels Microsoft n’est pas disponible dans votre pays/région. 
- Votre organisation requiert une connexion à des appareils analogiques tiers, des centres d’appels, etc. 
- Votre organisation a un contrat existant avec un opérateur PSTN.

Le routage direct prend également en charge les utilisateurs qui ont la licence supplémentaire pour l’offre d’appels Microsoft. Pour plus d’informations, [voir Système téléphonique et forfaits d’appels.](calling-plan-landing-page.md) 

Avec le routage direct, lorsque les utilisateurs participent à une conférence organisée, le numéro de connexion est fourni par le service d’audioconférence Microsoft, qui requiert une licence appropriée.  Lors de l’appel sortant, le service d’audioconférence Microsoft place l’appel à l’aide des fonctionnalités d’appel en ligne, qui nécessitent une licence appropriée. (Remarque : si un utilisateur n’a pas de licence d’audioconférence Microsoft, l’appel est routant directement.) Pour plus d’informations, [voir Réunions en ligne avec Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
La planification de votre déploiement du routage direct est essentielle pour une implémentation réussie. Cet article décrit les exigences en matière d’infrastructure et de gestion des licences et fournit des informations sur la connectivité SBC : 

- [Conditions requises pour l'infrastructure](#infrastructure-requirements)
- [Licences et autres conditions requises](#licensing-and-other-requirements)
- [Noms de domaine SBC](#sbc-domain-names)
- [Certificat approuvé public pour le SBC](#public-trusted-certificate-for-the-sbc)
- [Signalisation SIP : FQDN](#sip-signaling-fqdns)
- [Signalisation SIP : ports](#sip-signaling-ports)
- [Trafic de médias : plages de ports](#media-traffic-port-ranges)
- [Contrôleurs de bordure de session pris en charge](#supported-session-border-controllers-sbcs)

Pour plus d’informations sur la configuration du routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Conditions d’infrastructure requises
Les exigences d’infrastructure pour les SBCS, domaines et autres exigences de connectivité réseau pris en charge pour déployer le routage direct sont répertoriées dans le tableau suivant :  

|Conditions requises pour l’infrastructure|Vous avez besoin des|
|:--- |:--- |
|Contrôleur de bordure de session (SBC)|SBC pris en charge. Pour plus d’informations, voir [SBCS pris en charge.](#supported-session-border-controllers-sbcs)|
|Ligne téléphonique connectée au SBC|Une ou plusieurs ligne téléphoniques connectées au SBC. À l’une des extrémités, le SBC se connecte au Téléphone Microsoft via un routage direct. Le SBC peut également se connecter à des entités téléphoniques tierces, telles que PBX, des cartes téléphoniques analogiques, etc. Les options de connectivité PSTN connectées au SBC fonctionnent. (Pour la configuration des ligne PSTN vers le SBC, veuillez vous reporter aux fournisseurs SBC ou aux fournisseurs de ligne.)|
|Microsoft 365 ou Office 365 organisation|Organisation Microsoft 365 ou Office 365 que vous utilisez pour la maison de vos utilisateurs Microsoft Teams, la configuration et la connexion au SBC.|
|Bureau d’enregistrement d’utilisateurs|L’utilisateur doit être homed in Microsoft 365 ou Office 365.<br/>Si votre entreprise dispose d’un environnement Skype Entreprise ou Lync local avec une connectivité hybride à Microsoft 365 ou Office 365, vous ne pouvez pas activer la voix dans Teams pour un utilisateur domicile sur site.<br/><br/>Pour vérifier le bureau d’enregistrement d’un utilisateur, utilisez l’Skype Entreprise cmdlet PowerShell online suivante :<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>La sortie de l’cmdlet doit afficher :<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domaines|Un ou plusieurs domaines ont été ajoutés à Microsoft 365 ou Office 365 organisation.<br/><br/>Notez que vous ne pouvez pas utiliser le domaine .onmicrosoft.com par défaut créé automatiquement \* pour votre client.<br/><br/>Pour afficher les domaines, vous pouvez utiliser l’Skype Entreprise cmdlet PowerShell online suivante :<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Pour plus d’informations sur les domaines et Microsoft 365 ou Office 365 d’organisation, voir [FAQ sur les domaines.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Adresse IP publique pour le SBC|Adresse IP publique qui peut être utilisée pour se connecter au SBC. En fonction du type de SBC, le SBC peut utiliser une nat.|
|Nom de domaine complet (FQDN) pour le champ SBC|Un nom de domaine (FQDN) pour le SBC, dans lequel la partie domaine du nom de domaine (FQDN) est l’un des domaines enregistrés dans votre organisation Microsoft 365 ou Office 365 domaine. Pour plus d’informations, voir [les noms de domaine SBC.](#sbc-domain-names)|
|Entrée DNS publique pour le SBC |Entrée DNS publique m mappage du FQDN SBC à l’adresse IP publique. |
|Certificat approuvé public pour le SBC |Certificat pour le SBC à utiliser pour toutes les communications avec le routage direct. Pour plus d’informations, [voir Certificat de confiance public pour le SBC.](#public-trusted-certificate-for-the-sbc)|
|Points de connexion pour le routage direct |Les points de connexion pour le routage direct sont les trois FQDN suivants :<br/><br/>`sip.pstnhub.microsoft.com` – Votre FQDN global doit d’abord être essayé.<br/>`sip2.pstnhub.microsoft.com` – Un FQDN secondaire maie géographiquement la région de la deuxième priorité.<br/>`sip3.pstnhub.microsoft.com` – Le FQDN se produit géographiquement pour la troisième région prioritaire.<br/><br/>Pour plus d’informations sur la configuration requise, [voir Signalisation SIP : FQDNs.](#sip-signaling-fqdns)|
|Adresses IP et ports du pare-feu pour le routage direct |Le SBC communique aux services suivants dans le cloud :<br/><br/>Proxy SIP, qui gère le signalisation<br/>Processeur multimédia, qui gère le média, sauf lorsque la dérivation média est en cours<br/><br/>Ces deux services ont des adresses IP distinctes dans Microsoft Cloud, comme décrit plus loin dans ce document.<br/><br/>Pour plus d’informations, voir [la section Microsoft Teams des](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) URL et des [plages d’adresses IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|Profil de transport multimédia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Adresses IP du pare-feu et ports pour Microsoft Teams multimédia |Pour plus d’informations, [voir URL et plages d’adresses IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licences et autres conditions requises 

Les utilisateurs d’un routage direct doivent avoir les licences suivantes Microsoft 365 ou Office 365 : 

- Téléphone Microsoft Système. 
- Microsoft Teams + Skype Entreprise Plan 2, s’il est inclus dans les licences.
- Audioconférence Microsoft (lisez les notes et le paragraphe ci-dessous pour obtenir des exemples spécifiques de moment où la licence est requise).

> [!NOTE]
> Skype Entreprise Le plan ne doit pas être supprimé des contrats de licence inclus dans ce dernier. 
> 
> [!IMPORTANT]
> Cloud de la communauté du secteur public Les utilisateurs des services Haute et DoD doivent désactiver les licences d’audioconférence incluses dans G5 et attendre d’activer l’audioconférence jusqu’à ce que le routage direct soit entièrement configuré. Avant d’activer les licences d’audioconférence, les utilisateurs doivent avoir configuré des numéros de téléphone d’accès et un pavé de numérotation pour travailler. Pour [plus d’informations,](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) consultez audioconférence avec routage direct Cloud de la communauté du secteur public Haute et DoD.


> [!IMPORTANT]
>  Si vous voulez ajouter des participants externes à des réunions programmées, soit en les composant un numéro d’appel sortant, soit en fournissant le numéro d’accès, la licence d’audioconférence est requise.
> Pour Cloud de la communauté du secteur public haute et doD, n’affectez pas de licence d’audioconférence aux utilisateurs de G5.  Pour les utilisateurs de G3, n’affectez pas de licence d’audioconférence tant que le routage direct n’est pas entièrement configuré et que l’utilisateur dispose d’un pavé de numérotation opérationnel.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalade d’appel ad hoc et licence d’audioconférence

Un Teams utilisateur peut démarrer une Teams un appel RSTN ou Teams un appel Teams et y ajouter un participant PSTN. Ce scénario s’appelle une conférence ad hoc. Le chemin d’accès à l’appel varie selon que l’utilisateur qui l’appelle a reçu ou non une licence d’audioconférence Microsoft :

- Si une Teams Microsoft Audioconférence est affectée à l’utilisateur qui fait l’escalade de l’appel, l’escalade se produit via le service d’audioconférence Microsoft. Le participant PSTN distant invité à l’appel existant reçoit une notification concernant l’appel entrant et voit le numéro du pont Microsoft attribué à l’utilisateur du Teams qui a initié l’escalade.
- Si la licence de Teams de conférence AudioConférence Microsoft ne lui est pas attribuée, l’escalade se produit à l’aide d’un contrôleur de session en bordure connecté à l’interface de routage direct. Le participant PSTN distant qui est invité à l’appel reçoit une notification concernant l’appel entrant et voit le numéro de l’utilisateur Teams à l’origine de l’escalade. La stratégie de routage de l’utilisateur définit l’escalade spécifique utilisée. 


De plus, vous devez vous assurer que les choses suivantes sont les suivantes :
 
- CsOnlineVoiceRoutingPolicy est affecté à l’utilisateur. 
- Autoriser les appels privés est activé au niveau du client pour les Microsoft Teams. 

Le routage direct prend également en charge les utilisateurs titulaires d’une licence microsoft Calling Plan. Téléphone Microsoft Le système avec le plan d’appels peut router certains appels à l’aide de l’interface de routage direct. Toutefois, les numéros de téléphone des utilisateurs doivent être acquis en ligne ou portés à Microsoft.  

L’utilisation d’un plan d’appel et d’une connectivité de routage direct pour le même utilisateur est facultative, mais peut s’avérer utile (par exemple, lorsque l’utilisateur est affecté à un plan d’appels Microsoft mais souhaite router certains appels à l’aide du SBC). L’un des scénarios les plus courants est l’appel à des PBX tiers.  Avec les SYSTÈMES PBX tiers, tous les appels, à l’exception des appels vers les téléphones connectés à ces PBX, sont acheminés à l’aide d’un plan d’appel Microsoft, mais les appels vers les téléphones connectés à des PBX tiers sont acheminés vers le SBC et restent donc au sein du réseau d’entreprise et non du réseau PSTN. 

Pour plus d’informations sur [](https://products.office.com/compare-all-microsoft-office-products?tab=2) Système téléphonique licences de gestion de licences, voir Les options d’Office [et de Plan.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Pour plus d’informations sur Système téléphonique licences de module complémentaire, voir [Microsoft Teams de module complémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>Points de fin pris en charge 

Vous pouvez utiliser comme point de fin :

- N’importe Teams client. 
- Téléphones en zone commune. Consultez [Configurer la licence zone Téléphone commun pour Microsoft Teams.](./set-up-common-area-phones.md) Notez qu’il n’est pas nécessaire d’avoir une licence Plan d’appels lors de la configuration d’une zone Téléphone avec un routage direct.
- Skype Entreprise téléphones 3PIP. Consulter [Skype Entreprise prise en charge des téléphones 3PIP avec Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Noms de domaine SBC

Le nom de domaine SBC doit avoir été enregistré dans les domaines du client. Vous ne pouvez pas utiliser le client .onmicrosoft.com pour le nom de nom de domaine complet \* du SBC.

Le tableau suivant présente des exemples de noms DNS inscrits pour le client, indique si le nom peut être utilisé en tant que nom de domaine complet pour la carte de noms de domaine complet (SBC), ainsi que des exemples de noms de domaine complets valides :

|Nom DNS|Peut être utilisé pour le FQDN SBC|Exemples de noms de domaine domaine (FQDN)|
|:--- |:--- |:--- |
contoso.com|Oui|**Noms valides :**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|Non|L’utilisation de domaines *.onmicrosoft.com n’est pas prise en charge pour les noms SBC

Supposons que vous vouliez utiliser un nouveau nom de domaine. Par exemple, votre client a contoso.com nom de domaine enregistré dans votre client et vous souhaitez utiliser sbc1.sip.contoso.com. Avant de pouvoir coupler un SBC avec le sbc1.sip.contoso.com nom, vous devez inscrire le nom de domaine sip.contoso.com domaines dans votre client. Si vous tentez de coupler un SBC avec sbc1.sip.contoso.com avant d’enregistrer le nom de domaine, le message d’erreur suivant s’agit : « Impossible d’utiliser le domaine « sbc1.sip.contoso.com » car il n’a pas été configuré pour ce client. »
Après avoir ajouté le nom de domaine, vous devez également créer un utilisateur avec un nom d’utilisateur user@sip.contoso.com et affecter une Teams utilisateur. Une fois le nom de domaine ajouté aux domaines de votre client, un utilisateur avec un nouveau nom est créé et une licence peut prendre jusqu’à 24 heures. 

Il est possible qu’une entreprise puisse avoir plusieurs espaces d’adresse SIP dans un client. Par exemple, une entreprise peut avoir un espace contoso.com d’adresse SIP et fabrikam.com espace d’adresse SIP comme deuxième espace. Certains utilisateurs ont des adresses user@contoso.com et d’autres ont des adresses user@fabrikam.com. 

Le SBC n’a besoin que d’un seul FQDN et peut servicer les utilisateurs à partir de n’importe quel espace d’adresse dans le client couplé. Par exemple, un code SBC avec le nom sbc1.contoso.com peut recevoir et envoyer le trafic PSTN aux utilisateurs dont les adresses user@contoso.com et user@fabrikam.com sont enregistrées dans le même client.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificat approuvé public pour le SBC

Microsoft vous recommande de demander le certificat pour le SBC en générant une demande de signature de certification. Pour obtenir des instructions spécifiques sur la génération d’une qualité de service (CSR) pour un SBC, reportez-vous aux instructions ou à la documentation d’interconnexion fournies par vos fournisseurs SBC. 

  > [!NOTE]
  > La plupart des autorités de certification nécessitent que la taille de clé privée soit au moins 2 048. Gardez ceci à l’esprit lors de la génération de la CSR.

Le nom de domaine complet (FQDN) du certificat doit être le nom commun (CN) ou le champ SAN (Subject Alternative Name). Le certificat doit être émis directement auprès d’une autorité de certification et non d’un fournisseur intermédiaire.

Par contre, le routage direct prend en charge un caractère générique dans cn et/ou SAN, et ce caractère générique doit être conforme au [protocole RFC HTTP sur TLS standard.](https://tools.ietf.org/html/rfc2818#section-3.1) Par exemple, il serait d’utiliser un contoso.com qui correspondrait à la sbc.contoso.com de votre FQDN SBC, mais pas à \* la sbc.test.contoso.com.

Le certificat doit être généré par l’une des autorités de certification racine suivantes :

- Trust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Buypass
- Cybertrust
- Class 3 Public Primary Certification Authority
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Confiez
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Racine mobile Enterprise Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- CiteVadis
- USERTrust RSA Certification Authority
- Hong root CA 1,2,3
- Sectigo Root CA

Pour un routage direct dans Office 365 GCCH et DoD, le certificat doit être généré par l’une des autorités de certification racine suivantes :
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Si la prise en charge mutual TLS (MTLS) est activée pour la connexion Teams sur le SBC, vous devez installer le certificat racine CyberTrust de Baltimore dans le magasin racine approuvé SBC du contexte TLS Teams. (En raison du fait que les certificats de service Microsoft utilisent le certificat racine de Baltimore.) Pour télécharger le certificat racine de Baltimore, voir Office 365 [chaînes de chiffrement.](/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft travaille sur l’ajout d’autres autorités de certification en fonction des demandes des clients. 

## <a name="sip-signaling-fqdns"></a>Signalisation SIP : FQDN 

Le routage direct est proposé dans les environnements suivants :
- Microsoft 365 ou Office 365
- Office 365 Cloud de la communauté du secteur public
- Office 365 Cloud de la communauté du secteur public Haute
- Office 365 DoD

En savoir plus sur [les environnements Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) administration publique aux États-Unis, tels Cloud de la communauté du secteur public, Cloud de la communauté du secteur public Élevé et DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail

Les points de connexion pour le routage direct sont les trois FQDN suivants :

- **sip.pstnhub.microsoft.com** , vous devez d’abord essayer le FQDN global. Lorsque le SBC envoie une demande de résolution de ce nom, les serveurs DNS Microsoft Azure renvoient une adresse IP pointant vers le centre de données Azure principal affecté au SBC. L’affectation est basée sur les mesures de performance des centres de données et la proximité géographique par rapport au SBC. L’adresse IP renvoyée correspond au FQDN principal.
- **sip2.pstnhub.microsoft.com** (FQDN secondaire) géographiquement à la région de deuxième priorité.
- **sip3.pstnhub.microsoft.com** – FQDN de l’situation géographique de la troisième région.

En plaçant ces trois FQDN dans l’ordre, vous devait :

- Offrez une expérience optimale (moins chargé et le plus proche du centre de données SBC attribué en interrogeant le premier FQDN).
- Offrez unover lorsque la connexion à partir d’un SBC est établie vers un centre de données qui rencontre un problème temporaire. Pour plus d’informations, [voir le mécanisme deover ci-dessous.](#failover-mechanism-for-sip-signaling)  

Les noms de accès (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com et sip3.pstnhub.microsoft.com) sont résolus pour les adresses IP des sous-réseaux suivants :

- 52.112.0.0/14
- 52.120.0.0/14

Vous devez ouvrir des ports pour toutes ces plages d’adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.  Si votre pare-feu prend en charge les noms DNS, le sip-all.pstnhub.microsoft.com **de** noms de domaine (FQDN) est résolu pour tous ces sous-réseaux IP. 

### <a name="office-gcc-dod-environment"></a>Office Cloud de la communauté du secteur public Environnement DoD

Le point de connexion pour le routage direct est le FQDN suivant :

**sip.pstnhub.dod.teams.microsoft.us** – FQDN global. Étant donné que l’Office 365 DoD existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.

Le sip.pstnhub.dod.teams.microsoft.us de sip.pstnhub.dod.teams.microsoft.us de votre FQDN sera résolu en une adresse IP provenant du sous-réseau suivant :

- 52.127.64.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation.

### <a name="office-365-gcc-high-environment"></a>Office 365 Cloud de la communauté du secteur public environnement élevé

Le point de connexion pour le routage direct est le FQDN suivant :

**sip.pstnhub.gov.teams.microsoft.us** – FQDN global. Étant donné que l Cloud de la communauté du secteur public de haute ligne existe uniquement dans les centres de données américains, il n’existe aucun nom de fQDN secondaire et secondaire.

Le problème de sip.pstnhub.gov.teams.microsoft.us de sip.pstnhub.gov.teams.microsoft.us sera résolu en tant qu’adresse IP provenant du sous-réseau suivant :

- 52.127.88.0/21

Vous devez ouvrir des ports pour toutes ces adresses IP dans votre pare-feu pour autoriser le trafic entrant et sortant à se rendre ou à partir des adresses pour le trafic de signalisation. Si votre pare-feu prend en charge les noms DNS, le nom de domaine sip-all.pstnhub.gov.teams.microsoft.us **est** résolu pour toutes ces adresses IP. Ce nom de FQDN peut également être utilisé en tant que nom de fédéré pour la classification d’appel entrant.

## <a name="sip-signaling-ports"></a>Signalisation SIP : ports

Vous devez utiliser les ports suivants pour les environnements Microsoft 365 ou Office 365 où le routage direct est proposé :
- Microsoft 365 ou Office 365
- Office 365 Cloud de la communauté du secteur public
- Office 365 Cloud de la communauté du secteur public Haute
- Office 365 DoD

|Trafic|De|À|Port source|Port de destination|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Défini sur le SBC (pour Office 365 Cloud de la communauté du secteur public le port High/DoD uniquement 5061 doit être utilisé)|
SIP/TLS|SBC|SIP Proxy|Défini sur le SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mécanisme deover pour le signalisation SIP

Le SBC effectue une requête DNS pour résoudre des sip.pstnhub.microsoft.com. En fonction de l’emplacement SBC et des mesures de performances du centre de données, le centre de données principal est sélectionné. Si le centre de données principal est affecté, SBC tente d’essayer le sip2.pstnhub.microsoft.com qui résout le deuxième centre de données affecté et, dans le rare cas où des centres de données de deux régions ne sont pas disponibles, le SBC retentre le dernier sip3.pstnhub.microsoft.com de référence (FQDN), qui fournit l’adresse IP du centre de données indécable.

Le tableau ci-dessous résume les relations entre les centres de données principal, secondaire et secondaire :

|Si le centre de données principal est|EMEA|NOAM|ASIE|
|:--- |:--- |:--- |:--- |
|Centre de données secondaire (sip2.pstnhub.microsoft.com)|États-Unis|UE|États-Unis|
|Centre de données inexerateur (sip3.pstnhub.microsoft.com)|ASIE|ASIE|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Trafic de médias : plages de ports
Notez que les conditions suivantes s’appliquent si vous voulez déployer un routage direct sans contournement média. Pour plus d’informations sur les exigences de pare-feu pour la dérivation média, voir Planifier la [dérivation média avec le routage direct.](./direct-routing-plan-media-bypass.md)



Le trafic de médias circule vers et depuis un service distinct dans Microsoft Cloud. Les plages d’adresses IP pour le trafic de médias sont les suivantes :

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 et Office 365 Cloud de la communauté du secteur public de travail

- 52.112.0.0/14 (adresses IP de 52.112.0.1 à 52.115.255.254).
- 52.120.0.0/14 (adresses IP de 52.120.0.1 à 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 Environnement DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 Cloud de la communauté du secteur public environnement élevé

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Plage de ports (applicable à tous les environnements)
La plage de ports des processeurs multimédias est indiquée dans le tableau suivant : 

|Trafic|De|À|Port source|Port de destination|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processeur multimédia|SBC|3478-3481 et 49152 – 53247|Défini sur le SBC|
|UDP/SRTP|SBC|Processeur multimédia|Défini sur le SBC|3478-3481 et 49152 – 53247|

  > [!NOTE]
  > Microsoft recommande au moins deux ports par appel simultané sur le SBC.


## <a name="media-traffic-media-processors-geography"></a>Trafic de médias : géographie des processeurs multimédias

Le trafic de médias est flux via des composants appelés processeurs multimédias. Les processeurs multimédias sont placés dans les mêmes centres de données que les serveurs SIP. De plus, d’autres processeurs multimédias sont à même d’optimiser le flux de médias. Par exemple, nous n’avons pas de composant proxy SIP actuellement en Australie (flux SIP via Singapour ou Hong Kong), mais le processeur de médias est en Australie. Le besoin pour les processeurs multimédias en local est dicté par la latence que nous avons expérience en envoyant le trafic à longue distance, par exemple de l’Australie à Singapour ou à Hong Kong. Bien que la latence dans l’exemple du trafic qui s’écoule de l’Australie vers Hong Kong ou Singapour soit acceptable, il n’est pas acceptable de préserver la bonne qualité des appels pour le trafic SIP, mais pas pour le trafic de médias en temps réel.

Emplacement des processeurs multimédias :

Emplacements où les composants proxy et processeur multimédia SIP sont déployés :
- États-Unis (deux dans les centres de données Ouest et Est des États-Unis)
- Centres de données d’Europe (Amsterdam et Dublin)
- Asie (centre de données de Singapour)
- Japon (centres de données JP East et West)
- Australie (centre de données Australie de l’Est et du Sud-est)

## <a name="media-traffic-codecs"></a>Trafic de médias : codecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Étape entre SBC et cloud Media Processor ou Microsoft Teams client.
S’applique aussi bien aux cas de dérivation média qu’aux autres.

L’interface de routage direct sur la partie entre le contrôleur de bordure de session et le processeur multimédia cloud (sans dérivation média) ou entre le client Teams et le SBC (si la dérivation média est activée) peut utiliser les codecs suivants :

- Contournement non multimédia (SBC à Processeur de média cloud) : SILK, G.711, G.722, G.729
- Contournement multimédia (SBC Teams client) : SILK, G.711, G.722, G.729

Vous pouvez forcer l’utilisation du codec spécifique sur le contrôleur de session en excluant les codecs indésirables de l’offre.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Étape entre Microsoft Teams client et processeur de média cloud
S’applique uniquement aux cas de dérivation non multimédia. Avec la dérivation média, les médias circulent directement entre le client Teams et le SBC.

Dans la partie entre le processeur multimédia cloud et Microsoft Teams client SILK ou G.722 est utilisé. Le choix du codec de cette partie est basé sur les algorithmes Microsoft, qui prennent en considération plusieurs paramètres. 


## <a name="supported-session-border-controllers-sbcs"></a>Contrôleurs de bordure de session pris en charge

Microsoft prend uniquement en charge les SBCs certifiés à associer au routage direct. Étant Voix Entreprise essentiel pour les entreprises, Microsoft exécute des tests intensives avec les pc SBC sélectionnés et collabore avec les fournisseurs SBC pour s’assurer que les deux systèmes sont compatibles. 

Les périphériques validés sont répertoriés comme certifiés Teams routage direct. Le travail des périphériques certifiés est garanti dans tous les scénarios. 

Pour plus d’informations sur les SBCs pris en charge, voir Liste des contrôleurs de session [certifiés pour le routage direct.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Voir aussi

[Configurer le routage direct](direct-routing-configure.md)
