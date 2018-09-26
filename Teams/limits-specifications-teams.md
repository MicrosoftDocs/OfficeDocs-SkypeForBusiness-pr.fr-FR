---
title: Limites et les spécifications de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: Découvrez les limites, les spécifications et autres conditions qui s’appliquent à Microsoft Teams.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: af408506195878a4c213044e6c2223ae75bb815b
ms.sourcegitcommit: 72e2c4622deb3a7f4c0eafbee91dcf139ef44775
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25090185"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Limites et les spécifications de Microsoft Teams
=============================================

Cet article décrit certaines des limites, les spécifications et autres conditions qui s’appliquent à Microsoft Teams. 

<a name="teams-and-channels"></a>Équipes et canaux 
------------------

|Fonctionnalité    | Limite maximale |
|-----------|---------------|
|Nombre d’un utilisateur peut créer des équipes | Soumis à une limite de 250 objet & le sup1 ;         |
|Nombre de membres dans une équipe | 2 500       |
|Nombre d’un administrateur global peut créer des équipes        | 500 000   |
|Nombre d’équipes que non attribuable à un client Office 365    | 500 000     |
|Nombre de canaux par l’équipe    | 200         |

& sup1 ; N’importe quel objet d’annuaire dans Azure Active Directory compte dans cette limite.

<a name="meetings-and-calls"></a>Réunions et appels 
------------------

|Fonctionnalité     | Limite maximale |
|------------|---------------|
|Nombre de personnes à une réunion  | 250    |
|Nombre de personnes à une conversation privée  | 20    |

<a name="storage"></a>Stockage
-------

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Si vous ne disposez pas SharePoint Online activée sur votre client, les utilisateurs Microsoft Teams toujours ne peuvent pas partager des fichiers dans les équipes. Également les utilisateurs de chat privé ne peuvent pas partager des fichiers car OneDrive entreprise (qui est lié à la licence SharePoint) est requis pour cette fonctionnalité.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. (Pour plus d’informations, voir [comment SharePoint Online et OneDrive entreprise interagissent avec les équipes Microsoft](sharepoint-onedrive-interact.md)).

Équipes s’exécute sur un serveur principal SharePoint Online pour le partage de fichiers, les limites de SharePoint s’appliquent à la section fichiers au sein d’une équipe. Voici les limites de stockage applicables pour SharePoint Online.

|Fonctionnalité                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Stockage                 |1 To par organisation plus de 10 Go par licence acheté  |1 To par organisation plus de 10 Go par licence acheté  |1 To par organisation plus de 10 Go par licence acheté   |1 To par organisation plus de 10 Go par licence acheté |1 To par organisation plus de 10 Go par licence acheté  |1 To par l’organisation           |
|Stockage des fichiers d’équipes |Jusqu'à 25 To par collection de sites ou un groupe |Jusqu'à 25 To par collection de sites ou un groupe |Jusqu'à 25 To par collection de sites ou un groupe |Jusqu'à 25 To par collection de sites ou un groupe |Jusqu'à 25 To par collection de sites ou un groupe |Jusqu'à 25 To par collection de sites ou un groupe |
|Limite de téléchargement de fichier       |15 GO    |15 GO    |15 GO    |15 GO    |15 GO    |15 GO    |

Chaque onglet de fichiers dans les équipes s’exécute sur un serveur principal SharePoint Online, les limites de stockage ci-dessus s’appliquent à chaque canal au sein d’une équipe.

Pour plus d’informations, voir [limites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Messagerie
---------

Les utilisateurs de participer à des conversations qui font partie de la liste de conversation dans Microsoft Teams doivent avoir une Exchange Online (en nuage) boîte aux lettres pour un administrateur pour rechercher des conversations. C’est parce que les conversations qui font partie de la liste de conversation sont stockées dans les boîtes aux lettres en nuage de participants à la conversation. Si un participant de conversation ne possède une boîte aux lettres Exchange Online, l’administrateur sera en mesure de rechercher ou de placer une suspension des conversations. Par exemple, dans un déploiement Exchange hybride, les utilisateurs avec des boîtes aux lettres locales peuvent être en mesure de participer à des conversations qui font partie de la liste de conversation dans Microsoft Teams. Toutefois, dans ce cas, le contenu à partir de ces conversations n’est pas disponible pour la recherche et ne peut pas être mis en attente, car les utilisateurs ne possèdent des boîtes aux lettres en nuage. (Pour plus d’informations, voir [comment Exchange et les équipes Microsoft interagir](exchange-teams-interact.md).)

Fonction de conversation Microsoft Teams fonctionne sur un serveur principal Microsoft Exchange, vous pouvez appliquer des limites à la fonction de conversation dans Microsoft Teams de messagerie Exchange. Si les utilisateurs souhaitent envoyer un message électronique à un canal dans les équipes, ils utilisent l’adresse de messagerie de canal. Une fois qu’un message électronique fait partie d’un canal, n’importe qui peut répondre à lui permettant de démarrer une conversation. Voici certaines limites applicables pour l’envoi de courrier électronique à un canal. 

|Fonctionnalité  |Office 365 Entreprise E1  |Office 365 Entreprise E3  |Office 365 Entreprise E5  |Office 365 Entreprise F1  |
|---------|---------|---------|---------|---------|
|Limite de taille de message&dagger;  |25 KO   |25 KO   |25 KO   |25 KO   |
|Limite des pièces jointes de fichier&Dagger;  |20     |20     |20     |20    |
|Limite des images en ligne&Dagger; |50   |50   |50   |50   |

&dagger;Si le message dépasse cette limite, un aperçu du message est généré et l’utilisateur est invité à consulter/télécharger le courrier électronique d’origine à partir du lien fourni.

&Dagger;Si le nombre de pièces jointes ou d’images dépasse cette limite, le message ne sera pas traité et un message électronique de rapport de non-remise est envoyé à l’expéditeur pour les informer de l’erreur.

Pour plus d’informations, consultez la rubrique [limites d’Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Navigateurs   
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Systèmes d’exploitation
-----------------

Pour plus d’informations sur la configuration requise du système d’exploitation, voir [obtenir des clients pour les équipes Microsoft](get-clients.md).


