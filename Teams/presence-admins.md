---
title: Présence des utilisateurs dans Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informations destinées aux administrateurs sur la présence dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863195"
---
# <a name="user-presence-in-teams"></a>Présence des utilisateurs dans Teams

La présence fait partie du profil d’un utilisateur dans Microsoft Teams (et dans Office 365) et indique aux autres utilisateurs sa disponibilité et son statut actuels. Par défaut, tous les membres qui utilisent Teams dans votre organisation peuvent voir (en temps quasi-réel) si d’autres utilisateurs sont disponibles en ligne.

> [!IMPORTANT]
> Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution de contournement :pour afficher la présence dans Outlook (et d'autres applications Office), Skype Entreprise doit être installé, même si vous exécutez Teams en mode **Teams uniquement**. Microsoft est sensibilisé à ce problème et travaille activement au développement d’un correctif.

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures.

## <a name="presence-states-in-teams"></a>États de présence dans Teams

Les états de présence des utilisateurs disponibles dans Teams sont les suivants :

|L'utilisateur est configuré|L'application est configurée|
|:--- |:---|
| ![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) Disponible|![Une coche verte pleine indique une Présence : Disponible](media/Presence_Available.png) Disponible|
|| ![Une coche verte ouverte indique une Absence du bureau](media/Presence_Available_OOF.png) Disponible, Absent du bureau |
|  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé |  ![Un cercle rouge plein indique Occupé](media/Presence_Busy.png) Occupé  |
|| ![Un cercle rouge plein indique Occupé au téléphone](media/Presence_Busy.png) Au téléphone|
|| ![Un cercle rouge plein indique Occupé en réunion](media/Presence_Busy.png) En réunion |
|| ![Un cercle rouge ouvert indique Occupé](media/Presence_Busy_OOF.png) Au téléphone, absent du bureau|
|  ![Un cercle rouge avec une ligne blanche indique Ne pas déranger](media/Presence_DND.png) Ne pas déranger ||
|| ![Un cercle rouge avec une ligne blanche indique En cours de présentation](media/Presence_DND.png) En cours de présentation|
|| ![Un cercle rouge avec une ligne blanche indique un Travail individuel en cours](media/Presence_DND.png) Travail individuel en cours|
| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent|
|| ![Une icône d’horloge jaune indique l’absence](media/Presence_Away.png) Absent, *heure* de Vu pour la dernière fois|
|![Une icône d’horloge jaune indique l’absence, de retour dans quelques minutes](media/Presence_Away.png) De retour dans quelques minutes| |
|| ![Une icône d’horloge jaune indique l’absence, congé](media/Presence_Away.png)  Congé|
|| ![Un cercle gris avec un x indique un mode hors connexion](media/Presence_Offline.png) Hors connexion |
|| ![Un cercle gris ouvert indique un statut inconnu](media/Presence_Unknown.png) Statut inconnu|
||![Un cercle rouge ouvert avec une ligne diagonale indique bloqué](media/Presence_Blocked.png) Bloqué |
|| ![Un cercle violet avec une flèche indique absent du bureau](media/Presence_OOF.png) Absent du bureau|
|||
 
Les utilisateurs peuvent manuellement définir leur état de présence actuel pour certaines options et il se reflète vers tous les autres utilisateurs. D’autres détails sur la présence de l’utilisateur sont également mis à jour automatiquement. Les modifications sont basées sur l’activité des utilisateurs (Disponible, Absent), les états du calendrier Outlook (En réunion) ou l’état de l’application Teams (Au téléphone, En cours de présentation) et aux états mis en retrait dans la liste. Il y a un délai d’inactivité de 15 minutes, après lequel l’état de présence actuel est rétabli sur Absent.

Les utilisateurs reçoivent tous les messages de conversation qui leur sont envoyés dans Teams, quel que soit leur état de présence. Si un utilisateur est hors connexion lorsqu’une personne envoie un message, celui-ci apparaît dans Teams lorsque l'utilisateur est de nouveau en ligne. Si un utilisateur est dans un état Ne pas déranger, il reçoit les messages de conversation, mais une bannière de notification ne s’affiche pas.

Les utilisateurs reçoivent des appels quel que soit l'état de présence, à l’exception des états Ne pas déranger dans lesquels les appels entrants sont transmis à leur messagerie vocale. Si le destinataire a bloqué l’appelant, l'appel n’est pas remis et l’appelant voit la présence du destinataire en Mode hors connexion.

Les utilisateurs peuvent ajouter des utilisateurs à leur liste d’accès prioritaire en accédant à **Paramètres** > **Confidentialité** dans Teams. Les contacts disposant d’un accès prioritaire peuvent contacter l’utilisateur, même lorsque celui-ci est dans un état Ne pas déranger.

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a>Paramètres d’administrateur dans Teams comparé à ceux de Skype Entreprise

Les paramètres d’administration suivants de Skype Entreprise sont différents de ceux dans Teams :

- Le partage de présence est toujours activé dans Teams pour les utilisateurs de l’organisation. La configuration de la confidentialité (dans laquelle vous définissez les personnes pouvant voir la présence) n’est pas disponible dans Teams.
- Le partage de présence avec tout le monde (y compris les services fédérés) est toujours activé pour les utilisateurs de Teams. Leur liste de contacts (s'ils en avaient une dans Skype Entreprise) est visible sous **Conversation > Contacts** ou sous **Appels > Contacts**.
- Les fonctionnalités du client Ne sont pas déranger et Autorisé à appeler sont toujours activées pour les utilisateurs Teams.
- L'intégration du calendrier (comprend les informations d’absence du bureau et d’autres informations de calendrier) est toujours activée pour les utilisateurs lorsque Teams est intégrée à Outlook.
- L'indicateur *Vu pour la dernière fois* ou *Absent depuis* est toujours activé pour les utilisateurs Teams si l’organisation utilise également Skype Entreprise.

> [!NOTE]
> La possibilité pour un administrateur Teams de personnaliser ces paramètres n’est pas prise en charge pour le moment.

## <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Pour plus d’informations sur les fonctions de présence Teams lorsque votre organisation utilise également Skype Entreprise, voir [Coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md).
