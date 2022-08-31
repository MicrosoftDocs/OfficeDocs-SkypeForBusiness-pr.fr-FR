---
title: Configurer des fichiers journaux pour la surveillance et la résolution des problèmes dans Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux d’activité Debug, Media et Desktop produits par Microsoft Teams, où ils se trouvent et comment ils peuvent aider à la surveillance et à la résolution des problèmes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae6e6eb0c84eae8293f141940842506fa3f54142
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466032"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Configurer des fichiers journaux pour la surveillance et la résolution des problèmes dans Teams

Il existe trois types de fichiers journaux générés automatiquement par le client, qui peuvent être utilisés pour faciliter la supervision et la résolution des problèmes teams :

-   [Journaux de débogage](#debug-logs)

-   [Journaux d’activité multimédias](#media-logs)

-   [Journaux du bureau](#desktop-logs)

Cet article décrit ces journaux et leur utilisation. Pour plus d’informations sur la résolution des problèmes spécifiques, consultez : [Résolution des problèmes Teams](/MicrosoftTeams/troubleshoot/teams). 

Pour plus d’informations sur la façon de contacter le support technique, consultez [Obtenir un support](/microsoft-365/business-video/get-help-support).

> [!NOTE]
> Dans cet article, le terme **Journaux de débogage** fait référence aux journaux utilisés pour la résolution des problèmes. Toutefois, les fichiers générés pour ces journaux contiennent les **journaux de diagnostic de** terme dans leurs noms.  

## <a name="logs-overview"></a>Vue d’ensemble des journaux

Il est important de collecter les journaux dès qu’un problème se produit.

Lors de la création d’une demande de support avec Support Microsoft, l’ingénieur du support technique requiert les journaux de débogage. Le fait de disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de commencer rapidement à résoudre le problème. **Les journaux multimédias** ou **de bureau** ne sont requis que si Microsoft le demande.

Les journaux de débogage, de bureau et de média seront collectés dans un dossier portant le nom _de journal de diagnostic MSTeams \<local date and time\>_. Ce dossier peut être compressé et partagé lorsque vous ouvrez une demande de support avec Support Microsoft. Le dossier contient des dossiers pour Desktop, Meeting (Media) et Debug (web). Vous pouvez collecter les fichiers à l’aide des raccourcis clavier suivants :

- Windows : <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Maj</kbd> + <kbd>1</kbd>

- Mac : <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


Si un problème se produit avec une réunion spécifique ou un événement en direct, il est utile d’associer l’URL à la réunion. L’URL fournit des informations supplémentaires pour vous aider à identifier la réunion exacte ou l’événement en direct dans les journaux d’activité. Ces informations peuvent être collectées auprès de n’importe quel participant pour une réunion ou d’un présentateur ou d’un producteur pour un événement en direct. Cette URL peut être capturée en pointant sur l’URL de jointure et en choisissant **Copier le lien hypertexte**.

> [!NOTE]
> Si la journalisation multimédia est activée, des fichiers supplémentaires sont inclus dans le dossier Réunion, qui sont nécessaires pour examiner les problèmes audio et vidéo. Si la journalisation multimédia n’est pas activée, un nombre limité de journaux d’activité est disponible.
  
Le tableau suivant présente les différents clients et leurs journaux d’activité associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d’exploitation.

|Client |Debug|Bureau|Media|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).

## <a name="debug-logs"></a>Journaux de débogage

Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients basés sur un navigateur. Les journaux d’activité sont basés sur du texte et sont lus à partir du bas vers le haut. Ils peuvent être lus à l’aide de n’importe quel éditeur de texte, et de nouveaux journaux d’activité sont créés lors de la connexion au client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion à des services de niveau intermédiaire

-   Appel/conversation

Pour collecter les journaux pour Linux :
- Raccourci clavier : <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Maj</kbd> + <kbd>1</kbd>  
- Les fichiers seront disponibles dans `~/Downloads`

Pour collecter les journaux d’activité pour Navigateur et Windows :
- Raccourci clavier : <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Maj</kbd> + <kbd>1</kbd>  
- Les fichiers seront disponibles dans `%userprofile%\Downloads`

Pour collecter les journaux pour Mac :
- Raccourci clavier : <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- Les fichiers seront disponibles dans `~/Downloads`

## <a name="media-logs"></a>Journaux des médias

Les journaux multimédias contiennent des données de diagnostic sur le partage audio, vidéo et d’écran dans les réunions Teams. Elles sont requises pour les cas de support liés à des problèmes liés aux appels.

La journalisation du média est activée par défaut pour les ordinateurs si votre UC est :
- n’importe quelle Apple M1
- n’importe quel Intel Xeon
- intel i9, à l’exception des séries U, G7, M et MQ
- n’importe quelle 6ème génération et intel i7 ultérieure, à l’exception des séries U, G7, M et MQ

Sinon, elle est désactivée par défaut. Il existe deux façons de consigner les données de diagnostic pour les réunions Teams :

- Administration configuration : vous pouvez gérer les journaux multimédias pour vos utilisateurs finaux
- Configuration de l’utilisateur final : vos utilisateurs finaux peuvent activer les journaux multimédias

### <a name="admin-configuration"></a>configuration Administration

La gestion des journaux multimédias pour vos utilisateurs finaux offre une expérience de dépannage transparente, en particulier lorsque les problèmes sont intermittents. Les administrateurs peuvent utiliser l’applet de commande TeamsMediaLoggingPolicy pour activer et gérer la journalisation des médias pour les utilisateurs.

Lisez [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) pour les applets de commande PowerShell et plus d’informations.

### <a name="end-user-configuration"></a>Configuration de l’utilisateur final

Pour que vos utilisateurs finaux consignent les données de diagnostic pour les réunions Teams, ils doivent activer l’option dans le client Teams. Ils passent à **Paramètres** > **généraux**, sélectionnent **activer les journaux multimédias (données de diagnostic pour le partage audio, vidéo et d’écran). Nécessite le redémarrage de Teams)** (nécessite le redémarrage de Teams), redémarrer Teams et reproduire le problème. Le client Teams doit être redémarré pour que la journalisation commence. Les utilisateurs peuvent le redémarrer en cliquant avec le bouton droit sur l’icône dans leur dock (Mac) ou leur barre des tâches (Windows) et en sélectionnant Quitter. Une fois qu’ils ont quitté, ils peuvent cliquer sur l’icône de l’application pour ouvrir à nouveau Teams.

> [!NOTE]
> Lorsque vos utilisateurs se déconnectent de Teams, la journalisation multimédia est réinitialisée à sa valeur par défaut.

### <a name="collecting-and-sending-media-logs"></a>Collecte et envoi de journaux multimédias

Avant d’envoyer les fichiers journaux au support Microsoft, vérifiez l’horodatage des fichiers journaux pour vous assurer que les journaux couvrent la période pendant laquelle vous avez reproduit le problème.

Pour collecter les journaux pour Linux :  
- Les fichiers seront disponibles aux emplacements suivants :
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Pour collecter les journaux d’activité pour Windows :  
- Les fichiers seront disponibles aux emplacements suivants :
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

Pour collecter les journaux pour Mac :
- Les fichiers seront disponibles aux emplacements suivants :
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.

<br/>

|Nom du fichier journal  |Description  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contient des informations relatives à la pile multimédia. Cela inclut l’état du canal, comme la résolution, les décodeurs et les encodeurs utilisés, ainsi que le nombre d’images envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra.         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Enregistre les informations relatives aux actions de contrôle à distance, telles que l’horodatage lorsque le contrôle est donné, et les informations du pointeur de la souris.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Enregistre les événements de trace de la pile multimédia.         |
|`Debug-0-s2790420889.blog`    | Contient des informations relatives à l’agent multimédia, y compris la qualité de rendu.          |
|`tscalling-0-2061129496.blog`   |Enregistre les événements dans l’API ts-calling.       |

## <a name="desktop-logs"></a>Journaux du bureau

Les journaux d’activité de bureau, également appelés journaux du programme d’amorçage, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur. À l’instar des journaux d’activité multimédias, ces journaux d’activité ne sont nécessaires que si Microsoft les demande. Les journaux d’activité sont basés sur du texte et peuvent être lus à l’aide de n’importe quel éditeur de texte dans un format de haut en bas.

Pour collecter les journaux pour Linux :
- Cliquez sur l’icône Microsoft Teams dans votre barre d’état système, puis **sélectionnez Obtenir les journaux**.
- Les fichiers seront disponibles dans `~/.config/Microsoft/Microsoft Teams/logs.txt`.

Pour collecter les journaux pour Mac :
- Cliquez sur le menu Aide dans Microsoft Teams, puis **sélectionnez Collecter les fichiers de support**.
- Le `logs.txt` fichier se trouve dans le dossier Bureau à l’intérieur du dossier _journal \<local date and time>des diagnostics MSTeams_.

Pour collecter les journaux d’activité pour Windows :
- Cliquez sur l’icône Microsoft Teams dans votre barre d’état système, puis **sélectionnez Collecter les fichiers de support**.
- Le `logs.txt` fichier est ouvert automatiquement dans le Bloc-notes.

Lors de l’examen des problèmes de connexion à Teams, vous devrez peut-être collecter manuellement les journaux de bureau. Ces fichiers journaux se trouvent dans %appdata%\Microsoft\Teams dans Windows.

## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)

[Journaux d’activité et suivi du navigateur pour Teams](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
