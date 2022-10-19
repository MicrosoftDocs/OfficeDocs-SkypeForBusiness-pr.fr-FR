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
description: 'Découvrez les fonctionnalités, la disponibilité et comment planifier et configurer Microsoft Phone System pour votre entreprise. '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584785"
---
# <a name="heres-what-you-get-with-phone-system"></a>Les avantages du système téléphonique

Cet article décrit les fonctionnalités du système téléphonique. Pour plus d’informations sur l’utilisation du système téléphonique comme remplacement de votre pbX (Private Branch Exchange) et les options de connexion au réseau téléphonique commuté (RTC), voir [Qu’est-ce que le système téléphonique](what-is-phone-system-in-office-365.md) ?

Les clients sont disponibles pour PC, Mac et mobile, qui fournit des fonctionnalités sur les appareils, des tablettes et des téléphones mobiles aux PC et aux téléphones IP de bureau. Pour plus d’informations, consultez [Obtenir des clients pour Microsoft Teams](get-clients.md).

 > [!Note]
> Pour plus d’informations sur les systèmes téléphoniques Teams sur différentes plateformes, consultez [fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

Pour utiliser les fonctionnalités du système téléphonique, votre organisation doit disposer d’une licence système téléphonique. Pour plus d’informations sur les licences, voir [Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

N’oubliez pas que la plupart des fonctionnalités vous obligent à attribuer la licence système téléphonique et à vérifier que les utilisateurs sont « activés par la voix ». Pour attribuer la licence, utilisez l’applet de commande [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) et définissez le paramètre **EnterpriseVoiceEnabled** sur $true. Certaines fonctionnalités, telles que le standard automatique cloud, ne nécessitent pas l’activation vocale d’un utilisateur. Les exceptions sont appelées dans le tableau ci-dessous.
  
## <a name="phone-system-features"></a>Fonctionnalités du système téléphonique

Le système téléphonique fournit les fonctionnalités suivantes.
  
|Fonctionnalité système téléphonique  |Description |
|:-----|:-----|
|[Standards automatiques cloud](what-are-phone-system-auto-attendants.md)  |Vous permet de créer un système de menus qui permet aux appelants externes et internes de localiser et de placer ou de transférer des appels aux utilisateurs de l’entreprise ou aux services de votre organisation.  <br/> Notez que les utilisateurs *n’ont pas* besoin d’être activés par la voix pour recevoir des appels à partir de la numérotation du standard automatique par nom, numérotation par numéro de recherche d’annuaire. *Les* utilisateurs doivent être activés par la voix pour recevoir des appels à partir des options de menu standard automatique. |
|[Files d’attente d’appels cloud](create-a-phone-system-call-queue.md) <br> |Vous permet de configurer la façon dont les files d’attente d’appels sont gérées pour votre organisation : par exemple, configurer les messages d’accueil et la musique en attente, rechercher l’agent d’appel disponible suivant pour gérer l’appel, et ainsi de suite.  <br/> Notez *que les* utilisateurs doivent être activés par la voix pour recevoir des appels à partir d’une file d’attente d’appels.|
|[Attente musicale](music-on-hold.md) | Lit la musique par défaut définie par le service ou la musique personnalisée chargée par l’administrateur client lorsqu’un appel externe du réseau téléphonique commuté (RTC) est mis en attente. Cette fonctionnalité fonctionne pour les appels PSTN-to-Teams un-à-un, en plus des appels effectués vers une file d’attente d’appels. Cette fonctionnalité fournit une parité de notification en attente avec d’autres plateformes. |
|Démarrage d'un appel/réponse à un appel (par nom et numéro)   |Permet aux utilisateurs de répondre aux appels entrants d’une touche tactile et de passer des appels sortants en composant le numéro de téléphone complet ou en cliquant sur un nom dans le client.   |
|[Options de transfert d’appel et sonnerie simultanée](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |Permet aux utilisateurs de configurer des règles de transfert afin que les appels puissent les utiliser n’importe où, ou que les appels puissent être transférés à des collègues ou à la messagerie vocale.   |
|[Prise d’appel de groupe et transfert vers le groupe](call-sharing-and-group-call-pickup.md)  | Permet aux utilisateurs de partager des appels entrants avec des collègues afin qu’ils puissent répondre aux appels qui se produisent alors que l’utilisateur n’est pas disponible. Moins perturbateur pour les destinataires que les autres formes de partage d’appels (comme le transfert d’appel ou la sonnerie simultanée), car les utilisateurs peuvent configurer la façon dont ils souhaitent être avertis d’un appel partagé entrant. |
|[Transférer un appel et un transfert consultatif](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |Permet aux utilisateurs de transférer des appels à une autre personne. Ou, s’ils ont besoin de quitter leur bureau mais veulent continuer la conversation, ils peuvent transférer les appels de leur PC ou téléphone IP vers leur téléphone cellulaire.  <br/> Notez que les utilisateurs *n’ont pas* besoin d’être activés par la voix pour recevoir des appels transférés d’un autre utilisateur. |
|[Transfert vers la messagerie vocale à mi-appel*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | Permet aux utilisateurs de transférer vers la messagerie vocale pendant un appel. |
|[Parcage d’appel et récupération](call-park-and-retrieve.md)   | Permet aux utilisateurs de mettre un appel en attente dans le service Teams dans le cloud. Lorsqu’un appel est garé, le service génère un code unique pour la récupération des appels. L’utilisateur qui a garé l’appel ou une autre personne peut ensuite utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel.  |
|Numéro de téléphone d’appel à partir de la recherche   | Permet aux utilisateurs de passer un appel à partir de la zone de recherche en utilisant la commande /call et en spécifiant un nom ou un nombre.  |
|[ID de l’appelant](how-can-caller-id-be-used-in-your-organization.md)   |Les appels de l’entreprise affichent un ID d’appelant détaillé qui extrait les informations de l’annuaire d’entreprise, affichant l’ID d’image et le titre du travail au lieu d’un simple numéro de téléphone. Pour les appels à partir de numéros de téléphone externes, l’ID d’appelant fourni par le fournisseur de services téléphoniques s’affiche. Si les numéros de téléphone externes sont des numéros secondaires dans l’annuaire d’entreprise, les informations de l’annuaire d’entreprise s’affichent.   |
|Changement de périphériques   |Permet aux utilisateurs de passer un appel ou une réunion sur un autre appareil HID connecté à Teams ; par exemple, passer de leurs haut-parleurs de PC à un casque.    |
|Routage des appels basés sur la présence  |Contrôle les communications entrantes avec présence, ce qui permet à l’utilisateur de bloquer toutes les communications entrantes à l’exception de celles indiquées spécifiquement.   |
|[Pavé de numérotation intégré](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | Permet aux utilisateurs de composer par nom ou par numéro n’importe où dans la barre de recherche et dans le pavé de numérotation, ce qui accélère le processus d’appels sortants.  |
|Appels fédérés   |Permet aux utilisateurs de se connecter, de communiquer et de collaborer en toute sécurité avec des utilisateurs dans des locataires fédérés.   |
|[Passer et recevoir un appel vidéo](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | Si le compte de l’utilisateur est activé pour les appels vidéo, l’utilisateur peut passer des appels vidéo en face à face avec ses contacts. Il leur suffit d’une caméra, des haut-parleurs et du microphone de leur ordinateur. Les utilisateurs peuvent également utiliser un casque si leur ordinateur n’a pas d’appareil audio intégré. |
|[Messagerie vocale cloud](set-up-phone-system-voicemail.md)  | Lorsqu’un utilisateur reçoit une messagerie vocale, elle est remise à sa boîte aux lettres Exchange sous la forme d’un e-mail avec le message vocal en pièce jointe. Les utilisateurs peuvent écouter leurs messages sur leur téléphone de bureau certifié et sur toutes les applications Teams ou Skype Entreprise. La prise en charge de la transcription de messagerie vocale a été ajoutée à partir de mars 2017 et est activée par défaut pour toutes les organisations et tous les utilisateurs. <br> Notez que les utilisateurs *n’ont pas* besoin d’une licence système téléphonique et qu’ils n’ont *pas* besoin d’être activés par la voix pour utiliser Messagerie vocale infonuagique fonctionnalités.    |
|[Messagerie vocale infonuagique paramètres utilisateur](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permet aux utilisateurs de configurer leurs paramètres client pour les messages d’accueil par messagerie vocale, les règles de réponse aux appels et le langage de message d’accueil, y compris les messages d’accueil hors bureau. <br> Notez que les utilisateurs *n’ont pas* besoin d’une licence système téléphonique et qu’ils n’ont *pas* besoin d’être activés par la voix pour utiliser Messagerie vocale infonuagique fonctionnalités.  |
|[Sonnerie secondaire](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | Les utilisateurs disposant de plusieurs périphériques de haut-parleur connectés à leur PC peuvent choisir de définir un appareil secondaire à sonner en plus de leur haut-parleur par défaut. Par exemple, un utilisateur disposant d’un casque connecté aux haut-parleurs du PC et du bureau peut choisir de faire sonner à la fois le casque et les haut-parleurs de bureau lorsqu’un appel arrive afin de ne pas manquer un appel.  |
|[Alertes d’anneau distinctifs](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) (Teams uniquement) |Permet aux utilisateurs de choisir des sonneries distinctes pour les appels normaux, les appels transférés et les appels délégués afin qu’ils puissent distinguer le type d’appel.   |
|[Mode partage de lignes](shared-line-appearance.md)  | Permet aux utilisateurs de partager leur ligne téléphonique afin qu’un autre utilisateur puisse passer et recevoir des appels en leur nom.|
|[Busy on Busy](teams-calling-policy.md) (Teams uniquement)  | Stratégie d’appel qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est : <ul><li>dans un appel </li><li>dans une conférence</li><li>a un appel mis en attente. </li></ul> L’appelant recevra l’une des réponses suivantes : <ul><li>entendre un signal occupé lorsque l’appelé est sur le téléphone</li> <li>sera routée en conséquence vers les paramètres sans réponse de l’utilisateur. Une option permet à l’appelant de laisser une messagerie vocale pour l’utilisateur qui est déjà en appel.</li></ul> L’appelé reçoit une notification d’appel manqué, mais ne peut pas répondre aux appels entrants. Cette fonctionnalité est désactivée par défaut, mais peut être activée par l’administrateur du locataire.|
|[Blocage des appels](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | Permet aux utilisateurs d’ajouter des numéros de téléphone (RTC) à une liste bloquée afin que l’appel suivant à partir de ce numéro ne puisse pas sonner l’utilisateur.|
|[Téléphones de zone commune](set-up-common-area-phones.md)  | Un téléphone commun est généralement placé dans une zone telle qu’une salle d’attente ou une salle de conférence le rendant disponible pour plusieurs personnes. Les téléphones de zone commune sont configurés en tant qu’appareils plutôt qu’utilisateurs et peuvent se connecter automatiquement à un réseau.|
|[Prise en charge de la déviation du trafic](direct-routing-plan-media-bypass.md) multimédia (pour le routage direct Teams uniquement)  | Pour de meilleures performances, le média est conservé entre le contrôleur de frontière de session (SBC) et le client au lieu de l’envoyer via le système téléphonique. |
|[Routage des nombres non attribués](routing-calls-to-unassigned-numbers.md) | Autorise le routage des numéros non attribués aux utilisateurs, aux standards automatiques, aux files d’attente d’appels ou à une annonce personnalisée. |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>Disponibilité dans les clouds GCC High et DoD
<a name="bkmk_setup"> </a>

Les fonctionnalités suivantes ne sont pas encore disponibles dans les clouds GCC High et DoD. 

- [Paramètres d’appel pour la sonnerie secondaire, la messagerie vocale et la délégation améliorée](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [Transfert vers la messagerie vocale à mi-appel](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- Numéro de téléphone d’appel à partir de la barre de recherche
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
- [Teams pour l’infrastructure de bureau virtualisée avec des appels et des réunions](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
