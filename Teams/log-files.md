---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085750"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
=================================================

Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.

-   Journaux de débogage

-   Journaux des médias

-   Journaux du bureau

When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.

The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.


|Client |Debug|Bureau|Media|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Journaux de débogage
---------------------------

Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft. Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients reposant sur un navigateur. Il s’agit de fichiers texte qui sont lus de bas en haut. Ils peuvent être lus à l’aide de n’importe quel éditeur de texte. En outre, des journaux sont créés lors de la connexion au client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion à des services de niveau intermédiaire

-   Appel/conversation

Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :

-   Windows :

      Raccourci clavier : Ctrl + Alt + Maj + 1

-   Mac OSX :

      Raccourci clavier : Option + Commande + Maj t+1

-   *

      Raccourci clavier : Ctrl + Alt + Maj + 1

Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.

-   Windows : %userprofile%\\Téléchargements

-   Mac OSX : Téléchargements

-   Linux : ~/downloads

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.


|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/teams/Media-Stack/*. blog         |
|            |~/Library/Application Support/Microsoft/teams/skylib/*. blog         |
|Linux       |~/.config/Microsoft/Microsoft teams/Media-Stack/*. blog         |
|            |~/.config/Microsoft/Microsoft teams/skylib/*. blog         |



<a name="desktop-logs"></a>Journaux du bureau
---------------------

Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.

Windows :

1.  Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, sélectionnez **obtenir les journaux**

Mac OsX :

1.  Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.

*

1.  Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft équipes/logs.txt         |


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

