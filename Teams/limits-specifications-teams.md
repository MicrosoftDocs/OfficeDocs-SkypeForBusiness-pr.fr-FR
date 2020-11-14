---
title: Limites et spécifications de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cet article présente les limites, spécifications et autres exigences qui s’appliquent à Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a552fd88d469c7daaae324614c398c24ac2f9d41
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031360"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites et spécifications de Microsoft Teams

Cet article présente certaines limites, spécifications et autres configurations requises qui s’appliquent à Teams.

## <a name="teams-and-channels"></a>Équipes et canaux

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’équipes qu’un utilisateur peut créer | Soumis à une limite objet de 250 et sup1 ;         |
|Nombre d’équipes dont un utilisateur peut-être membre|1 000&sup2 ;|
|Nombre de membres dans une équipe. | 10 000<sup>5</sup>     |
|Nombre de propriétaires par équipe | 100   |
|Nombre d’équipes à l’échelle de l’organisation autorisées dans un client | 5     |
|Nombre de membres dans une[équipe à l’échelle de l’organisation](create-an-org-wide-team.md) | 5 000       |
|Nombre d’équipes qu’un administrateur général peut créer        |  500 000   |
|Nombre d’équipes qu’une organisation Microsoft 365 ou Office 365 peut avoir    | 500,000&sup2;     |
|Nombre de canaux par équipe    | 200 (y compris les canaux supprimés)&sup3;         |
|Nombre de canaux privés par équipe    |30| 200 (y compris les canaux supprimés)&sup3;
|Nombre de membres dans un canal privé    |250|
|Nombre maximal de membres d’un groupe Office 365 pouvant être convertis en équipe    |10 000<sup>5</sup>     |
|Taille de billet de conversation de canal | Environ 28 Ko par billet<sup>4</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).

<sup>2</sup> Cette limite inclut les équipes archivées.

<sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>4</sup> 28 Ko est une limite approximative, car elle inclut le message lui-même (texte, liens d’image, etc.), les @-mentions, le nombre de connecteurs et les réactions.

<sup>5</sup> Les équipes du cloud de la communauté du secteur public ne peuvent accueillir que 5 000 membres et celles de GCCH/DoD ne peuvent en accueillir que 2 500.
## <a name="messaging"></a>Messagerie

### <a name="chat"></a>Conversation

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)

Les conversations de Teams fonctionnent sur un serveur principal Microsoft Exchange, donc les limites de messagerie Exchange s’appliquent à la fonction de conversation dans Teams.

|Fonctionnalité  | Limite maximale  |
|---------|---------|
|Nombre de personnes dans une conversation privée<sup>1</sup>  | 250 |
|Nombre de personnes dans un appel vidéo ou audio de la conversation | 20 |
|Nombre de pièces jointes<sup>2</sup>  |10     |
|Taille de la conversation | Environ 28 Ko par billet<sup>3</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Si le nombre de pièces jointes dépasse cette limite, un message d’erreur s’affiche.

<sup>3</sup> 28 Ko est une limite approximative, car elle inclut le message lui-même (texte, liens d’image, etc.), les @-mentions et les réactions.

### <a name="emailing-a-channel"></a>Envoi d’un message électronique à un canal

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

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
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.



## <a name="channel-names"></a>Noms des canaux

Les noms des canaux ne peuvent pas contenir les caractères ou les mots suivants.

|Tapez|Exemple|
|---------|---------|
|Caractères     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|Caractères dans ces plages    | 0 à 1F<br>80 à 9F        |
|Mots     | formulaires, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 à COM9, LPT1 à LPT9, desktop.ini,  &#95;vti&#95;|

Les noms des canaux ne peuvent pas non plus commencer par un trait de soulignement (_) ou un point (.) ou se terminer par un point (.).

## <a name="meetings-and-calls"></a>Réunions et appels

> [!IMPORTANT]
> **Augmentation de la limite d’événements en direct Microsoft 365**
>
> **Pour aider nos clients, jusqu’au 1er janvier 2021, nous allons étendre les augmentations de limite temporaires pour les événements en direct hébergés dans Teams, Stream et Yammer, y compris**  :
>
>- Jusqu’à 20 000 participants par événement
>- Jusqu’à 50 événements simultanés par client Teams
>- Jusqu’à 16 heures par diffusion
>
> En outre, des événements en direct réunissant jusqu'à 100 000 participants peuvent être planifiés grâce au programme d'assistance de Microsoft 365. L’équipe évalue chaque demande et travaille avec vous pour déterminer les options disponibles. [En savoir plus](https://aka.ms/Stream/Blog/LiveEventOptions). **Après le 1er janvier 2021, les clients qui ont besoin de ces augmentations de limite sont invités à acheter le [module complémentaire des communications avancées](teams-add-on-licensing/advanced-communications.md).**


|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de participants à une réunion (possibilité de conversation et appel entrant)  | 300 |
|Nombre de personnes dans un appel vidéo ou audio de la conversation | 20 |
|Taille maximale des fichiers PowerPoint | 2 Go|
|Teams garde les [enregistrements de réunions](cloud-recording.md) non chargés dans Microsoft Stream, disponibles en téléchargement local | 20 jours |

>[!Note]
> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive. Au démarrage, vous serez en mesure d’opter pour cette expérience, en novembre vous devrez annuler votre abonnement si vous souhaitez continuer à utiliser Stream, et début 2021, tous les clients devront utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.

### <a name="meeting-expiration"></a>Expiration de réunion

|Type de réunion  |La réunion expire après un certain délai  |Chaque fois qu’une réunion démarre ou est mise à jour, l’expiration se prolonge d’un certain délai  |
|---------|---------|---------|
|Conférence maintenant     |Heure de début + 8 heures         |N/A         |
|Normale sans heure de fin     |Heure de début + 60 jours         | 60 jours        |
|Normale avec heure de fin     |Heure de fin + 60 jours         |60 jours         |
|Périodique sans heure de fin     |Heure de début + 60 jours         |60 jours         |
|Périodique avec heure de fin     |Heure de fin de la dernière occurrence + 60 jours         |60 jours         |

> [!NOTE]
> Les réunions Microsoft Teams ont une durée limite de 24 heures.

## <a name="teams-live-events"></a>Événements en direct Teams

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Taille de l’audience | 10 000 participants |
|Durée de l’événement | 4 heures |
|Événements en direct simultanés exécutés dans une organisation Microsoft 365 ou Office 365 <sup>1</sup> | 15 |

<sup>1</sup> vous pouvez planifier autant d’événements en direct que vous le souhaitez, mais vous ne pouvez exécuter que 15 à la fois. Dès que le producteur rejoint un événement en direct, celui-ci est considéré comme étant en cours d’exécution. Le producteur qui tente de participer au seizième événement en direct reçoit une erreur.

Pour plus d’informations sur les événements en direct et pour voir une comparaison entre les événements en direct Teams et la diffusion de réunion Skype, accédez à [événements en direct Teams et diffusion de réunion Skype](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Consultez également [Planifier un événement en direct Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Augmentation de la limite d’événements en direct Microsoft 365**
>
> **Pour aider nos clients, jusqu’au 1er janvier 2021, nous allons étendre les augmentations de limite temporaires pour les événements en direct hébergés dans Teams, Stream et Yammer, y compris**  :
>
> - Jusqu’à 20 000 participants par événement
> - Jusqu’à 50 événements simultanés par client Teams
> - Jusqu’à 16 heures par diffusion
>
> En outre, des événements en direct réunissant jusqu'à 100 000 participants peuvent être planifiés grâce au programme d'assistance de Microsoft 365. L’équipe évalue chaque demande et travaille avec vous pour déterminer les options disponibles. [En savoir plus](https://aka.ms/Stream/Blog/LiveEventOptions). **Après le 1er janvier 2021, les clients qui ont besoin de ces augmentations de limite sont invités à acheter le [module complémentaire des communications avancées](teams-add-on-licensing/advanced-communications.md).**

## <a name="presence-in-outlook"></a>Présence dans Outlook

La présence de Teams dans Outlook est prise en charge dans l’application de bureau Outlook 2013 et les versions ultérieures. Pour en savoir plus sur la présence dans Teams, voir [Présence de l’utilisateur dans Teams](presence-admins.md).

## <a name="storage"></a>Stockage

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

> [!NOTE]
> Chaque [canal privé](https://docs.microsoft.com/microsoftteams/private-channels) possède sa propre collection de sites SharePoint.

Si SharePoint Online n’est pas activé dans votre client, les utilisateurs Microsoft Teams ne peuvent pas toujours partager des fichiers dans les équipes. De plus, les utilisateurs dans une conversation privée ne peuvent pas partager des fichiers car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis pour ces fonctionnalités.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. (Pour plus d’informations, voir[Comment SharePoint Online et OneDrive Entreprise interagissent avec Microsoft Teams](sharepoint-onedrive-interact.md).)

Étant donné que Teams s’exécute sur un serveur principal SharePoint Online pour le partage de fichiers, les limitations SharePoint s’appliquent à la section Fichiers dans une équipe. Voici les limites de stockage applicables pour SharePoint Online.

|Fonctionnalité                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée   |1 To par organisation, plus 10 Go par licence achetée |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation           |
|Espace de stockage pour fichiers Teams |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |
|Limite de chargement de fichiers (par fichier)    |100 Go    |100 Go    |100 Go    |100 Go    |100 Go    |100 Go    |

Les canaux sont protégés par des dossiers au sein de la collection de sites SharePoint Online créée pour l’équipe, de sorte que les onglets des fichiers au sein des canaux partagent les limites de stockage de l’équipe à laquelle ils appartiennent.

Pour plus d’informations, voir [Limites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Équipes de classe :

Microsoft Teams pour l’éducation fournit des modèles conçus pour des scénarios d’éducation uniques, tels que l’apprentissage en classe. Pour plus d’informations sur les types d’équipe, y compris les équipes de classe, est disponible dans [Choisir un type d’équipe à des fins de collaboration dans Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Une équipe de classe est un type de modèle avec des applications supplémentaires incluses, et des limites distinctes au nombre de membres de l’équipe.

> [!NOTE]
> L’utilisation d’équipes de classe nécessite une licence [Microsoft Office 365 pour l’éducation](https://www.microsoft.com/education/products/office).

Les limites pour les équipes de classe sont répertoriées dans le tableau suivant :

|Fonctionnalité  |Limite maximale  |
|---------|---------|
|Nombre de membres dans une équipe.    | Consultez la section [Équipes et canaux](#teams-and-channels) de cet article.        |
|Nombre de membres pour utiliser Affectations dans une équipe de classe    | 200        |
|Nombre de membres pour utiliser un bloc-notes OneNote pour la classe dans une équipe de classe     |200         |

Une équipe de classe peut prendre en charge plus de 200 membres. Toutefois, si vous envisagez d’utiliser l’application Affectations ou bloc-notes pour la classe au sein de votre équipe, vous devrez conserver le nombre de membres inférieur aux limites maximales ci-dessus.


## <a name="tags"></a>Balises

|Fonctionnalité  |Limite maximale  |
|---------|---------|
|Nombre de balises par équipe    | 100        |
|Nombre de balises par défaut suggérées par équipe    | 25        |
|Nombre de membres de l’équipe attribués à un indicateur    |100         |
|Nombre de mots clés attribués à un utilisateur    |25         |

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
