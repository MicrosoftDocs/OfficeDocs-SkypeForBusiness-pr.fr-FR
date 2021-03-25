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
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112190"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
=================================================

Il existe trois types de fichiers journaux produits automatiquement par le client, que vous pouvez utiliser pour vous aider à résoudre les problèmes de Microsoft Teams :

-   Journaux de débogage

-   Journaux des médias

-   Journaux du bureau

Lorsque vous créez une demande de support auprès du Support Microsoft, l’ingénieur support a besoin des journaux de débogage. Disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de rapidement commencer à résoudre le problème. **Les journaux** **multimédias ou** de bureau ne sont requis que si Microsoft les demande.

> [!NOTE]
> Dans cet article, les journaux **de débogage** font référence aux journaux utilisés pour le dépannage. Toutefois, les fichiers générés pour ces journaux contiennent les journaux **de diagnostic de terme** dans leurs noms.  

Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés à des emplacements spécifiques au client et au système d’exploitation.


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

Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft. Les journaux de débogage sont produits par les clients de bureau Windows et Mac, ainsi que par les clients basés sur le navigateur. Les journaux sont basés sur du texte et sont lus de bas en haut. Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion à des services de niveau intermédiaire

-   Appel/conversation

Les journaux de débogage sont produits à l’aide des méthodes de système d’exploitation suivantes :

-   Windows :

      Raccourci clavier : Ctrl + Alt + Maj + 1

-   Mac OSX :

      Raccourci clavier : Option + Commande + Maj t+1

-   Linux :

      Raccourci clavier : Ctrl + Alt + Maj + 1

Les journaux de débogage sont téléchargés automatiquement dans les dossiers suivants :

-   Windows : %userprofile%\\Téléchargements

-   Mac OSX : ~/Downloads

-   Linux : ~/Téléchargements

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams. Ils sont requis pour les cas de support liés à des problèmes liés aux appels.

La journalisation multimédia est désactivée par défaut. Pour enregistrer des données de diagnostic pour les réunions Teams, les utilisateurs doivent activer l’option dans le client Teams. Sélectionnez la case à cocher **Paramètres** généraux, activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de Teams), redémarrez  >  Teams et reproduisez le problème. 

Le tableau suivant présente les emplacements des journaux multimédias. Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’heure et l’heure des fichiers journaux pour vous assurer que les journaux couvrent la période lors de la reproduction du problème.

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.

|Nom du fichier journal  |Description  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contient des informations relatives à la pile de médias. Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Événements de suivi de pile de fichiers multimédias d’enregistrements.         |
|Debug-0-s2790420889.blog    | Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.          |
|tscalling-0-2061129496.blog   |Enregistre les événements dans l’API ts-calling.       |

<a name="desktop-logs"></a>Journaux du bureau
---------------------

Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur. Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande. Les journaux sont basés sur du texte et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.

Windows :

 - Cliquez avec le bouton droit **sur l’icône Microsoft Teams** dans votre bac système, puis **sélectionnez Obtenir les journaux.**

Mac OsX :

 - Sélectionnez **Obtenir les journaux** dans **le** menu déroulant Aide.

Linux :

 - Cliquez sur **l’icône Microsoft Teams** dans votre bac système, puis **sélectionnez Obtenir les journaux.**

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)