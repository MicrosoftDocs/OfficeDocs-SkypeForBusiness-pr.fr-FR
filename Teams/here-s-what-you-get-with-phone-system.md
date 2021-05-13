---
title: Les avantages du système téléphonique
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Découvrez les fonctionnalités, la disponibilité et comment planifier et configurer Téléphone Microsoft système pour votre entreprise. '
ms.openlocfilehash: 877c7d49710821632477803cbc36c8009411cd3a
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469726"
---
# <a name="heres-what-you-get-with-phone-system"></a>Les avantages du système téléphonique

Cet article décrit Système téléphonique fonctionnalités principales. Pour plus d’informations sur l’utilisation de Système téléphonique en tant que remplacement de votre Exchange de branche privée (PBX) et les options de connexion au réseau téléphonique commuté (PSTN), consultez les informations [Système téléphonique.](what-is-phone-system-in-office-365.md)

Les clients sont disponibles pour PC, Mac et appareils mobiles, ce qui fournit des fonctionnalités sur les appareils qui vont des tablettes et téléphones mobiles aux PC et téléphones IP de bureau. Pour plus d’informations, [voir Obtenir des clients pour Microsoft Teams.](get-clients.md)

 > [!Note]
> Pour plus d’informations sur Teams de téléphone sur différentes plateformes, voir Teams [fonctionnalités par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>Système téléphonique fonctionnalités

Système téléphonique fournit les fonctionnalités suivantes. Sauf indication contraire, les fonctionnalités sont disponibles dans Teams et Skype Entreprise Online.
  
|||
|:-----|:-----|
|**Système téléphonique fonctionnalité** <br/> |**Description** <br/> |
|[Attendant automatiques cloud](what-are-phone-system-auto-attendants.md) <br/> |Vous permet de créer un système de menus qui permet aux appelants externes et internes de localiser et de placer ou de transférer des appels à des utilisateurs de l’entreprise ou à des services de votre organisation.  <br/> Notez *qu’il n’est* pas nécessaire que les utilisateurs soient activés pour recevoir des appels du attendant automatique. |
|[Files d’attente d’appels cloud](create-a-phone-system-call-queue.md) <br> |Vous permet de configurer la façon dont les files d’attente d’appels sont gérées pour votre organisation : par exemple, configurer les salutations et la musique en attente, rechercher le prochain agent d’appel disponible pour gérer l’appel, etc.  <br/> Notez que les *utilisateurs* doivent être activés pour recevoir des appels à partir d’une file d’attente d’appels.|
|Attente musicale | Lit la musique par défaut définie par le service lorsqu’un appel externe à partir du réseau téléphonique commuté (PSTN) est mis en attente. Cette fonctionnalité fonctionne pour les appels PSTN-to-Teams ainsi que pour les appels effectués dans une file d’attente d’appels. Cette fonctionnalité fournit la parité des notifications en attente avec d’autres plateformes. Cette fonctionnalité est configurable par l’administrateur, mais [pour l’instant uniquement via PowerShell.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) La musique d’attente n’est pas non plus prise en charge dans le transfert consultatif d’un appel PSTN.|
|Démarrage d'un appel/réponse à un appel (par nom et numéro)  <br/> |Permet aux utilisateurs de répondre aux appels entrants d’un simple appel et de placer des appels sortants en composant le numéro de téléphone complet ou en cliquant sur un nom dans le client.  <br/> |
|[Options de forwardage d’appel et sonnerie simultanée](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |Permet aux utilisateurs de configurer des règles de forwarding afin que les appels soient suivis n’importe où, ou de les retourner à des collègues ou à des messages vocaux.  <br/> |
|[Regroupement d’appels et transfert vers le groupe](call-sharing-and-group-call-pickup.md) <br/> | Permet aux utilisateurs de partager des appels entrants avec des collègues afin que ces derniers répondent à des appels qui se produisent alors que l’utilisateur n’est pas disponible. Moins perturbateur pour les destinataires que d’autres formes de partage d’appel (comme le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils souhaitent être informés d’un appel partagé entrant. |
|[Transfert d’appel et transfert consultatif](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |Permet aux utilisateurs de transférer des appels à une autre personne. Ou, s’il doit quitter son bureau mais que vous souhaitez poursuivre la conversation, il peut transférer les appels à partir de son ordinateur ou de son téléphone IP vers son téléphone mobile.  <br/> |
|[Transfert vers la messagerie vocale mid call*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | Permet aux utilisateurs de transférer vers la messagerie vocale pendant un appel. |
|[Parcage d’appel et récupération](call-park-and-retrieve.md)  <br/> | Permet aux utilisateurs de mettre un appel en attente dans le service Teams dans le cloud. Lorsqu’un appel est paré, le service génère un code unique pour l’extraction des appels. L’utilisateur qui a parké l’appel ou une autre personne peut ensuite utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel. <br/> |
|Appeler un numéro de téléphone à partir de la recherche  <br/> | Permet aux utilisateurs de placer un appel à partir de la zone de recherche à l’aide de la commande /call et de spécifier un nom ou un numéro. <br/> |
|[ID de l’appelant](how-can-caller-id-be-used-in-your-organization.md)  <br/> |Les appels en provenance de l’entreprise affichent un ID d’appelant détaillé qui permet d’obtenir des informations de l’annuaire d’entreprise, avec l’ID d’image et la fonction plutôt qu’un numéro de téléphone. Pour les appels provenant de numéros de téléphone externes, l’ID d’appelant fourni par le fournisseur de services téléphoniques s’affiche. Si les numéros de téléphone externes sont des numéros secondaires dans l’annuaire de l’entreprise, les informations de l’annuaire d’entreprise sont affichées.  <br/> |
|Changement de périphériques  <br/> |Permet aux utilisateurs de lire un appel ou une réunion sur un autre périphérique HID connecté à Teams ; par exemple, passer des haut-parleurs de son PC à un casque.   <br/> |
|Routage des appels en fonction de la présence <br/> |Contrôle les communications entrantes avec présence, ce qui permet à l’utilisateur de bloquer toutes les communications entrantes à l’exception de celles spécifiquement indiquées.  <br/> |
|[Pavé de numérotation intégré](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | Permet aux utilisateurs de composer par nom ou par numéro n’importe où dans la barre de recherche et dans le pavé de numérotation, ce qui accélère le processus d’appels sortants. <br/> |
|Appels fédérés  <br/> |Permet aux utilisateurs de se connecter, communiquer et collaborer en toute sécurité avec des utilisateurs dans des clients fédérés.  <br/> |
|[Effectuer et recevoir un appel vidéo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | Si le compte de l’utilisateur est activé pour les appels vidéo, il peut effectuer des appels vidéo afin de faire face à ses contacts. Tout ce dont ils ont besoin, c’est d’une caméra, des haut-parleurs et du microphone de leur ordinateur. Les utilisateurs peuvent également utiliser un casque si leur ordinateur n’est pas connecté à un périphérique audio intégré.<br/> |
|[Messagerie vocale cloud*](set-up-phone-system-voicemail.md) <br/> | Lorsqu’un utilisateur reçoit un message vocal, il est remis dans sa boîte aux lettres Exchange courrier électronique avec le message vocal en pièce jointe. Les utilisateurs peuvent écouter leurs messages sur leur téléphone de bureau certifié et sur toutes Teams ou Skype Entreprise applications. Le support pour la transcription de messages vocaux est ajouté depuis mars 2017 et activé par défaut pour toutes les organisations et tous les utilisateurs.   <br/> |
|[Paramètres utilisateur de la messagerie vocale cloud*](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permet aux utilisateurs de configurer les paramètres de leur client pour les messages d’accueil de la messagerie vocale, les règles de répondeur téléphonique et la langue du message d’accueil, y compris les messages d’accueil d’arrêt du bureau.   |
|[Sonnerie secondaire](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | Les utilisateurs qui ont plusieurs périphériques de haut-parleur connectés à leur PC peuvent choisir de configurer un appareil secondaire pour qu’il sonne en plus de leur haut-parleur par défaut. Par exemple, un utilisateur avec un casque connecté au PC et aux haut-parleurs de bureau peut choisir de sonner à la fois le casque et les haut-parleurs de bureau lorsqu’un appel arrive afin de ne pas manquer un appel.  |
|[Alertes de sonnerie distinctes](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams uniquement)<br/> |Permet aux utilisateurs de choisir des sonneries distinctes pour les appels normaux, les appels transmis et les appels délégués afin de distinguer le type d’appel.  <br/> |
|[Mode partage de lignes](shared-line-appearance.md) <br/> | Permet aux utilisateurs de partager leur ligne téléphonique afin qu’un autre utilisateur puisse effectuer et recevoir des appels en son nom.|
|[Occupé(e)](teams-calling-policy.md) (Teams uniquement) <br/> | Stratégie d’appel qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est : <ul><li>dans un appel </li><li>dans une conférence</li><li>un appel est mis en attente. </li></ul> L’appelant recevra l’une des réponses suivantes : <ul><li>entendre un signal Occupé lorsque l’appelant est au téléphone</li> <li>seront acheminés en conséquence vers les paramètres sans réponse de l’utilisateur. Une option permet à l’appelant de laisser un message vocal à l’utilisateur qui est déjà en appel.</li></ul> L’appelant reçoit une notification d’appel manqué, mais ne peut pas répondre aux appels entrants. Cette fonctionnalité est désactivée par défaut, mais peut être désactivée par l’administrateur client.|
|[Blocage d’appel](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | Permet aux utilisateurs d’ajouter des numéros de téléphone (PSTN) à une liste bloquée de sorte que l’appel suivant de ce numéro soit bloqué.|
|[Téléphones en zone commune](set-up-common-area-phones.md) <br/> | Un téléphone local commun est généralement placé dans une zone telle qu’une salle d’attente ou une salle de conférence et le rend accessible à plusieurs personnes. Les téléphones en zone commune sont configurer en tant qu’appareils plutôt que comme utilisateurs et peuvent se connecter automatiquement à un réseau.|
|[Prise en charge de la dérivation](direct-routing-plan-media-bypass.md) média (Teams routage direct uniquement) <br/> | Pour de meilleures performances, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via Téléphone Microsoft système informatique. |


\* Les utilisateurs n’ont pas besoin d’être activés pour utiliser les fonctionnalités de messagerie vocale.

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilité dans Cloud de la communauté du secteur public nuages haut et de DoD
<a name="bkmk_setup"> </a>

Les fonctionnalités suivantes ne sont pas encore disponibles dans Cloud de la communauté du secteur public Nuages haut et dod nuages. 

- [Paramètres d’appel pour la sonnerie secondaire, la messagerie vocale et la délégation améliorée](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transfert vers la messagerie vocale mid call](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Appeler un numéro de téléphone à partir de la barre de recherche
- Attente musicale
- Recherche de numéro inversé d’Azure AD

## <a name="related-topics"></a>Sujets associés

- [Qu’est-ce que le système téléphonique ?](what-is-phone-system-in-office-365.md)
- [Appel vocal dans le nuage dans Microsoft Teams](cloud-voice-landing-page.md)
- [Configurer le système téléphonique](setting-up-your-phone-system.md)
- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Routage direct via le système téléphonique](direct-routing-landing-page.md)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Tarification pour Système téléphonique](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams infrastructure bureau virtualisé avec appels et réunions](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
