---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761092"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
=================================================

Il existe trois types de fichiers journaux créés automatiquement par le client, qui peuvent être utilisés pour aider à résoudre les problèmes liés à Microsoft teams :

-   Journaux de débogage

-   Journaux des médias

-   Journaux du bureau

Lors de la création d’une demande de support auprès du support technique Microsoft, l’ingénieur du support technique doit avoir les journaux de débogage. Le fait de disposer des journaux de débogage avant de créer une demande de support permet à Microsoft de commencer rapidement à résoudre le problème. Les journaux de **médias** ou de **Bureau** ne sont obligatoires que si vous en êtes invité par Microsoft.

> [!NOTE]
> Dans cet article, le terme **journaux de débogage** fait référence aux journaux utilisés pour la résolution des problèmes. Toutefois, les fichiers générés pour ces journaux contiennent le terme journaux de **diagnostic** dans leur nom.  

Le tableau suivant présente les différents clients et leurs journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d’exploitation.


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

Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft. Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients basés sur un navigateur. Les journaux sont basés sur du texte et sont lus du haut vers le bas. Ils peuvent être lus à l’aide d’un éditeur de texte et de nouveaux journaux lors de la connexion au client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion aux services de couche intermédiaire

-   Appel/conversation

Les journaux de débogage sont générés à l’aide des méthodes spécifiques au système d’exploitation suivantes :

-   Windows :

      Raccourci clavier : Ctrl + Alt + Maj + 1

-   Mac OSX :

      Raccourci clavier : Option + Commande + Maj t+1

-   *

      Raccourci clavier : Ctrl + Alt + Maj + 1

Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants :

-   Windows : %userprofile%\\Téléchargements

-   Mac OSX : ~/downloads

-   Linux : ~/downloads

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams. Ils sont requis pour les cas de support liés aux problèmes liés aux appels.

La journalisation multimédia est désactivée par défaut. Pour consigner les données de diagnostic pour les réunions d’équipes, les utilisateurs doivent activer l’option dans le client Teams. Accédez à **paramètres**  >  **généraux**, activez la case à cocher **activer la journalisation des diagnostics de réunion (nécessite le redémarrage d’équipes**), redémarrez Teams, puis reproduisez le problème. 

Le tableau suivant présente les emplacements du journal multimédia. Lorsque vous envoyez les fichiers journaux au support Microsoft, veuillez vérifier l’horodatage des fichiers journaux pour vous assurer que les journaux dépassent la période pendant laquelle vous reproduisez le problème.

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/teams/Media-Stack/*. blog         |
|            |~/Library/Application Support/Microsoft/teams/skylib/*. blog         |
|Linux       |~/.config/Microsoft/Microsoft teams/Media-Stack/*. blog         |
|            |~/.config/Microsoft/Microsoft teams/skylib/*. blog         |

Vous trouverez ci-dessous la liste des fichiers journaux générés ainsi que les informations qu’ils contiennent.

|Nom de fichier journal  |Description  |
|---------|---------|
|Teams. msRTC-0-s1039525249. blog     | Contient des informations relatives à la pile multimédia. Il s’agit de l’état du canal, tel que la résolution, les décodeurs et les encodeurs utilisés, ainsi que le nombre de trames envoyés et reçus, ainsi que l’état de session du partage d’écran vidéo (VBSS).         |
|rtmcontrol. msRTC-0-2415069487. blog      |Enregistre les informations relatives aux actions de contrôle à distance, telles que l’horodatage lorsque le contrôle est fourni et les informations sur le pointeur de la souris.          |
|Teams_MediaStackETW -2-U-xr-U. etl      |Enregistre les événements de suivi des piles de médias.         |
|Debug-0-s2790420889. blog    | Contient des informations relatives à l’agent de média, y compris la qualité de rendu.          |
|tscalling-0-2061129496. blog   |Enregistre les événements dans l’API d’appel TS.       |

<a name="desktop-logs"></a>Journaux du bureau
---------------------

Les journaux de bureau, également appelés journaux de programme d’amorçage, contiennent les données de journalisation qui se produisent entre le client de bureau et le navigateur. Comme les journaux multimédias, ces journaux sont uniquement nécessaires si Microsoft est demandé. Les journaux sont basés sur du texte et peuvent être lus à l’aide d’un éditeur de texte dans un format de haut en bas.

Windows :

 - Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**.

Mac OsX :

 - Dans le menu déroulant **aide** , sélectionnez **obtenir les journaux** .

*

 - Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**.

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft équipes/logs.txt         |


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
