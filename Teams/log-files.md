---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e0484b84daa1bd8604c5f2caf9cb728f8fce25a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894409"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
=================================================

Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.

-   Journaux de débogage

-   Journaux des médias

-   Journaux du bureau

Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.

Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.


|Client |Debug|Bureau|Media|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
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

Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.

-   Windows : %userprofile%\\Téléchargements

-   Mac OSX : Téléchargements

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Les journaux des médias contiennent des données de diagnostic sur les appels audio, vidéo et le partage d'écran. Ils sont requis pour les cas de support uniquement sur demande et seul Microsoft peut les lire. Le tableau suivant présente l'emplacement des journaux.


|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>Journaux du bureau
---------------------

Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.

Windows :

1.  Cliquez avec le bouton droit de la souris sur l’**icône Microsoft Teams dans la** barre d’état de votre application, puis sélectionnez **Obtenir les journaux**.

Mac OsX :

1.  Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
