---
title: Limites et spécifications de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: En savoir plus sur les limites, spécifications et autres configurations requises pour Microsoft Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa6fad448f0251a44d31c5277b43390daeb3441c
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823909"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites et spécifications de Microsoft Teams

Cet article présente certaines limites, spécifications et autres configurations requises qui s’appliquent à Teams.

## <a name="teams-and-channels"></a>Équipes et canaux

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’équipes qu’un utilisateur peut créer | Soumis à une limite objet de 250 et sup1 ;         |
|Nombre d’équipes dont un utilisateur peut-être membre|1 000|
|Nombre de membres dans une équipe. | 5,000       |
|Nombre d’équipes à l’échelle de l’organisation autorisées dans un client | 5     |
|Nombre de membres dans une[équipe à l’échelle de l’organisation](create-an-org-wide-team.md) | 5 000       |
|Nombre d’équipes qu’un administrateur général peut créer        |  500 000   |
|Nombre d’équipes que peut avoir un client Office 365    | 500,000&sup2;     |
|Nombre de canaux par équipe    | 200 (y compris les canaux supprimés)&sup3;         |
|Nombre de canaux privés par équipe    |30|

& sup1 ; N’importe quel objet dans Azure Active Directory compte dans cette limite. Les administrateurs généraux sont exempts de cette limite, comme les applications appelant Microsoft Graph en utilisant des[autorisations d’application](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Cette limite inclut les équipes archivées.

&sup3; Les canaux supprimés peuvent être restaurés dans un délai de 30 jours. Pendant ces 30 jours, un canal supprimé continue d’être pris en compte dans la limite des 200 canaux par équipe. Après 30 jours, un canal supprimé et son contenu sont supprimés de façon définitive et le canal n’est plus pris en compte dans la limite des 200 canaux par équipe.

## <a name="messaging"></a>Messagerie

### <a name="chat"></a>Conversation

Les utilisateurs qui participent aux conversations qui font partie de la liste de conversation dans Teams doivent avoir une boîte aux lettres Exchange Online (sur le cloud) pour qu’un administrateur recherche des conversations instantanées. C’est parce que les conversations qui font partie de la liste de conversations sont stockées dans les boîtes aux lettres des participants basées sur le cloud. Si un participant de conversation ne dispose pas de boîte aux lettres Exchange Online, l’administrateur ne pourra pas effectuer de recherche ou suspendre de conversations instantanées. Par exemple, dans un déploiement Exchange hybride, les utilisateurs disposant de boîtes aux lettres locales peuvent peut-être participer aux conversations qui font partie de la liste de conversations dans Teams. Toutefois, dans ce cas, le contenu de ces conversations n’est pas consultable et ne peut pas être mis en attente, car les utilisateurs n’ont pas de boîtes aux lettres sur le cloud. (Pour plus d’informations, voir [comment Exchange et Microsoft Teams interagissent](exchange-teams-interact.md).)

Les conversations de Teams fonctionnent sur un serveur principal Microsoft Exchange, donc les limites de messagerie Exchange s’appliquent à la fonction de conversation dans Teams.

|Fonctionnalité  | Limite maximale  |
|---------|---------|
|Nombre de personnes dans une conversation privée<sup>1</sup>  | 100    |
|Nombre de pièces jointes<sup>2</sup>  |10     |

<sup>1</sup> Si plus de 1 personnes sont présentes dans une conversation, les fonctionnalités de conversation suivantes sont désactivées : réponses automatiques d’Outlook et messages d’état de Teams, indicateur de saisie, appels vidéo et audio, partage, confirmations de lecture.

<sup>2</sup> Si le nombre de pièces jointes dépasse cette limite, un message d’erreur s’affiche.

### <a name="emailing-a-channel"></a>Envoi d’un message électronique à un canal

 Si un utilisateur souhaite envoyer un message électronique à un canal dans Teams, ils utilisent l’adresse de messagerie du canal. Lorsqu’un message électronique fait partie d’un canal, tout le monde peut y répondre et démarrer une conversation. Voici quelques-unes des limites applicables pour l’envoi de courrier à un canal.

|Fonctionnalité  | Limite maximale  |
|---------|---------|
|Taille du message<sup>1<sup> | 24 Ko |
|Nombre de pièces jointes<sup>2</sup>  |20     |
|Taille de chaque pièce jointe | Inférieur à 10 Mo |
|Nombre d’images incorporées<sup>2</sup> |50   |

<sup>1</sup> Si le message excède cette limite, un aperçu du message est généré et l’utilisateur est invité à télécharger et à afficher le message d’origine à partir du lien fourni.

<sup>2</sup> Si le nombre de pièces jointes ou d’images dépasse cette limite, un message d’erreur s’affiche.

Pour plus d’informations, voir [Limites d’Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Les limites de taille des messages, de pièces jointes et d’images incorporées sont identiques pour toutes les licences Office 365.

## <a name="channel-names"></a>Noms des canaux

Les noms des canaux ne peuvent pas contenir les caractères ou les mots suivants.

|||
|---------|---------|
|Caractères     | ~ # % & * { } + / \ : < > ? &#124; ' " ..        |
|Caractères dans ces plages    | 0 à 1F<br>80 à 9F        |
|Mots     | formulaires, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 à COM9, LPT1 à LPT9, desktop.ini,  &#95;vti&#95;|

Les noms des canaux ne peuvent pas non plus commencer par un trait de soulignement (_) ou un point (.) ou se terminer par un point (.).

## <a name="meetings-and-calls"></a>Réunions et appels

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de personnes dans une réunion  | 250    |
|Taille maximale des fichiers PowerPoint | 2 Go|

### <a name="meeting-expiration"></a>Expiration de réunion

|Type de réunion  |La réunion expire après un certain délai  |Chaque fois qu’une réunion démarre ou est mise à jour, l’expiration se prolonge d’un certain délai  |
|---------|---------|---------|
|Conférence maintenant     |Heure de début + 8 heures         |N/A         |
|Normale sans heure de fin     |Heure de début + 60 jours         | 60 jours        |
|Normale avec heure de fin     |Heure de fin + 60 jours         |60 jours         |
|Périodique sans heure de fin     |Heure de début + 60 jours         |60 jours         |
|Périodique avec heure de fin     |Heure de fin de la dernière occurrence + 60 jours         |60 jours         |



## <a name="teams-live-events"></a>Événements en direct Teams

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Taille de l’audience | 10 000 participants |
|Durée de l’événement | 4 heures |
|Événements en direct simultanés dans un client Office 365 | 15 |

Pour plus d’informations sur les événements en direct et pour voir une comparaison entre les événements en direct Teams et la diffusion de réunion Skype, accédez à [événements en direct Teams et diffusion de réunion Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="presence-in-outlook"></a>Présence dans Outlook

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures. Pour en savoir plus sur la présence dans Teams, voir [Présence de l’utilisateur dans Teams](presence-admins.md).

## <a name="storage"></a>Stockage

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Si SharePoint Online n’est pas activé dans votre client, les utilisateurs Microsoft Teams ne peuvent pas toujours partager des fichiers dans les équipes. De plus, les utilisateurs dans une conversation privée ne peuvent pas partager des fichiers car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis pour ces fonctionnalités.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. (Pour plus d’informations, voir[Comment SharePoint Online et OneDrive Entreprise interagissent avec Microsoft Teams](sharepoint-onedrive-interact.md).)

Étant donné que Teams s’exécute sur un serveur principal SharePoint Online pour le partage de fichiers, les limitations SharePoint s’appliquent à la section Fichiers dans une équipe. Voici les limites de stockage applicables pour SharePoint Online.

|Fonctionnalité                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée   |1 To par organisation, plus 10 Go par licence achetée |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation           |
|Espace de stockage pour fichiers Teams |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |
|Limite de chargement de fichiers (par fichier)    |15 Go    |15 Go    |15 Go    |15 Go    |15 Go    |15 Go    |

Les canaux sont protégés par des dossiers au sein de la collection de sites SharePoint Online créée pour l’équipe, de sorte que les onglets des fichiers au sein des canaux partagent les limites de stockage de l’équipe à laquelle ils appartiennent.

Pour plus d’informations, voir [Limites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="contacts"></a>Contacts

Teams utilise ces contacts :

- Contacts dans l’annuaire Active Directory de votre organisation
- Contacts ajoutés au dossier Outlook par défaut de l’utilisateur

Les utilisateurs de Teams peuvent communiquer avec n’importe quel membre de l’annuaire Active Directory de votre organisation et peuvent ajouter n’importe quel membre de l’annuaire Active Directory de votre organisation à leur liste de contacts en accédant à **Conversation** > **Contacts** ou **Appels** > **Contacts**.

Les utilisateurs de Teams peuvent également ajouter une personne qui n’est pas dans l’annuaire Active Directory de votre organisation à leur liste de contacts en accédant à **Appels** > **Contacts**.

## <a name="browsers"></a>Navigateurs

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Systèmes d’exploitation

Pour plus d'informations sur les exigences logicielles pour chaque plateforme, voir [Obtenir des clients pour Microsoft Teams](get-clients.md).
