---
title: Décisions de routage Direct téléphone système service - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 07/09/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: En savoir plus sur le routage Direct, licences, et les décisions qui doivent être effectuées.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d79b6e0423ddb94b29a9d82ea1e6d6d1f173cf3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374441"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de mon service

Pour planifier l’implémentation technique de téléphone système routage Direct (« routage Direct »), vous devez apporter une série de décisions de service à l’avance pour mieux préparer votre organisation pour implémenter une solution qui répond aux besoins de l’entreprise que vous avez définie.

## <a name="calling-in-teams"></a>Appel dans Teams

Avec Microsoft Teams, vos utilisateurs peuvent passer et recevoir des appels vers ou depuis le réseau téléphonique commuté (RTC). Vos utilisateurs peuvent utiliser leurs propres numéros de téléphone dédié pour l’émission et réception d’appels nationales et internationales (y compris la messagerie vocale) à partir de l’application cliente équipes.

## <a name="direct-routing"></a>Routage direct

Pour les utilisateurs équipes pouvoir émettre et recevoir des appels RTC, ils doivent être activés pour le système téléphonique, une fonctionnalité d’Office 365.

Pour activer la connectivité au réseau RTC, vous pouvez utiliser le routage Direct à donner aux personnes de votre organisation la possibilité d’émettre et recevoir des appels téléphoniques à l’extérieur de l’organisation via le réseau RTC.

Avec le routage Direct, connectivité PSTN est facilitée par un fournisseur tiers, ce qui vous permet de continuer à utiliser vos jonctions PSTN existantes fournies par votre fournisseur de services PSTN. Ainsi, pour le déploiement dans les pays où système téléphonique avec l’appel Plans (« appel Plans ») ne sont pas disponibles ou dans les déploiements où un contrat de fournisseur de service RTC doit être conservée ou l’interopérabilité avec certains systèmes locaux Obligatoire.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilité de routage Direct

Routage direct est disponible dans les pays où Office 365 est disponible. Pour obtenir la liste de ces pays, voir [disponibilité internationale](https://products.office.com/business/international-availability) .

Après avoir confirmé que votre organisation peut obtenir la fonctionnalité système téléphonique, compiler la liste des emplacements de l’utilisateur ou de bureaux où vous allez implémenter système téléphonique, en fonction de la liste des pays et régions disponibles. Identifier les utilisateurs auxquels vous souhaitez activer le routage Direct ou Plans de l’appel pour chaque emplacement que vous avez également.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Identifiez les emplacements de l’utilisateur et les bureaux dans lequel vous allez implémenter système téléphonique.<li>Identifier les utilisateurs qui vous souhaitez activer le routage Direct ou Plans de l’appel pour chaque emplacement que vous avez.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements de l’utilisateur ou les bureaux à activer pour le système téléphonique.<li>La liste des utilisateurs que vous souhaitez activer le routage Direct ou Plans de l’appel pour chaque emplacement que vous avez de documents</ul>|

> [!TIP]
> Voici un exemple d’une liste d’activation site routage Direct.
> 
> | **Bureau**                     | **Emplacement**   | **Service de système téléphonique** |
> |--------------------------------|----------------|--------------------------|
> | 1 Eppîng Road                | Australie      | Service PSTN hérité |
> | 100 Cyberport Road             | Hong Kong R.A.S.  | Routage d’un système téléphonique Direct |
> | 1 Marina Boulevard           | Singapour      | Routage d’un système téléphonique Direct |
> | 32 London Bridge Street        | Royaume-Uni | Système téléphonique avec forfaits d’appels |
> | 39 quai du Président Roosevelt | France         | Système téléphonique avec forfaits d’appels |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Système téléphonique, chaque utilisateur dans votre organisation doit disposer un unique vers l’intérieur direct composer le numéro de téléphone (DID)). Avec le routage Direct, les numéros de téléphone et les services d’urgence fournis par votre fournisseur de services PSTN.

> [!NOTE]
> Avec le routage Direct, vos utilisateurs peuvent continuer à l’aide de leurs propres numéros de téléphone, fourni par le fournisseur de services PSTN.
> 
> [!TIP]
> Vous pouvez utiliser le modèle suivant pour documenter les détails de numéros de téléphone.
> 
> |Utilisateur |Numéro de téléphone |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |Louis Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Messagerie vocale

Messagerie vocale de système téléphonique, grâce aux services de messagerie vocale Azure, prend en charge les dépôts de messagerie vocale pour les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers.

La messagerie vocale du système téléphonique inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Besoins de votre entreprise peuvent nécessiter que vous désactivez la transcription de la messagerie vocale pour des utilisateurs spécifiques ou tout le monde dans toute l’organisation. Si votre organisation a décidé de conserver la transcription de la messagerie vocale activée, vous devez également prendre en compte si le masquage de la messagerie vocale transcription gratuites doit être activée. Pour plus d’informations, voir [définition des stratégies de messagerie vocale dans votre organisation](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) .

Pour plus d’informations sur la messagerie vocale dans une implémentation du système téléphonique, voir [configurer le système téléphonique de la messagerie vocale](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si vous devez activer la messagerie vocale système téléphonique dans votre implémentation de routage Direct.<li>Décider si vous activer ou désactiver la transcription de la messagerie vocale et masquage de gratuites transcription de la messagerie vocale dans toute l’organisation ou des utilisateurs spécifiques.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, les points de décision pour prendre en charge le système téléphonique de la messagerie vocale du document.<li>Si vous devez activer ou désactiver la messagerie vocale, la transcription de la messagerie vocale et masquage de gratuites transcription de la messagerie vocale uniquement pour des utilisateurs spécifiques, cette liste d’utilisateurs du document.</ul>|

> [!TIP]
> Téléphone les détails du système de la messagerie vocale pour l’implémentation des Plans de l’appel peuvent être documentés comme dans le tableau suivant.
> 
> | **Utilisateur**         | **Boîte aux lettres Exchange** | **Activer la messagerie vocale ?** | **Transcription de la messagerie vocale** | **Masquage de la messagerie vocale transcription gratuites** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | En ligne               | Oui                   | Activé                     | Activé                                       |
> | Lidia Holloway   | En ligne               | Oui                   | Activé                     | Désactivé                                      |
> | Louis Lahr       | Local          | Oui                   | Activé                     | Activé                                       |
> | Marcel Beauchamp | Local          | Oui                   | Désactivé                    | N/D                                           |
> | Rachelle Cormier | En ligne               | Oui                   | Désactivé                    | N/D                                           |
> | Isabell Potvin   | Local          | Oui                   | Désactivé                    | N/D                                           |
> 
> [!NOTE]
> Pour utiliser la messagerie vocale et les équipes, vos utilisateurs doivent disposer de boîtes aux lettres Exchange. Pour plus d’informations, voir [comment Exchange et les équipes Microsoft interagir](https://docs.microsoft.com/microsoftteams/exchange-teams-interact) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Gestion des licences pour le routage Direct

Si votre organisation envisage d’utiliser le routage Direct, vous devez obtenir les licences requises. Les utilisateurs de routage Direct doivent disposer les licences suivantes affectés dans Office 365 :



-   Système téléphonique de Microsoft

-   Microsoft Teams

-   Audioconférence

Licence de conférence audio est obligatoire pour ajouter des participants externes aux réunions planifiées, par un appel sortant leur ou en fournissant le numéro d’accès. Lorsqu’un participant externe est composé à, le service de conférence Audio passe l’appel à l’aide des fonctionnalités d’appel en ligne. Licence de conférence audio est facultative et requis uniquement pour les utilisateurs qui seront à organiser des équipes de conférences qui incluent l’audioconférence.


> [!NOTE]
> Pour fournir des numéros de téléphone de pont de conférence gratuit et pour prendre en charge la conférence rendez-vous aux numéros de téléphone international, vous devez configurer [Les crédits de Communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) pour votre organisation.

Conférence audio et système téléphonique peuvent être une licence séparée en tant que services de module complémentaire pour les clients disposant d’Office 365 E3 ou des plans d’abonnement E1 ; ils sont déjà inclus dans le cadre de la planification d’abonnement Office 365 E5.

> [!TIP]
> Vous pouvez également utiliser le routage Direct pour les utilisateurs activés pour l’appel des Plans lors du routage de leurs appels au PBX tiers. Pour plus d’informations, voir [Gestion des licences et les autres exigences de routage Direct](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne possède pas la licence de système téléphonique nécessaire, décidez si vous permet d’acquérir la licence du système téléphonique par le renforcement de vos abonnements Office 365 existants ou à acquérir le service complémentaire système téléphonique.<li>Décider si vous devez Communications générique pour l’implémentation de routage Direct.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les groupes de division, département, office ou utilisateur que vous allez attribuer une licence de système téléphonique du document.<li>En cas d’audioconférence avec numéros de téléphone gratuits dans la portée, les groupes division, département, office ou utilisateur, vous devez ensuite activer Communications crédits du document.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Considérations relatives à Office 365

Tout utilisateur qui sera activé pour le routage Direct doit être hébergé dans Office 365. Pour les déploiements hybrides avec Skype local de Business Server ou Lync Server, vous devez déplacer des utilisateurs vers Skype pour Business Online avant de les configurer pour utiliser le routage directe avec les équipes.

Tous les utilisateurs qui se trouvent dans l’étendue des implémentations de routage Direct doivent être activés pour les équipes.

Votre client Office 365 doit être activé avec un ou plusieurs domaines, car la valeur par défaut \*. onmicrosoft.com domaine ne peut pas être utilisé avec le routage Direct. Pour plus d’informations sur les domaines et les clients Office 365, voir [Le Forum aux questions sur les domaines](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si les utilisateurs doivent être migrées vers Skype pour Business Online prendre en charge le routage Direct.<li>Identifier les utilisateurs qui doivent être activés pour les équipes.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>La liste des utilisateurs qui doivent atteindre Skype pour Business Online et être activé pour les équipes de documents.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Considérations relatives à la SBC

Vous devez utiliser des contrôleurs de frontière de session certifié et pris en charge (SBC) qui doivent être associés au service de routage Direct afin de fournir une connectivité PSTN pour vos utilisateurs. Pour une liste de SBC certifié, voir [Contrôleurs de frontière de Session pris en charge](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs).

Selon votre environnement, le nombre d’emplacements et exigences de routage voix, vous devrez déployer plusieurs SBCs pour prendre en charge votre base d’utilisateurs.

### <a name="sbc-domain-names"></a>Noms de domaine SBC

Chaque SBC établir une association avec le routage Direct doit avoir un nom DNS unique. Les noms DNS SBC doivent être d’un des noms de domaines enregistrés dans le client Office 365. Si plusieurs noms de domaine a été assigné à votre client, vous pouvez utiliser ces noms de domaine lors de la planification pour les noms DNS des votre SBCs.

> [!IMPORTANT]
> L’utilisation de *. onmicrosoft.com pour le nom DNS SBC n’est pas autorisée.

### <a name="certificates"></a>Certificats

Chaque SBC déployé avec le routage Direct nécessite un certificat obtenu auprès d’une liste d’autorités de certification prises en charge. Le certificat doit inclure le nom DNS SBC dans l’objet, autre nom du sujet ou les champs nom commun.

> [!NOTE]
> L’utilisation des certificats avec caractères génériques avec SBC est également pris en charge.

Pour plus d’informations et une liste d’autorités de certification prises en charge, consultez la rubrique [Public certificat approuvé pour le contrôleur SBC](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Ports et adresses IP SBC

Chaque SBC doit être configuré à l’aide d’une adresse IP publique accessible à partir des centres de données Office 365. Vous pouvez également configurer la traduction d’adresses réseau (NAT) pour publier votre SBCs vers les centres de données Office 365.

SBC requièrent une connectivité bidirectionnelle pour communiquer avec les services en nuage pour la signalisation et des médias. Signalisation est gérée par le composant nommé *Proxy SIP*et le média est géré par les *Processeurs multimédia*.

Vous devez définir des numéros de port spécifiques sur chaque SBC pour la signalisation SIP et des médias et de configurer votre pare-feu pour autoriser le trafic bidirectionnel à ces ports ainsi que leurs adresses IP.

Pour plus d’informations, voir [de signalisation SIP : noms de domaine complets et les ports de pare-feu](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports) et [du trafic multimédia : plages de ports](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges).


> [!NOTE]
> Nous vous recommandons de définir une limite de session simultanés maximale pour chaque SBC, selon le modèle SBC. Cette limite puis déclenche une notification lorsque le contrôleur SBC est en cours d’exécution ou n’atteigne déjà sa capacité.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez à quels endroits vous envisagez de déployer SBCs.<li>Choisir un nom DNS pour chaque SBC vous projetez de déployer.<li>Selon la décision de nom de domaine SBC, décider si vous prévoyez d’utiliser un certificat générique pour prendre en charge toutes les SBCs dans votre déploiement ou un certificat par SBC dédié.<li>Décider quelle autorité de certification publique vous allez obtenir les certificats pour votre SBCs à partir de.<li>Définir une paire de port/adresse IP publique pour chaque SBC vous allez déployer et décider si vous allez attribuer les adresses IP publiques pour les SBCs ou utiliser NAT.<li>Identifiez le nombre maximal de sessions simultanées que chaque SBC prend en charge ou peut gérer.<li>Décider quels SBCs vont être configurés à l’aide de contournement de média.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Chaque décision effectuée à l’aide du tableau suivant pour les SBCs du document.</ul>|


> [!TIP]
> Utilisez le modèle suivant pour documenter les détails SBC pour votre déploiement de routage Direct.
> 
> | **Nom DNS SBC (FQDN)** | **SBC marque et un modèle** | **Certificat** | **Emplacement**  | **Adresse IP** | **Port de signalisation SIP** | **NAT ?** | **Sessions simultanées maximales** | **Le contournement de média activé ?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*. contoso.com | Amsterdam | TBD | TBD | Oui | TBD | Non |
> | SBC-Asie.contoso.com | TBD | \*. contoso.com | Hong Kong SAR (香港特別行政區) | TBD | TBD | Non | TBD | Oui |
> | SBC-Africa.contoso.com | TBD | \*. contoso.com | Johannesburg | TBD | TBD | Oui | TBD | Oui |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Routage des communications vocales

Vous devez configurer le système téléphonique de Microsoft pour acheminer les appels vers les SBCs spécifiques pour le routage Direct. Vous pouvez configurer des itinéraires de communications vocales en fonction de :

-   Modèle de numéro appelé.

-   Modèle de numéro appelé + de l’utilisateur qui effectue l’appel.


Routage des appels est composé des éléments suivants :

-   Stratégie de routage voix – conteneur pour les utilisations RTC ; peuvent être attribuées à un utilisateur ou à plusieurs utilisateurs

-   Utilisations PSTN – conteneur pour les itinéraires de communications vocales et les utilisations RTC ; peuvent être partagées dans différentes stratégies de routage des communications vocales

-   Itinéraires-modèle de numéro et un ensemble de Online passerelles PSTN à utiliser pour les appels où le numéro appelant correspond au modèle de voix

-   Passerelle PSTN Online - pointeur SBC, stocke également la configuration est appliquée lorsqu’un appel est passé via le contrôleur SBC, telles que le transfert P-Asserted-Identity (PAI) ou Codecs par défaut ; peuvent être ajoutés à des itinéraires de communications vocales

Vous pouvez configurer vos itinéraires de communications vocales avec le routage Direct de coexister avec les Plans de l’appel. Cette configuration permet l’appel prévoit d’acheminer certains des appels vers les SBCs spécifiques à l’aide de routage Direct.

> [!TIP]
> SBC peut être désignés comme *actif* et de *sauvegarde*. Cela signifie que lorsque la SBC est configuré comme actif pour ce numéro de modèle, ou le numéro de modèle + utilisateur spécifique, n’est pas disponible, les appels sont acheminés vers un contrôleur SBC sauvegarde.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez la voix de routage des stratégies, les utilisations PSTN et les itinéraires de communications vocales que vous créerez à la prise en charge d’emplacements d’utilisateur ou de bureaux dans la portée de l’implémentation de routage Direct.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les stratégies de routage voix, utilisations PSTN et itinéraires de communications vocales pour votre organisation.<li>Les utilisateurs à être affecté pour chaque stratégie de routage voix que vous définissez du document.</ul>|

> [!TIP]
> Utilisez le modèle suivant pour documenter les stratégies de voix pour votre déploiement de routage Direct.
> 
> | **Utilisation PSTN** | **Itinéraire de communications vocales** | **Schéma de numéro** | **Priorité** | **SBC** | **Description** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | Nous uniquement | « Redmond 1 » | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Itinéraire actif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206 |
> | Nous uniquement | « Redmond 2 » | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | SBC3.contoso.com sbc4.contoso.com | Itinéraire alternatif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206 |
> | Nous uniquement | « Autres + 1 » | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Routage de numéros appelés + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206) |
> | International | International | \\+ d | 4 | sbc2.contoso.com sbc5.contoso.com | Itinéraire pour n’importe quel modèle de numéro |
> 
> [!IMPORTANT]
> Les utilisations PSTN dans les stratégies de routage voix sont appliquées dans l’ordre, et si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>L’appel et interopérabilité stratégies

Routage direct est uniquement pris en charge avec Microsoft Teams. Pour passer ou recevoir des appels PSTN par le biais de routage Direct, vous devez configurer les stratégies nécessaires pour garantir les appels entrants sont reçus dans les équipes.

> [!NOTE]
> Les utilisateurs activés pour le routage Direct ne peut pas émettre ou recevoir diriger des appels de routage à l’aide de Skype pour les entreprises et doit donc être déployé le client équipes.

Vous pouvez configurer les utilisateurs pour définir des équipes en tant que leur client par défaut pour les appels à une des deux méthodes suivantes :

-   Configurer l’utilisateur pour le mode équipes uniquement

-   Configurer les équipes en tant que client appelant par défaut en affectant la TeamsCallingPolicy et le TeamsInteropPolicy.

Pour plus d’informations, voir [définir les équipes Microsoft en tant que préférable appel client pour les utilisateurs](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Identifiez la méthode que vous allez utiliser pour définir des équipes comme client par défaut pour les appels.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les utilisateurs à configurer avec les stratégies d’interopérabilité et l’appel du document.</ul>|

> [!IMPORTANT]
> Lorsqu’un utilisateur est configuré pour les équipes seule, cet utilisateur n’est plus connecter à Skype pour les entreprises.

Pour que vos utilisateurs à l’onglet appels dans le client d’équipes, vous devez activer privée appelant au niveau de l’organisation du client. Pour plus d’informations sur l’activation des appels privées, voir [Activer d’appel pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions de service de document

Utilisez les informations dans les sections précédentes de cet article pour documenter vos décisions de service. En règle générale, cette documentation contient les sections principales suivantes :

-   Liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels

-   Détails sur la configuration de la messagerie vocale

-   Affectation de licence pour les utilisateurs de routage d’un système téléphonique Direct

-   Détails de configuration SBC

-   Stratégie et les détails de routage de voix

-   Détails de la stratégie d’interopérabilité de base et l’appel

<!--ENDOFSECTION-->
