---
title: Limites et spécifications de Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: Cet article présente les limites, spécifications et autres exigences qui s’appliquent à Microsoft Teams.
ms.localizationpriority: high
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
ms.openlocfilehash: 16ca31652f3b5b9daa0216e683d80e6d9b0c809d
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886631"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites et spécifications de Microsoft Teams

Cet article présente certaines limites, spécifications et autres configurations requises qui s’appliquent à Teams.

## <a name="teams-and-channels"></a>Équipes et canaux

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’équipes qu’un utilisateur peut créer | Soumis à une limite objet de 250 et sup1 ;         |
|Nombre d’équipes dont un utilisateur peut-être membre|1 000&sup2 ;|
|Nombre de membres dans une équipe. | 25 000<sup>6</sup>     |
|Nombre de propriétaires par équipe | 100   |
|Nombre d’équipes à l’échelle de l’organisation autorisées dans un client | 5&sup2;     |
|Nombre de membres dans une[équipe à l’échelle de l’organisation](create-an-org-wide-team.md) | 10 000       |
|Nombre d’équipes qu’un administrateur général peut créer        |  500 000   |
|Nombre d’équipes qu’une organisation Microsoft 365 ou Office 365 peut avoir    | 500 000 &sup3 ;     |
|Nombre de canaux par équipe    | 200 (y compris les canaux supprimés)<sup>4</sup>        |
|Nombre de canaux privés par équipe    |30 (y compris les canaux supprimés)<sup>4</sup>        |
|Nombre de membres dans un canal privé    |250|
|Taille maximale de liste de distribution, groupe de sécurité ou groupe Office 365 pouvant être importé dans une équipe    |3 500|
|Nombre maximal de membres d’un groupe Office 365 pouvant être convertis en équipe    |10 000<sup>6</sup>     |
|Taille de billet de conversation de canal | Environ 28 Ko par billet<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> Cette limite inclut les équipes archivées. 

<sup>3</sup> Pour augmenter davantage le nombre d’équipes, vous devez contacter le support Microsoft et demander à augmenter le nombre d’objets Azure Active Directory de votre client. Une augmentation est réalisée uniquement pour les scénarios de production réels.

<sup>4</sup> Les canaux supprimés peuvent être restaurés sous 30 jours. Pendant ces 30 jours, un canal supprimé continue à être compté vers les 200 canaux ou 30 canaux privés selon la limite par équipe. Après 30 jours, un canal supprimé et son contenu sont définitivement supprimés et le canal ne compte plus dans la limite par équipe.

<sup>5</sup> 28 Ko est une limite approximative, car elle inclut le message lui-même (texte, liens d’image, etc.), les @-mentions, le nombre de connecteurs et les réactions.

<sup>6</sup> membres de canaux partagés extérieurs à l’équipe sont comptabilisés dans cette limite. Notez également que les mentions d’équipes/canaux sont bloquées dans les équipes de plus de 10 000 membres.

> [!NOTE]
> Pour l'aperçu des limites des canaux partagés, voir [Limites des canaux partagés (aperçu)](/MicrosoftTeams/shared-channels#limits-for-shared-channels-preview).

## <a name="messaging"></a>Messagerie

### <a name="chat"></a>Conversation

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|Fonctionnalité  | Limite maximale  |
|---------|---------|
|Nombre de personnes dans une conversation privée<sup>1</sup>  | 250<sup>2</sup> |
|Nombre de personnes dans un appel vidéo ou audio de la conversation | 20 |
|Nombre de pièces jointes<sup>3</sup>  |10     |
|Taille de la conversation | Environ 28 Ko par billet<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Uniquement 200 membres à la fois peuvent être ajoutés à une conversation de groupe. [Pour plus d’informations, consultez cet article](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> Si le nombre de pièces jointes dépasse cette limite, un message d’erreur s’affiche.

<sup>4</sup> 28 Ko est une limite approximative, car elle inclut le message lui-même (texte, liens d’image, etc.), les @-mentions, le nombre de connecteurs et les réactions.

### <a name="emailing-a-channel"></a>Envoi d’un message électronique à un canal

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|Fonctionnalité  | Limite maximale  |
|---------|---------|
|Taille du message<sup>1<sup> | 24 Ko |
|Nombre de pièces jointes<sup>2</sup>  |20     |
|Taille de chaque pièce jointe | Inférieur à 10 Mo |
|Nombre d’images incorporées<sup>2</sup> |50   |

> [!NOTE]
> Le nombre d'e-mails que vous pouvez envoyer à un canal est limité. La limite est de six e-mails par dix secondes par canal et par utilisateur et de huit e-mails par dix secondes par client et par utilisateur.
<sup>1</sup> Si le message excède cette limite, un aperçu du message est généré et l’utilisateur est invité à télécharger et à afficher le message d’origine à partir du lien fourni.

<sup>2</sup> Si le nombre de pièces jointes ou d’images dépasse cette limite, un message d’erreur s’affiche.

Pour plus d’informations, voir [Limites d’Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>Noms des canaux

Les noms des canaux ne peuvent pas contenir les caractères ou les mots suivants :

|Type|Exemple|
|---------|---------|
|Caractères     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|Caractères dans ces plages    | 0 à 1F<br>80 à 9F        |
|Mots     | formulaires, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 à COM9, LPT1 à LPT9, desktop.ini,  &#95;vti&#95;|

Les noms des canaux ne peuvent pas non plus commencer par un trait de soulignement (_) ou un point (.) ou se terminer par un point (.).

## <a name="meetings-and-calls"></a>Réunions et appels

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de participants à une réunion (possibilité de conversation et appel entrant)  | 1000, inclut GCC, GCCH et DoD, mais pas A1 (300). **La fonction de visualisation** permet à un maximum de 20 000 participants en mode écoute de se joindre à une réunion pour laquelle l'organisateur dispose d'une licence pour E3/E5/A3/A5 SKU, ainsi que pour les gouvernements (GCC, GCC High, DoD). L’expérience d’affichage en lecture seule sera bientôt disponible pour les webinaires. En savoir plus sur l'[Expérience d’affichage seul](view-only-meeting-experience.md).<sup>1,2</sup>.|
|Nombre de personnes dans un appel vidéo ou audio de la conversation | 20 |
|Taille maximale des fichiers PowerPoint | 2 Go|
|Teams garde les [enregistrements de réunions](cloud-recording.md) non chargés dans Microsoft Stream, disponibles en téléchargement local | 20 jours |
| Durée maximale de l’enregistrement de la réunion | 4 heures ou 1,5 Go. Lorsque cette limite est atteinte, l’enregistrement se termine et redémarre automatiquement.
  
<sup>1</sup> Pour une expérience optimale dans les réunions de grande taille, les webinaires et les événements en direct, Microsoft recommande d’utiliser la dernière version du client de bureau Teams ou des clients mobiles Teams.

<sup>2</sup> Les présentateurs dans les grandes réunions, les webinaires et les événements en direct doivent utiliser le client de bureau Teams. Pour obtenir des conseils supplémentaires sur l’hébergement de réunions volumineuses, consultez [Meilleures pratiques pour une réunion Teams de grande taille](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).

> [!NOTE]
> Les salles de groupe restreint ne peuvent être créées que dans les réunions qui ont moins de 300 participants. En outre, la création de salles de groupe restreint dans une réunion limite automatiquement le nombre de participants à la réunion à 300. Informez vos utilisateurs finaux de ne pas lancer les salles de groupe restreint auxquelles ils attendent plus de 300 participants. Pour plus d’informations sur les grandes réunions d’équipe, partagez les conseils [Meilleures pratiques pour une réunion Teams volumineuse](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) avec vos utilisateurs finaux.

### <a name="meeting-expiration"></a>Expiration de réunion

> [!NOTE]
> L'URL d'une réunion ne cessera jamais de fonctionner. L'expiration ne concerne que les numéros d'appel RTPC, les coordonnées CVI et/ou les stratégies et paramètres de réunion sous-jacents.

|Type de réunion  |La réunion expire après un certain délai  |Chaque fois qu’une réunion démarre ou est mise à jour, l’expiration se prolonge d’un certain délai  |
|---------|---------|---------|
|Conférence maintenant     |Heure de début + 8 heures         |N/A         |
|Normale sans heure de fin     |Heure de début + 60 jours         | 60 jours        |
|Normale avec heure de fin     |Heure de fin + 60 jours         |60 jours         |
|Périodique sans heure de fin     |Heure de début + 60 jours         |60 jours         |
|Périodique avec heure de fin     |Heure de fin de la dernière occurrence + 60 jours         |60 jours         |

> [!NOTE]
> Les réunions Microsoft Teams ont une durée limite de 30 heures.

## <a name="teams-live-events"></a>Événements en direct Teams

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Taille de l’audience | 10 000 participants |
|Durée de l’événement | 4 heures |
|Événements en direct simultanés exécutés dans une organisation Microsoft 365 ou Office 365 <sup>1</sup> | 15 |

<sup>1</sup> Vous pouvez planifier autant d’Evénements en Direct que vous le souhaitez, mais vous ne pouvez exécuter que 15 à la fois. Dès que le producteur rejoint un événement en direct, celui-ci est considéré comme étant en cours d’exécution. Le producteur qui tente de participer au 16e événement en direct reçoit une erreur.

Pour plus d’informations sur les événements en direct et une comparaison des évènements en direct Teams et Skype Meeting Broadcast, accédez à [Evènements en direct Teams et Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). Consultez également [Programmer un évènement en direct Teams](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

> [!IMPORTANT]
> **Augmentation de la limite d’événements en direct Microsoft 365**
>
> **Afin de continuer la prise en charge des besoins de nos clients, nous étendons les augmentations temporaires des limites pour les événements en direct jusqu’au 30 juin 2022, à savoir :**
>
>- Soutien aux événements accueillant jusqu'à 20 000 participants
>- 50 événements à la fois peuvent être hébergés chez un client
>- Durée de l'événement : 16 heures par diffusion
>
> En plus les Evènements en direct avec plus de 100 000 participants peuvent être planifiés à travers le programme d’assistance Microsoft 365. L’équipe évaluera chaque demande et travail avec vous pour déterminer les options disponibles. [En savoir plus](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Présence dans Outlook

La présence Teams dans Outlook est prise en charge sur l’application de bureau de Outlook 2013 et ultérieure. Pour en savoir plus sur la présence dans Teams, consultez [Présence d’utilisateur dans Teams](presence-admins.md).

## <a name="storage"></a>Stockage

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

> [!NOTE]
> Chaque [canal privé](./private-channels.md) possède son propre site SharePoint (anciennement appelé « collection de sites »).

Si SharePoint n’est pas activé dans le client, les utilisateurs de Microsoft Teams n’ont pas toujours accès au partage des fichiers dans les équipes. Les utilisateurs de conversations privées n’ont pas également accès au partage des fichiers parce que OneDrive Entreprise (lié à la licence SharePoint) est obligatoire pour cette fonctionnalité.

En sauvegardant la bibliothèque de documents SharePoint Online, toutes les règles de conformité au niveau client seront respectées. (Pour en savoir plus, consultez [Interaction  SharePoint Online, OneDrive Entreprise et Microsoft Teams](sharepoint-onedrive-interact.md).)

Etant donné que Teams est exécuté sur le serveur principal de SharePoint Online, les limites SharePoint s’appliquent à la section des fichiers dans une équipe. Voici les limites de stockage de SharePoint Online.

|Fonctionnalité                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée   |1 To par organisation, plus 10 Go par licence achetée |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation           |
|Espace de stockage pour fichiers Teams |Jusqu’à 25 To par site ou groupe |Jusqu’à 25 To par site ou groupe |Jusqu’à 25 To par site ou groupe |Jusqu’à 25 To par site ou groupe |Jusqu’à 25 To par site ou groupe |Jusqu’à 25 To par site ou groupe |
|Limite de taille de fichiers :    |250 Go    |250 Go    |250 Go    |250 Go    |250 Go    |250 Go    |

Les canaux sont sauvegardés dans un site SharePoint Online (auparavant appelé « collection de sites ») créé pour l’équipe. les onglets de fichier au sein des canaux partagent ainsi les limites de stockage de l’équipe à laquelle ils appartiennent.

Pour plus d’informations, voir [Limites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="class-teams"></a>Équipes de classe :

Microsoft Teams Education offrent des modèles dédiés à des scénarios d’éducation uniques tels que l’enseignement en salle. Vous pouvez accéder à plus d’informations sur ;les types d’équipes, notamment les équipes de classe, dans [Choisissez un type d’équipe pour collaborer dans Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

Une équipe de classe est un type de modèle avec des applications supplémentaires incluses, et des limites distinctes au nombre de membres de l’équipe.

> [!NOTE]
> L’utilisation d’équipes de classe nécessite une licence [Microsoft Office 365 pour l’éducation](https://www.microsoft.com/education/products/office).

Les limites pour les équipes de classe sont répertoriées dans le tableau suivant :

|Fonctionnalité  |Limite maximale  |
|---------|---------|
|Nombre de membres dans une équipe.    | Consultez la section [Équipes et canaux](#teams-and-channels) de cet article.        |
|Nombre de membres pour utiliser Affectations dans une équipe de classe    | 300        |
|Nombre de membres pour utiliser un bloc-notes OneNote pour la classe dans une équipe de classe     |300         |

Un équipe de classe peut prendre en charge 300 membres. Toutefois, si vous décidez d’utiliser l’application d’Assignation ou l’application des Bloc-notes de classe, vous devrez maintenir le nombre de membres en dessous de la limite maximale indiquée ci-dessus.

## <a name="tags"></a>Balises

|Fonctionnalité  |Limite maximale  |
|---------|---------|
|Nombre de balises par équipe    | 100        |
|Nombre de balises par défaut suggérées par équipe    | 25        |
|Nombre de membres de l’équipe attribués à un indicateur    |100         |
|Nombre de mots clés attribués à un utilisateur par équipe    |25         |

## <a name="contacts"></a>Contacts

Teams utilise ces contacts :

- Contacts dans l’annuaire Active Directory de votre organisation
- Contacts ajoutés au dossier Outlook par défaut de l’utilisateur

Les utilisateurs de Teams peuvent communiquer avec n’importe quel membre de l’annuaire Active Directory de votre organisation et peuvent ajouter n’importe quel membre de l’annuaire Active Directory de votre organisation à leur liste de contacts en accédant à **Conversation** > **Contacts** ou **Appels** > **Contacts**.

Les utilisateurs de Teams peuvent également ajouter une personne qui n’est pas dans l’annuaire Active Directory de votre organisation à leur liste de contacts en accédant à **Appels** > **Contacts**.

## <a name="browsers"></a>Navigateurs

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Systèmes d’exploitation

Pour plus d'informations sur les exigences logicielles pour chaque plateforme, voir [Obtenir des clients pour Microsoft Teams](get-clients.md).
