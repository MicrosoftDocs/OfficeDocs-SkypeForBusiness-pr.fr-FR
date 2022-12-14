---
title: Les avantages du système téléphonique
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Découvrez les fonctionnalités, la disponibilité et comment planifier et configurer Microsoft système téléphonique pour votre entreprise. '
ms.openlocfilehash: 118f2d52193583149e881bf564fb1df616bf108c
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392244"
---
# <a name="heres-what-you-get-with-phone-system"></a>Les avantages du système téléphonique

Cet article décrit les fonctionnalités du système téléphonique. Pour plus d’informations sur l’utilisation du système téléphonique comme remplacement pbx (Private Branch Exchange) et les options de connexion au réseau téléphonique commuté public (RTC), consultez [Qu’est-ce que le système téléphonique](what-is-phone-system-in-office-365.md)?

Les clients sont disponibles pour PC, Mac et mobile, ce qui fournit des fonctionnalités sur les appareils, des tablettes et téléphones mobiles aux PC et aux téléphones IP de bureau. Pour plus d’informations, consultez [Obtenir des clients pour Microsoft Teams](get-clients.md).

 > [!Note]
> Pour plus d’informations sur les systèmes téléphoniques Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Pour utiliser les fonctionnalités du système téléphonique, votre organisation doit disposer d’une licence de système téléphonique. Pour plus d’informations sur les licences, voir [Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

N’oubliez pas que la plupart des fonctionnalités vous obligent à attribuer la licence système téléphonique et à vous assurer que les utilisateurs sont « vocaux activés ». Pour attribuer la licence, utilisez [l’applet de commande Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) et définissez le paramètre **EnterpriseVoiceEnabled** sur $true. Certaines fonctionnalités, telles que le standard automatique cloud, ne nécessitent pas qu’un utilisateur soit activé par la voix. Les exceptions sont appelées dans le tableau ci-dessous.
  
## <a name="phone-system-features"></a>Fonctionnalités du système téléphonique

Le système téléphonique fournit les fonctionnalités suivantes.
  
|Fonctionnalité système téléphonique  |Description |
|:-----|:-----|
|[Standards automatiques cloud](what-are-phone-system-auto-attendants.md)  |Vous permet de créer un système de menus qui permet aux appelants externes et internes de localiser, de placer ou de transférer des appels vers des utilisateurs ou des services de l’entreprise au sein de votre organisation.  <br/> Notez que les utilisateurs *n’ont pas* besoin d’être activés par la voix pour recevoir des appels de la numérotation du standard automatique par nom, composer par numéro dans l’annuaire. *Les utilisateurs* doivent être activés par la voix pour recevoir des appels à partir des options de menu du standard automatique. |
|[Files d’attente d’appels cloud](create-a-phone-system-call-queue.md) <br> |Vous permet de configurer la façon dont les files d’attente d’appels sont gérées pour votre organisation : par exemple, configurer des messages d’accueil et de la musique en attente, rechercher l’agent d’appel disponible suivant pour gérer l’appel, etc.  <br/> Notez *que les utilisateurs* doivent être activés par la voix pour recevoir des appels à partir d’une file d’attente d’appels.|
|[Attente musicale](music-on-hold.md) | Lit la musique par défaut définie par le service ou la musique personnalisée chargée par l’administrateur du locataire lorsqu’un appel externe à partir du réseau téléphonique commuté public (RTC) est mis en attente. Cette fonctionnalité fonctionne pour les appels RTC un-à-un vers Teams en plus des appels effectués vers une file d’attente d’appels. Cette fonctionnalité fournit une parité de notification en attente avec d’autres plateformes. |
|Démarrage d'un appel/réponse à un appel (par nom et numéro)   |Permet aux utilisateurs de répondre aux appels entrants avec une interaction tactile et de passer des appels sortants en composant le numéro de téléphone complet ou en cliquant sur un nom dans le client.   |
|[Options de transfert d’appel et sonnerie simultanée](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Permet aux utilisateurs de configurer des règles de transfert pour que les appels puissent aller avec eux n’importe où, ou les appels peuvent être transférés à des collègues ou à la messagerie vocale.   |
|[Prise d’appel de groupe et transfert vers le groupe](call-sharing-and-group-call-pickup.md)  | Permet aux utilisateurs de partager des appels entrants avec des collègues afin qu’ils puissent répondre aux appels qui se produisent lorsque l’utilisateur n’est pas disponible. Moins perturbant pour les destinataires que d’autres formes de partage d’appels (telles que le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils souhaitent être avertis d’un appel partagé entrant. |
|[Transférer un appel et un transfert consultatif](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Permet aux utilisateurs de transférer les appels à une autre personne. Ou, s’ils doivent quitter leur bureau mais veulent poursuivre la conversation, ils peuvent transférer les appels de leur PC ou téléphone IP vers leur téléphone cellulaire.  <br/> Notez que les utilisateurs *n’ont pas* besoin d’être activés par la voix pour recevoir les appels transférés d’un autre utilisateur. |
|[Transfert vers la messagerie vocale à mi-appel*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Permet aux utilisateurs de transférer vers la messagerie vocale pendant un appel. |
|[Parcage d’appel et récupération](call-park-and-retrieve.md)   | Permet aux utilisateurs de placer un appel en attente dans le service Teams dans le cloud. Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels. L’utilisateur qui a parqué l’appel ou une autre personne peut alors utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel.  |
|Appeler le numéro de téléphone à partir de la recherche   | Permet aux utilisateurs de passer un appel à partir de la zone de recherche en utilisant la commande /call et en spécifiant un nom ou un numéro.  |
|[ID de l’appelant](how-can-caller-id-be-used-in-your-organization.md)   |Les appels provenant de l’intérieur de l’entreprise affichent un ID d’appelant détaillé qui extrait des informations de l’annuaire de l’entreprise, montrant l’ID d’image et le poste au lieu d’un simple numéro de téléphone. Pour les appels à partir de numéros de téléphone externes, l’ID de l’appelant fourni par le fournisseur de services téléphoniques s’affiche. Si les numéros de téléphone externes sont des numéros secondaires dans l’annuaire de l’entreprise, les informations de l’annuaire d’entreprise s’affichent.   |
|Changement de périphériques   |Permet aux utilisateurs de lire un appel ou une réunion sur un autre appareil HID connecté à Teams ; par exemple, passer de leurs haut-parleurs de PC à un casque.    |
|Routage des appels basé sur la présence  |Contrôle les communications entrantes avec présence, ce qui permet à l’utilisateur de bloquer toutes les communications entrantes à l’exception de celles spécifiquement indiquées.   |
|[Pavé de numérotation intégré](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Permet aux utilisateurs de composer par nom ou par numéro n’importe où dans la barre de recherche et dans le pavé de numérotation, ce qui accélère le processus d’appels sortants.  |
|Appel fédéré   |Permet aux utilisateurs de se connecter, de communiquer et de collaborer en toute sécurité avec les utilisateurs dans des locataires fédérés.   |
|[Passer et recevoir un appel vidéo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Si le compte de l’utilisateur est activé pour les appels vidéo, l’utilisateur peut passer des appels vidéo en face à face avec ses contacts. Tout ce dont ils ont besoin, c’est d’une caméra, des haut-parleurs et du microphone de leur ordinateur. Les utilisateurs peuvent également utiliser un casque si leur ordinateur n’a pas de périphérique audio intégré. |
|[Messagerie vocale cloud](set-up-phone-system-voicemail.md)  | Lorsqu’un utilisateur reçoit une messagerie vocale, elle est remise à sa boîte aux lettres Exchange sous forme d’e-mail avec le message vocal en tant que pièce jointe. Les utilisateurs peuvent écouter leurs messages sur leur téléphone de bureau certifié et sur toutes les applications Teams ou Skype Entreprise. La prise en charge de la transcription de la messagerie vocale a été ajoutée depuis mars 2017 et est activée par défaut pour toutes les organisations et tous les utilisateurs. <br> Notez que les utilisateurs *n’ont pas* besoin d’une licence de système téléphonique *et* qu’ils n’ont pas besoin d’activer la voix pour utiliser les fonctionnalités Messagerie vocale infonuagique.    |
|[Messagerie vocale infonuagique paramètres utilisateur](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permet aux utilisateurs de configurer leurs paramètres client pour les messages d’accueil de messagerie vocale, les règles de réponse aux appels et la langue d’accueil, y compris les messages d’accueil d’absence du bureau. <br> Notez que les utilisateurs *n’ont pas* besoin d’une licence de système téléphonique *et* qu’ils n’ont pas besoin d’activer la voix pour utiliser les fonctionnalités Messagerie vocale infonuagique.  |
|[Sonnerie secondaire](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Les utilisateurs disposant de plusieurs haut-parleurs connectés à leur PC peuvent choisir de définir un appareil secondaire à sonner en plus de leur haut-parleur par défaut. Par exemple, un utilisateur avec un casque connecté au PC et aux haut-parleurs de bureau peut choisir de faire sonner à la fois le casque et les haut-parleurs de bureau lorsqu’un appel arrive afin qu’il ne manque pas un appel.  |
|[Alertes en anneau distinctifs](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams uniquement) |Permet aux utilisateurs de choisir des sonneries distinctes pour les appels normaux, les appels transférés et les appels délégués afin de pouvoir distinguer le type d’appel.   |
|[Mode partage de lignes](shared-line-appearance.md)  | Permet aux utilisateurs de partager leur ligne téléphonique afin qu’un autre utilisateur puisse passer et recevoir des appels en leur nom.|
|[Occupé sur Occupé](teams-calling-policy.md) (Teams uniquement)  | Stratégie d’appel qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur : <ul><li>dans un appel </li><li>lors d’une conférence</li><li>a un appel mis en attente. </li></ul> L’appelant reçoit l’une des réponses suivantes : <ul><li>entendre un signal occupé lorsque l’appelé est sur le téléphone</li> <li>sera acheminé en conséquence vers les paramètres sans réponse de l’utilisateur. Une option permet à l’appelant de laisser une messagerie vocale pour l’utilisateur qui est déjà en appel.</li></ul> L’appelé reçoit une notification d’appel manqué, mais n’est pas en mesure de répondre aux appels entrants. Cette fonctionnalité est désactivée par défaut, mais peut être activée par l’administrateur du locataire.|
|[Blocage des appels](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permet aux utilisateurs d’ajouter des numéros de téléphone (RTC) à une liste bloquée afin que l’appel suivant de ce numéro ne puisse pas sonner l’utilisateur.|
|[Téléphones de zone commune](set-up-common-area-phones.md)  | Un téléphone de zone commune est généralement placé dans une zone comme une salle d’attente ou une salle de conférence, ce qui le rend disponible pour plusieurs personnes. Les téléphones de zone commune sont configurés en tant qu’appareils plutôt qu’en tant qu’utilisateurs et peuvent se connecter automatiquement à un réseau.|
|[Prise en charge de la déviation du trafic](direct-routing-plan-media-bypass.md) multimédia (pour le routage direct Teams uniquement)  | Pour de meilleures performances, le média est conservé entre le contrôleur de bordure de session (SBC) et le client au lieu de l’envoyer via le système téléphonique. |
|[Routage des numéros non attribués](routing-calls-to-unassigned-numbers.md) | Autorise le routage des numéros non attribués aux utilisateurs, aux standards automatiques, aux files d’attente d’appels ou à une annonce personnalisée. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilité dans les clouds GCC High et DoD
<a name="bkmk_setup"> </a>

Les fonctionnalités suivantes ne sont pas encore disponibles dans les clouds GCC High et DoD. 

- [Paramètres d’appel pour la sonnerie secondaire, la messagerie vocale et la délégation améliorée](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transférer vers la messagerie vocale à mi-appel](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Numéro de téléphone à partir de la barre de recherche
- Attente musicale
- Recherche de numéros inversés Azure AD

## <a name="related-topics"></a>Rubriques connexes

- [Qu’est-ce que le système téléphonique ?](what-is-phone-system-in-office-365.md)
- [Appel vocal dans le nuage dans Microsoft Teams](cloud-voice-landing-page.md)
- [Configurer le système téléphonique](setting-up-your-phone-system.md)
- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Tarification pour Système téléphonique](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams pour l’infrastructure de bureau virtualisée avec appels et réunions](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
