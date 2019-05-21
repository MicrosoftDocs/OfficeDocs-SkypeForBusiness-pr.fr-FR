---
title: Limites et spécifications de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/07/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: En savoir plus sur les limites, spécifications et autres configurations requises pour Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c71b789684d6d40ab9eb67e0464f8dc46ae0e96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299680"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limites et spécifications de Microsoft Teams

Cet article présente certaines limites, spécifications et autres configurations requises qui s’appliquent à Teams.

## <a name="teams-and-channels"></a>Équipes et canaux 

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’équipes qu’un utilisateur peut créer | Soumis à une limite objet de 250 et sup1 ;         |
|Nombre de membres dans une équipe. | 5 000       |
|Nombre de membres dans une[équipe à l’échelle de l’organisation](create-an-org-wide-team.md) | 5 000       |
|Nombre d’équipes qu’un administrateur général peut créer        |  500 000   |
|Nombre d’équipes que peut avoir un client Office 365    | 500 000&sup2;     |
|Nombre de canaux par équipe    | 200 (y compris les canaux supprimés) &sup3;         |

& sup1 ; N’importe quel objet dans Azure Active Directory compte dans cette limite. Les administrateurs généraux sont exempts de cette limite, comme les applications appelant Microsoft Graph en utilisant des[autorisations d’application](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Cette limite inclut les équipes archivées.

&sup3; les canaux supprimés peuvent être restaurés dans les 30 jours. Pendant ces 30 jours, le nombre de canaux supprimés continue d’être comptabilisé au canal 200 par équipe. Après 30 jours, un canal supprimé et son contenu sont supprimés de manière définitive et le canal n’est plus compté vers les canaux 200 par équipe.

## <a name="meetings-and-calls"></a>Réunions et appels 

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de personnes dans une réunion  | 250    |
|Nombre de personnes dans une discussion privée  | 50    |

## <a name="storage"></a>Stockage

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Si SharePoint Online n’est pas activé dans votre client, les utilisateurs Microsoft Teams ne peuvent pas toujours partager des fichiers dans les équipes. De plus, les utilisateurs dans une conversation privée ne peuvent pas partager des fichiers car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis pour ces fonctionnalités.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. (Pour plus d’informations, voir[Comment SharePoint Online et OneDrive Entreprise interagissent avec Microsoft Teams](sharepoint-onedrive-interact.md).)

Étant donné que Teams s’exécute sur un serveur principal SharePoint Online pour le partage de fichiers, les limitations SharePoint s’appliquent à la section Fichiers dans une équipe. Voici les limites de stockage applicables pour SharePoint Online.

|Fonctionnalité                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation, plus 10 Go par licence achetée   |1 To par organisation, plus 10 Go par licence achetée |1 To par organisation, plus 10 Go par licence achetée  |1 To par organisation           |
|Espace de stockage pour fichiers Teams |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |Jusqu’à 25 To par collection de sites ou groupe |
|Limite de chargement de fichiers       |15 Go    |15 Go    |15 Go    |15 Go    |15 Go    |15 Go    |

Chaque onglet Fichiers dans Teams est exécuté sur un serveur principal SharePoint Online, donc les limites de stockage ci-dessus s’appliquent à chaque Canal dans une Équipe.

Pour plus d’informations, voir [Limites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="messaging"></a>Messagerie 

Les utilisateurs qui participent aux conversations qui font partie de la liste de Conversation dans Microsoft Teams doivent avoir une boîte aux lettres Exchange Online (sur le cloud) pour qu’un administrateur recherche des conversations instantanées. C’est parce que les conversations qui font partie de la liste de Conversations sont stockées dans les boîtes aux lettres des participants basées sur le cloud. Si un participant de conversation ne dispose pas de boîte aux lettres Exchange Online, l’administrateur ne pourra pas effectuer de recherche ou suspendre de conversations instantanées. Par exemple, dans un déploiement Exchange hybride, les utilisateurs disposant de boîtes aux lettres locales peuvent peut-être participer aux conversations qui font partie de la liste de Conversations dans Microsoft Teams. Toutefois, dans ce cas, le contenu de ces conversations n’est pas consultable et ne peut pas être mis en attente, car les utilisateurs n’ont pas de boîtes aux lettres sur le cloud. (Pour plus d’informations, voir [comment Exchange et Microsoft Teams interagissent](exchange-teams-interact.md).)

Fonction de conversation de Microsoft Teams fonctionne sur un serveur principal Microsoft Exchange, donc vous pouvez appliquer les limites de messagerie Exchange à la fonction de conversation dans Microsoft Teams. Si un utilisateur souhaite envoyer un message électronique à un canal dans Teams, ils utilisent l’adresse de messagerie du canal. Une fois qu’un message électronique fait partie d’un canal, tout le monde peut y répondre et démarrer une conversation. Voici quelques-unes des limites applicables pour l’envoi de courrier à un canal. 

|Fonctionnalité  |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|---------|---------|---------|---------|---------|
|Limite de la taille des messages&dagger;  |25 Ko   |25 Ko   |25 Ko   |25 Ko   |
|Limite du nombre de pièces jointes&Dagger;  |0,10     |0,10     |0,10     |0,10    |
|Utilisation d’images en ligne&Dagger; |50   |50   |50   |50   |

&dagger; Si le message excède cette limite, un aperçu du message est généré et l’utilisateur est invité à afficher/télécharger le message d’origine à partir du lien fourni.

&Dagger; Si le nombre de pièces jointes ou images excède cette limite, le message ne sera pas traité et un message électronique de notification d’échec est envoyé à l’expéditeur pour l’avertir de l’erreur.

> [!NOTE]
> La taille des messages, des pièces jointes et des images incorporées sont les mêmes pour toutes les licences Office 365.

Pour plus d’informations, voir [Limites d’Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="browsers"></a>Navigateurs

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Systèmes d’exploitation

Pour plus d'informations sur les exigences logicielles pour chaque plateforme, voir [Obtenir des clients pour Microsoft Teams](get-clients.md).
