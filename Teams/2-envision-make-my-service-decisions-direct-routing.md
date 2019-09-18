---
title: Prendre des décisions pour le service de systèmes téléphoniques avec forfaits d’appels -Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: En savoir plus sur le routage direct, les licences et les décisions qui doivent être prises.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57b3c8950f7e1618f578862290e8fb1696b6bc0
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018778"
---
# <a name="make-my-service-decisions"></a>Prendre des décisions de service

Pour planifier l’implémentation technique du routage direct du système téléphonique (« routage directe »), vous devez mettre en place une série de décisions sur le service pour mieux préparer votre organisation à la mise en œuvre d’une solution qui répond aux besoins de l’entreprise que vous avez définis.

## <a name="calling-in-teams"></a>Appel dans teams

Grâce à Microsoft Teams, vos utilisateurs peuvent passer et recevoir des appels téléphoniques à partir du réseau téléphonique public commuté (RTC). Vos utilisateurs peuvent utiliser leurs propres numéros de téléphone dédiés pour le placement et la réception d’appels nationaux et internationaux (y compris la boîte vocale) depuis l’application cliente Teams.

## <a name="direct-routing"></a>Routage direct

Pour permettre aux utilisateurs d’équipes de passer et de recevoir des appels RTC, ils doivent être activés pour le système téléphonique, une fonctionnalité d’Office 365.

Pour activer la connectivité au réseau PSTN, vous pouvez utiliser le routage direct pour permettre aux membres de votre organisation de passer et de recevoir des appels téléphoniques extérieurs à l’organisation via PSTN.

Le routage direct permet à un fournisseur tiers de vous offrir la possibilité de continuer à utiliser vos liaisons RTC existantes fournies par votre fournisseur de services RTC. Cela permet le déploiement dans des pays où le système téléphonique avec des plans d’appel (« plans d’appel ») n’est pas disponible, ou dans les déploiements où un contrat de prestataire de services RTC existant doit être maintenu ou l’interopérabilité avec certains systèmes locaux est Obligatoire.

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>Disponibilité du routage direct

Le routage direct est disponible dans tous les pays où Office 365 est disponible. Pour obtenir la liste de ces pays, voir [disponibilité internationale](https://products.office.com/business/international-availability) .

Après confirmation de l’obtention de la fonctionnalité du système téléphonique par votre organisation, compilez la liste des emplacements des utilisateurs ou des bureaux où vous allez mettre en œuvre le système téléphonique, en fonction de la liste des pays et régions disponibles. Identifiez également les utilisateurs pour lesquels vous souhaitez activer les offres d’appels ou le routage direct de chaque emplacement.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Identifiez les emplacements des utilisateurs ou les bureaux dans lesquels vous implémenterez le système téléphonique.<li>Identifiez les utilisateurs pour lesquels vous souhaitez activer les offres d’appels ou le routage direct de chaque emplacement.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements des utilisateurs ou les bureaux à activer pour le système téléphonique.<li>Documentez la liste des utilisateurs pour lesquels vous souhaitez activer les offres d’appels ou le routage direct de chaque emplacement</ul>|

> [!TIP]
> Vous trouverez ci-dessous un exemple de liste de sites de routage direct.
> 
> | **Bureau**                     | **Emplacement**   | **Service de système téléphonique** |
> |--------------------------------|----------------|--------------------------|
> | 1 Eppîng Road                | Australie      | Service PSTN hérité |
> | 100 Cyberport Road             | Hong Kong R.A.S.  | Routage direct via le système téléphonique |
> | 1 Marina Boulevard           | Singapour      | Routage direct via le système téléphonique |
> | 32 London Bridge Street        | Royaume-Uni | Système téléphonique avec forfaits d’appels |
> | 39 quai du Président Roosevelt | France         | Système téléphonique avec forfaits d’appels |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Le système téléphonique nécessite que tous les utilisateurs de votre organisation disposent d’un numéro de téléphone unique de numérotation vers l’intérieur. Avec le routage direct, les numéros de téléphone et les services d’urgence sont fournis par votre fournisseur de services RTC.

> [!NOTE]
> Le routage direct permet à vos utilisateurs de continuer à utiliser leurs propres numéros de téléphone fournis par le fournisseur de services RTC.
> 
> [!TIP]
> Vous pouvez utiliser le modèle suivant pour documenter les détails des numéros de téléphone.
> 
> |Utilisateur |Numéro de téléphone |
> |-----|-------------|
> |Emily Braun | commande + 44 23 4567 8901 |
> |Lidia Holloway | commande + 44 23 4567 89112 |
> |Louis Lahr | commande + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Messagerie vocale

La messagerie vocale Cloud, optimisée par les services de boîte vocale Azure, prend en charge les dépôts de boîte vocale dans les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de courrier tiers.

La messagerie vocale Cloud inclut la transcription de la boîte vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription de la boîte vocale pour des utilisateurs spécifiques ou pour tout le monde au sein de l’organisation. Si votre organisation a décidé de maintenir la transcription de la boîte vocale activée, vous devez également envisager d’activer ou de désactiver le masquage de la boîte vocale. Pour plus d’informations, reportez-vous à [la rubrique Configuration des stratégies de messagerie vocale pour votre organisation](set-up-phone-system-voicemail.md)

Pour plus d’informations sur la boîte vocale dans l’implémentation d’un système téléphonique, voir [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décidez si vous voulez activer la boîte vocale Cloud dans votre implémentation de routage direct.<li>Décidez si vous activez ou désactivez la transcription de la boîte vocale et le masquage des blasphèmes de transcription de la boîte vocale au sein de l’organisation ou pour des utilisateurs spécifiques.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, documentez les points de décision pour prendre en charge la messagerie vocale Cloud.<li>Si vous activez ou désactivez la boîte vocale, la transcription de la boîte vocale et le masquage par inconvenances de transcription vocale uniquement pour des utilisateurs spécifiques, documentez la liste des utilisateurs.</ul>|

> [!TIP]
> Les détails de la boîte vocale Cloud pour l’implémentation des plans d’appels peuvent être décrits comme suit :
> 
> | **User**         | **Boîte aux lettres Exchange** | **Activer la boîte vocale ?** | **Transcription de la boîte vocale** | **Masquage de l’blasphème de transcription de la boîte vocale** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | Oui                   | Activé                     | Activé                                       |
> | Lidia Holloway   | Online               | Oui                   | Activé                     | Désactivé                                      |
> | Louis Lahr       | Sur site          | Oui                   | Activé                     | Activé                                       |
> | Marcel Beauchamp | Sur site          | Oui                   | Désactivé                    | S/O                                           |
> | Rachelle Cormier | Online               | Oui                   | Désactivé                    | S/O                                           |
> | Isabell Potvin   | Sur site          | Oui                   | Désactivé                    | S/O                                           |
> 
> [!NOTE]
> Pour utiliser les équipes et la messagerie vocale, vos utilisateurs doivent disposer de boîtes aux lettres Exchange. Pour plus d’informations, voir [Comment Exchange et Microsoft teams interagissent](exchange-teams-interact.md) .

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>Gestion des licences pour le routage direct

Si votre organisation envisage d’utiliser le routage direct, vous devez obtenir les licences requises. Les utilisateurs du routage direct doivent avoir les licences suivantes affectées dans Office 365 :

-   Système Microsoft Phone

-   Microsoft Teams

-   Audioconférence,

Une licence d’audioconférence est nécessaire pour ajouter des participants externes à des réunions planifiées en les appelant ou en fournissant le numéro de connexion. Lors de l’appel d’un participant externe, le service d’audioconférence passe l’appel à l’aide des fonctionnalités d’appel en ligne. La licence d’audioconférence est facultative et est uniquement requise pour les utilisateurs qui organiseront des conférences d’équipes incluant des conférences audio.


> [!NOTE]
> Pour fournir des numéros de téléphone de conférence rendez-vous gratuits et prendre en charge les appels vers des numéros internationaux, vous devez configurer des [crédits de communication](what-are-communications-credits.md) pour votre organisation.

Les services d’audioconférence et de téléphonie peuvent être dotés d’une licence séparée en tant que services complémentaires pour les clients existants disposant d’offres d’abonnement Office 365 E3 ou E1 ; ils sont déjà inclus dans le cadre du forfait d’abonnement Office 365 E5.

> [!TIP]
> Vous pouvez également utiliser le routage direct pour les utilisateurs qui sont activés pour les offres d’appels lors du routage de leurs appels vers des PBX tiers. Pour en savoir plus, voir gestion [des licences et autres exigences relatives au routage direct](direct-routing-plan.md#licensing-and-other-requirements).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne dispose pas de la licence de système téléphonique requis, décidez si vous allez acquérir la licence du système téléphonique en accroissant vos abonnements Office 365 existants ou en acquérant le service de complément système téléphonique.<li>Décidez si vous aurez besoin de crédits de communication pour votre implémentation du routage direct.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter les groupes de divisions, services, bureaux ou groupes d’utilisateurs vous devez attribuer une licence de système téléphonique.<li>Si l’étendue de la fonction de conférence rendez-vous, documentez la Division, le service, les bureaux ou les groupes d’utilisateurs, vous activerez les crédits de communication.</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Remarques sur Office 365

Tout utilisateur qui sera activé pour le routage direct doit être hébergé dans Office 365. Pour les déploiements hybrides avec Skype entreprise Server ou Lync Server en local, vous devez déplacer des utilisateurs vers Skype entreprise Online avant de les configurer de manière à utiliser le routage direct avec Teams.

Tous les utilisateurs qui font partie du champ d’implémentation du routage direct doivent être activés pour Teams.

Votre client Office 365 doit être activé avec un ou plusieurs domaines, car le domaine \*par défaut. onmicrosoft.com ne peut pas être utilisé avec le routage direct. Pour plus d’informations sur les domaines et les clients 365 Office, voir [FAQ sur les domaines](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si les utilisateurs doivent être migrés vers Skype entreprise Online pour prendre en charge le routage direct.<li>Identifiez les utilisateurs qui doivent être activés pour Teams.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez la liste des utilisateurs qui doivent être migrés vers Skype entreprise Online et activez pour Teams.</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>Considérations relatives aux SBC

Vous devez utiliser des contrôleurs de frontière de session certifiés et pris en charge (SBCs) qui doivent être associés au service de routage direct pour fournir une connectivité PSTN à vos utilisateurs. Pour obtenir la liste des [contrôleurs de frontière de session, voir prises en charge](direct-routing-plan.md#supported-session-border-controllers-sbcs).

Selon votre environnement, le nombre d’emplacements et les exigences en matière de routage vocal, il est possible que vous deviez déployer plusieurs éléments SBCs pour prendre en charge votre base d’utilisateurs.

### <a name="sbc-domain-names"></a>Noms de domaine SBC

Chaque SBC que vous jumelez avec le routage direct doit avoir un nom DNS unique. Les noms DNS de SBC doivent être issus de l’un des noms de domaine inscrits dans le client Office 365. Si votre client a été affecté de plusieurs noms de domaine, vous pouvez utiliser l’un de ces noms de domaine lors de la planification de vos noms DNS SBCs.

> [!IMPORTANT]
> L’utilisation de *. onmicrosoft.com pour le nom DNS de SBC n’est pas autorisée.

### <a name="certificates"></a>Certificats

Chaque SBC déployé avec le routage direct nécessite un certificat obtenu à partir d’une liste des autorités de certification prises en charge. Le certificat doit inclure le nom DNS du SBC dans l’objet, le nom de l’objet ou le nom du sujet.

> [!NOTE]
> L’utilisation de certificats génériques avec SBCs est également prise en charge.

Pour plus d’informations et une liste des autorités de certification prises en charge, voir [certificat de confiance public pour l’SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).


### <a name="sbc-ip-addresses-and-ports"></a>Adresses IP et ports de SBC

Chaque SBC doit être configuré à l’aide d’une adresse IP publique accessible à partir de centres de discussion Office 365. Vous pouvez également configurer la traduction d’adresses réseau (NAT) pour publier votre connexion SBCs aux centres de datacenters Office 365.

SBCs nécessite une connectivité bidirectionnelle pour communiquer avec les services Cloud pour le signalement et le contenu multimédia. Le signalement est géré par le composant appelé *proxy SIP*et le média est géré par les *processeurs de médias*.

Vous devez définir des numéros de port spécifiques sur chaque SBC pour les signaux et éléments multimédias SIP, et configurer vos pare-feu pour autoriser le trafic bidirectionnel vers ces ports et leurs adresses IP associées.

Pour plus d’informations, reportez-vous à la section [signalisation SIP : FQDN](direct-routing-plan.md#sip-signaling-fqdns) et [trafic multimédia : plages de ports](direct-routing-plan.md#media-traffic-port-ranges).


> [!NOTE]
> Nous vous recommandons vivement de définir le nombre maximal de sessions simultanées pour chaque SBC, en fonction du modèle SBC. Cette limite déclenche alors une notification lorsque l’SBC est en cours d’exécution, ou près de sa capacité.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les emplacements que vous déploierez SBCs.<li>Déterminez le nom DNS de chaque SBC que vous envisagez de déployer.<li>Sur la base de la décision de nom de domaine SBC, décidez si vous allez utiliser un certificat générique pour la prise en charge de tout SBCs dans votre déploiement ou d’un certificat dédié par SBC.<li>Déterminez les autorités de certification publiques auxquelles vous souhaitez accéder aux certificats de votre SBCs.<li>Définissez une paire adresse IP/port publique pour chaque SBC que vous déploierez, et décidez si vous allez affecter les adresses IP publiques au protocole SBCs ou utiliser la traduction d’adresses réseau (NAT).<li>Identifiez le nombre maximal de sessions simultanées prises en charge ou peut gérer chaque SBC.<li>Déterminez les éléments SBCs à configurer à l’aide du contournement multimédia.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez chaque décision apportée pour l’SBCs en utilisant l’exemple de tableau suivant.</ul>|


> [!TIP]
> Utilisez le modèle suivant pour documenter les détails d’un SBC pour votre déploiement de routage direct.
> 
> | **Nom de domaine complet (FQDN)** | **Marque et modèle SBC** | **Certificat** | **Emplacement**  | **Adresse IP** | **Port de signalisation SIP** | **NAT?** | **Nombre maximal de sessions simultanées** | **Contournement de média activé ?** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | DÉFINIR | \*. contoso.com | Amsterdam | DÉFINIR | DÉFINIR | Oui | DÉFINIR | Non |
> | SBC-Asia.contoso.com | DÉFINIR | \*. contoso.com | Hong Kong R.A.S. | DÉFINIR | DÉFINIR | Non | DÉFINIR | Oui |
> | SBC-Africa.contoso.com | DÉFINIR | \*. contoso.com | Johannesbourg | DÉFINIR | DÉFINIR | Oui | DÉFINIR | Oui |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>Itinéraires vocaux

Vous devez configurer le système Microsoft Phone pour acheminer les appels vers l’objet SBCs spécifique pour le routage direct. Vous pouvez configurer des itinéraires vocaux en fonction de :

-   Appelées modèle numérique.

-   Appelées modèle de numéro + l’utilisateur qui effectue l’appel.


Le routage des appels se compose des éléments suivants :

-   Politique de routage de la voix-conteneur d’utilisation PSTN ; peuvent être affectés à un utilisateur ou à plusieurs utilisateurs

-   Usages PSTN : conteneur des itinéraires vocaux et des utilisations PSTN ; peuvent être partagés dans différentes politiques de routage vocal

-   Itinéraires vocaux : modèle numérique et ensemble de passerelles RTC en ligne à utiliser pour les appels dont le numéro de téléphone correspond au modèle

-   Le pointeur passerelle RTC en ligne sur SBC vous permet également de stocker la configuration appliquée lors de l’envoi d’un appel via SBC, par exemple en transférant l’identité P-assertion (PAI) ou les codecs préférés. peuvent être ajoutés aux itinéraires vocaux

Vous pouvez configurer vos itinéraires vocaux avec le routage direct pour cohabiter avec les offres d’appels. Cette configuration permet aux plans d’appel d’acheminer certains appels vers des SBCs spécifiques en utilisant le routage direct.

> [!TIP]
> SBCs peut être désignée comme *active* et *Backup*. Cela signifie que lorsque l’SBC configuré comme étant actif pour ce modèle de nombre (ou modèle de nombre + utilisateur spécifique) n’est pas disponible, les appels sont dirigés vers un SBC de sauvegarde.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez les stratégies de routage de voix, les usages RTC et les itinéraires vocaux que vous allez créer pour prendre en charge les emplacements des utilisateurs ou les bureaux dans le cadre de l’implémentation du routage direct.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les stratégies de routage de messages vocaux, les utilisations RTC et les itinéraires vocaux pour votre organisation.<li>Documentez les utilisateurs auxquels vous voulez attribuer une stratégie de routage vocale que vous définissez.</ul>|

> [!TIP]
> Utilisez le modèle suivant pour documenter les stratégies vocales pour votre déploiement de routage direct.
> 
> | **Utilisation PSTN** | **Route vocale** | **Schéma de numéro** | **Priorité** | **SBC** | **Description** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | États-Unis uniquement | "Redmond 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | 1 | sbc1.contoso.com sbc2.contoso.com | Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX |
> | États-Unis uniquement | "Redmond 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | 2 | sbc3.contoso.com sbc4.contoso.com | Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX |
> | États-Unis uniquement | "Other + 1" | \^\\commande + 1\\({10}d)\$ | 3 | sbc5.contoso.com sbc6.contoso.com | Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX) |
> | International | International | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | Itinéraire pour n’importe quel modèle numérique |
> 
> [!IMPORTANT]
> Les utilisations RTC dans les stratégies de routage vocal sont appliquées dans l’ordre, et si une correspondance est trouvée lors de la première utilisation, les autres utilisations ne sont jamais évaluées.

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>Politiques d’appel et d’interopérabilité

Le routage direct est uniquement pris en charge par Microsoft Teams. Pour passer ou recevoir des appels RTC via le routage direct, vous devez configurer les stratégies nécessaires pour vérifier que les appels entrants sont reçus dans Teams.

> [!NOTE]
> Les utilisateurs activés pour le routage direct ne peuvent pas passer ou recevoir des appels de routage direct à l’aide de Skype entreprise, et doivent donc déployer le client Teams.

Vous pouvez configurer vos utilisateurs de manière à ce qu’ils configurent les équipes en tant que client préféré pour les appels par l’une des deux méthodes suivantes :

-   Configurer l’utilisateur pour le mode équipes uniquement

-   Configurez teams en tant que client appelant préféré en attribuant le TeamsCallingPolicy et le TeamsInteropPolicy.

Pour plus d’informations, reportez-vous à la section [affectation uniquement du mode équipes aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams](direct-routing-configure.md#assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez l’approche à utiliser pour définir teams en tant que client préféré pour les appels.</ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les utilisateurs à configurer à l’aide de stratégies d’interopérabilité et d’appel.</ul>|

> [!IMPORTANT]
> Lorsqu’un utilisateur est configuré pour le mode équipe uniquement, cet utilisateur ne peut plus se connecter à Skype entreprise.

Pour que vos utilisateurs puissent voir l’onglet appels dans le client Microsoft Teams, vous devez activer les appels privés au niveau de l’Organisation pour le client. Pour plus d’informations sur l’activation des appels privés, voir [activer l’appel pour Microsoft teams](direct-routing-configure.md) .


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Décisions relatives au service de documents

Utilisez les informations des sections précédentes de cet article pour documenter les décisions de votre service. En règle générale, cette documentation contient les sections principales suivantes :

-   Système téléphonique avec une liste de plans d’appel d’activation de site

-   Détails de la configuration de la boîte vocale

-   Attribution de licence pour les utilisateurs du routage direct du système téléphonique

-   Détails de la configuration de SBC

-   Politique de routage de la voix et informations de routage

-   Détails de la stratégie d’interopérabilité et d’appels

<!--ENDOFSECTION-->
