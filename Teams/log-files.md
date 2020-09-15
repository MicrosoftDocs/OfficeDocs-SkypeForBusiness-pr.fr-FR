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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766758"
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

-   Mac OSX : ~/downloads

-   Linux : ~/downloads

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams. Ils sont requis pour les cas d’assistance uniquement en cas de demande et ne peuvent être vérifiés par Microsoft. 

La journalisation multimédia est désactivée par défaut. Pour consigner les données de diagnostic pour les réunions d’équipes, les utilisateurs doivent activer l’option dans le client Teams. Accédez à **paramètres**  >  **généraux**, activez la case à cocher **activer la journalisation des diagnostics de réunion (nécessite le redémarrage de l’équipe**), puis redémarrez Teams.

Le tableau suivant présente les emplacements du journal.

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

Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.

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

