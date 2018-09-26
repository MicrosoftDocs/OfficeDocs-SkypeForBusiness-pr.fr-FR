---
title: Utiliser des fichiers journaux pour le dépannage de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d28bac036476c417ccbe7929a23ab9fb37f3a8
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018899"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Utiliser des fichiers journaux pour le dépannage de Microsoft Teams
=================================================

Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.

-   Journaux de débogage

-   Journaux des médias

-   Journaux du bureau

Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.

Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.


|Client |Debogage|Bureau|Médias|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |
|Windows Phone     |-         |-         |-         |

Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Journaux de débogage
---------------------------

Ces se trouvent les journaux les plus courants et sont requis pour tous les cas de support technique Microsoft. Déboguer les journaux sont générées par les clients de bureau Windows et Mac, ainsi que les clients basé sur un navigateur. Les journaux sont texte et en lecture à partir du bas en. Qu’ils peuvent être lus à l’aide de n’importe quel éditeur de texte en fonction et nouveaux journaux sont créés lors de la connexion dans le client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion à des services de niveau intermédiaire

-   Appel/conversation

Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :

-   Windows :

    1.  Cliquez avec le bouton droit sur l'**icône de Microsoft Teams dans** la barre d'applications et sélectionnez **Obtenir les journaux**.

    2.  Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.

    3.  Raccourci clavier : Ctrl + Alt + Maj + 1

-   Mac OSX :

    1.  Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.

    2.  Raccourci clavier : Option + Commande + Maj t+1

Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.

-   Windows : %userprofile%\\Téléchargements

-   Mac OSX : Téléchargements

-   Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.

<a name="media-logs"></a>Journaux des médias
---------------------------

Les journaux des médias contiennent des données de diagnostic sur les appels audio, vidéo et le partage d'écran. Ils sont requis pour les cas de support uniquement sur demande et seul Microsoft peut les lire. Le tableau suivant présente l'emplacement des journaux.


|Client |Emplacement |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\media-Stack\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>Journaux du bureau
---------------------

Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.

|Client |Emplacement |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
