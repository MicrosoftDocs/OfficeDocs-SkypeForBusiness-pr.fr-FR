---
title: Limites et spécifications de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/09/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Obtenir des informations sur les limites, les spécifications et les autres conditions qui s’appliquent à Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff28cb59dabbf3d9d43dbde00cba73541280b39
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Limites et spécifications de Microsoft Teams
=============================================

Cet article décrit certaines des limites, les spécifications et les autres conditions qui s’appliquent à Microsoft Teams. 

<a name="teams-and-channels"></a>Équipes et canaux 
------------------

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’équipes, qu'un utilisateur peut créer. | 250         |
|Nombre de membres dans une équipe | 2 500       |
|Nombre d’équipes qu'un administrateur global peut créer.        | Un nombre illimité   |
|Nombre d’équipes qu'un locataire Office 365 peut avoir    | 500 000     |
|Nombre de canaux par équipe    | 200         |

<a name="meetings-and-calls"></a>Les réunions et les appels 
------------------

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de participants à une réunion  | 80    |
|Nombre de personnes à une conversation privée  | 20    |

<a name="storage"></a>Stockage
-------

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Si vous n’avez pas SharePoint Online activée dans vos clients, les utilisateurs de Microsoft Teams ne peut pas toujours partager des fichiers dans des équipes. Également les utilisateurs de chat privé ne peuvent pas partager des fichiers OneDrive pour les entreprises (qui est liée à la licence SharePoint) étant requis pour cette fonctionnalité.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. (Pour plus d’informations, consultez [comment SharePoint Online et OneDrive pour les entreprises interagissent avec les équipes Microsoft](sharepoint-onedrive-interact.md).)

Étant donné que les équipes s’exécute sur un serveur SharePoint en ligne principal pour le partage de fichiers, les limitations de SharePoint s’appliquent à la section des fichiers au sein d’une équipe. Voici les limites de stockage applicables pour SharePoint Online.

|Fonctionnalité                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par une organisation plus 0,5 Go chaque licence achetée.  |1 To par une organisation plus 0,5 Go chaque licence achetée.  |1 To par une organisation plus 0,5 Go chaque licence achetée.   |1 To par une organisation plus 0,5 Go chaque licence achetée. |1 To par une organisation plus 0,5 Go chaque licence achetée.  |1 To par organisation           |
|Stockage des fichiers d’équipes |Jusqu'à 25 To par collection de sites ou d’un groupe |Jusqu'à 25 To par collection de sites ou d’un groupe |Jusqu'à 25 To par collection de sites ou d’un groupe |Jusqu'à 25 To par collection de sites ou d’un groupe |Jusqu'à 25 To par collection de sites ou d’un groupe |Jusqu'à 25 To par collection de sites ou d’un groupe |
|Limite de téléchargement de fichier       |15 GO    |15 GO    |15 GO    |15 GO    |15 GO    |15 GO    |

Chaque onglet de fichiers dans des équipes s’exécute sur un serveur principal SharePoint Online, les limites de stockage ci-dessus s’appliquent à chaque couche au sein d’une équipe.

Pour plus d’informations, reportez-vous à la section [limites de SharePoint Online](https://support.office.com/en-us/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Messagerie
---------

Les utilisateurs de participent à des conversations qui font partie de la liste de discussion dans Microsoft Teams doivent avoir une Exchange Online (en nuage) boîte aux lettres d’un administrateur pour rechercher des conversations. C’est parce que les conversations qui font partie de la liste de discussion sont stockées dans les boîtes aux lettres en nuage de participants à la conversation. Si un participant de la conversation n’est pas une boîte aux lettres Exchange Online, l’administrateur ne sera en mesure de rechercher ou de placer un blocage sur des conversations. Par exemple, dans un déploiement hybride d’Exchange, les utilisateurs avec boîtes aux lettres de sur site peuvent être en mesure de participer à des conversations qui font partie de la liste de discussion dans Teams de Microsoft. Toutefois, dans ce cas, le contenu de ces conversations n’est pas disponible pour la recherche et ne peut pas être mis en blocage car les utilisateurs ne disposent de boîtes aux lettres basés sur le cloud. (Pour plus d’informations, voir [comment Exchange et interagir les équipes Microsoft](exchange-teams-interact.md).)

Teams Microsoft chat fonction fonctionne sur un serveur principal Microsoft Exchange, vous pouvez appliquer des limites à la fonction de conversation dans Microsoft Teams de messagerie Exchange. Si les utilisateurs souhaitent envoyer un e-mail à un canal des équipes, ils utilisent l’adresse de messagerie du canal. Une fois un e-mail fait partie d’un canal, toute personne peut répondre à lui permettant de démarrer une conversation. Voici les limites applicables pour l’envoi de courrier électronique à un canal. 

|Fonctionnalité  |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|---------|---------|---------|---------|---------|
|Taille limite des messages&dagger;  |25 KO   |25 KO   |25 KO   |25 KO   |
|Limite des pièces jointes de fichiers&Dagger;  |20     |20     |20     |20    |
|Limite d’images en ligne&Dagger; |50   |50   |50   |50   |

&dagger;Si le message dépasse cette limite, un aperçu du message est généré, et l’utilisateur est invité à consulter/télécharger l’e-mail d’origine à partir du lien fourni.

&Dagger;Si le nombre de pièces jointes ou d’images dépasse cette limite, il se peut que le message ne sera pas traité et un e-mail de rapport de non-remise est envoyé à l’expéditeur pour les informer de l’erreur.

Pour plus d’informations, reportez-vous à la section [limites Exchange en ligne](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Navigateurs 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Systèmes d’exploitation
-----------------

Pour plus d’informations sur la configuration requise du système d’exploitation, reportez-vous à la section [obtenir des clients pour les équipes de Microsoft](get-clients.md).


