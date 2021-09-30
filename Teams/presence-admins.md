---
title: Présence des utilisateurs dans Teams
author: dmaguire
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Découvrez les États de présence dans Teams et les paramètres administratifs de la fonctionnalité Présence.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a928b532dcfb87a866f25502f4523078ce9cd48
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012958"
---
# <a name="user-presence-in-teams"></a>Présence des utilisateurs dans Teams

La présence fait partie du profil d’un utilisateur dans Microsoft Teams (et dans Microsoft 365 ou Office 365). La présence indique aux autres utilisateurs la disponibilité et l’état actuel d’un utilisateur. Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne. La présence est mise à jour en temps réel sur le web et les versions de bureau lorsque vous actualisez la page sur mobile.

 > [!NOTE]
 > Pour plus d’informations sur les profils utilisateur Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

 > [!NOTE]
 > Teams respecte votre configuration de confidentialité. Par conséquent, si vous avez activé le mode de confidentialité, votre présence ne sera pas visible pour les utilisateurs externes.

## <a name="presence-states-in-teams"></a>États de présence dans Teams


|L'utilisateur est configuré|L'application est configurée|
|:--- |:---|
| ![Une coche verte pleine indique une Présence disponible](media/Presence_Available.png) Disponible|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) Disponible|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) Disponible, Absent(e) du bureau. Remarque : Absent(e) du bureau est automatiquement configurée pour les périodes pendant lesquelles l’utilisateur définit « Réponses automatiques » Si l’utilisateur utilise l’application pendant ces périodes, une double présence peut s’afficher, telle que « Absent(e) du bureau, disponible ». |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé  |
|| ![Un cercle rouge plein indique Occupé au téléphone.](media/Presence_Busy.png) Pendant un appel|
|| ![Un cercle rouge plein indique Occupé en réunion.](media/Presence_Busy.png) En réunion |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) Au téléphone, absent du bureau|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger.](media/Presence_DND.png) Ne pas déranger ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation.](media/Presence_DND.png) Présentation|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) Ne pas déranger (travail individuel). Le travail individuel se produit lorsque les utilisateurs planifient un temps de travail individuel dans MyAnalytics/Insights de leur calendrier.|
| ![Une icône d’horloge jaune indique l’absence.](media/Presence_Away.png) Absent(e)| ![Une icône d’horloge jaune indique l’absence.](media/Presence_Away.png) Absent|
|| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) De retour dans quelques minutes| |
|![Un cercle gris avec un x indique un mode Hors connexion.](media/Presence_Offline.png) Apparaître Hors connexion|![Un cercle gris avec un x indique un mode Hors connexion](media/Presence_Offline.png) Hors ligne. Lorsque les utilisateurs ne sont pas connectés sur l’un de leurs appareils, ils apparaissent hors ligne. |
|| ![Un cercle gris ouvert indique un statut inconnu.](media/Presence_Unknown.png) Statut inconnu|
|| ![Un cercle violet avec une flèche indique Absent(e) du bureau.](media/Presence_OOF.png) Absent(e) du bureau. Absent(e) du bureau est utilisé lorsque vous définissez une réponse automatique. |

 > [!NOTE]
 > Pour les utilisateurs dont la boîte aux lettres est hébergée localement, des retards de présence d’une heure (maximum) sont attendus.

Les états de présence configurés par l’application sont basés sur l’activité des utilisateurs (Disponible, Absent), les états du calendrier Outlook (En réunion) ou l’état de l’application Teams (Au téléphone, En cours de présentation). Lorsque vous êtes en mode travail individuel en fonction de votre calendrier, **Travail individuel en cours** est l’état visible par des contacts dans Teams. Le mode travail individuel s’affiche en tant que **Ne pas déranger** dans d’autres produits.

Votre état de présence actuel passe à Absent lorsque vous verrouillez votre ordinateur ou lorsque votre ordinateur entre en mode d’inactivité ou de veille. Sur un appareil mobile, le statut de présence passe à Absent lorsque l’application Teams est en arrière-plan.

Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence. Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne. Si un état d’utilisateur est défini sur Ne pas déranger, il continue de recevoir les messages de conversation, mais les notifications de bannière ne s’affichent pas.

Les utilisateurs reçoivent des appels quel que soit l'état de présence, à l’exception de l’état Ne pas déranger dans lequel les appels entrants sont redirigés vers la messagerie vocale. Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.

Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams. Les contacts disposant d’un accès prioritaire peuvent contacter l’utilisateur, même lorsque le statut de l’utilisateur est défini sur Ne pas déranger.

### <a name="dual-presence"></a>Double présence

  La façon dont la présence fonctionne pour la plupart des utilisateurs se fonde sur les événements présents dans le calendrier ou les événements de l’appareil tels qu’un appel. L’utilisateur peut remplacer cet état dans l’interface utilisateur en configurant manuellement les états, lesquels ont une date/heure d’expiration.

## <a name="user-configured-states-expiration"></a>Expiration des états configurés d’un utilisateur

Lorsqu’un utilisateur sélectionne un état de présence, celui-ci aura précédence sur la mise à jour de toute d’activité dans une application. Par exemple, si une utilisatrice se définit avec un statut Ne pas déranger, son état restera sur Ne pas déranger, même lorsqu’elle est en réunion ou qu’elle répond à un appel.

Les états configurés d’un utilisateur ont des paramètres d’expiration par défaut dans Teams pour empêcher les utilisateurs d’afficher un état qui peut ne pas être pertinent après un certain temps.

|État configuré d’un utilisateur|Expiration par défaut|
|:--- |:---|
| Occupé|1 jour|
| Ne pas déranger|1 jour|
| Autres|7 jours|

> [!NOTE]
> Un utilisateur peut également configurer manuellement la durée de sa présence. Par exemple, une utilisatrice peut se définir sur Apparaître hors ligne jusqu’au lendemain matin.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise

Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :

- Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation. La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.
- Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams. Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.
- Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.
- L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.
- L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.

> [!NOTE]
> La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a>Paramètres d’administrateur dans Teams comparé à ceux de Microsoft Outlook

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures pour les contacts dans la même organisation.

Si la stratégie du mode de mise à niveau du compte de l’utilisateur est définie sur TeamsOnly, Outlook indique à Teams d’obtenir les informations de présence. Si le compte de l’utilisateur n’est pas défini sur TeamsOnly, Outlook dialogue alors avec Skype Entreprise.

## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).
