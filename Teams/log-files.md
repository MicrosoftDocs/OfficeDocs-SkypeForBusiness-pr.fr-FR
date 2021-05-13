---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
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
description: Découvrez les journaux de débogage, multimédias et de bureau produits par Microsoft Teams, où ils sont trouvés et comment ils peuvent vous aider dans la surveillance et la résolution des problèmes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337741"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Utilisez les fichiers journaux pour surveiller les données et résoudre les Microsoft Teams

Il existe trois types de fichiers journaux produits automatiquement par le client, qui peuvent être mis à profit pour faciliter la surveillance et la résolution des Teams :

-   [Journaux de débogage](#debug-logs)

-   [Journaux multimédias](#media-logs)

-   [Journaux du bureau](#desktop-logs)

Cet article décrit les trois journaux et leur utilisation. 

Pour plus d’informations sur la résolution de problèmes spécifiques, voir : [Teams résolution des problèmes.](/MicrosoftTeams/troubleshoot/teams) Pour plus d’informations sur la façon de contacter le support technique, voir [Obtenir de l’aide.](/microsoft-365/business-video/get-help-support)

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

## <a name="debug-logs"></a>Journaux de débogage

Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft. Les journaux de débogage sont produits par les clients Windows bureau Mac et les clients de bureau basés sur le navigateur. Les journaux sont basés sur du texte et sont lus de bas en haut. Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.

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

## <a name="media-logs"></a>Journaux des médias

Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran Teams réunions. Ils sont requis pour les cas de support liés à des problèmes liés aux appels.

La journalisation multimédia est désactivée par défaut. Pour enregistrer des données de diagnostic pour Teams réunions, les utilisateurs doivent activer l’option dans le Teams client. Allez à **Paramètres,** activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de  >   **Teams),** redémarrez Teams et reproduisez le problème. 

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
|Teams,msrtc-0-s1039525249.blog     | Contient des informations relatives à la pile de médias. Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Événements de suivi de pile de fichiers multimédias d’enregistrements.         |
|Debug-0-s2790420889.blog    | Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.          |
|tscalling-0-2061129496.blog   |Enregistre les événements dans l’API ts-calling.       |

## <a name="desktop-logs"></a>Journaux du bureau

Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur. Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande. Les journaux sont basés sur du texte et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.

Windows :

 - Cliquez avec le bouton droit **sur l Microsoft Teams** de connexion dans votre bac système, puis **sélectionnez Obtenir les journaux.**

Mac OsX :

 - Sélectionnez **Obtenir les journaux** dans **le** menu déroulant Aide.

Linux :

 - Cliquez sur **l’Microsoft Teams** dans votre bac système, puis **sélectionnez Obtenir les journaux.**

|Client |Lieu |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="browser-trace"></a>Suivi du navigateur

Pour certaines catégories d’erreurs, le Support Microsoft peut exiger que vous collectiez un suivi du navigateur. Ces informations peuvent fournir des détails importants sur l’état du client Teams lorsque l’erreur se produit.

Avant de commencer la trace du navigateur, assurez-vous que vous êtes bien inscrit à Teams. Il est important de le faire avant de commencer la trace de sorte que celle-ci ne contienne pas d’informations de signature sensibles.

Une fois que vous êtes inscrit, sélectionnez l’un des liens suivants, le cas échéant, pour votre navigateur, puis suivez les étapes fournies. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Au cours des étapes, remplacez toutes les références au portail Azure par le client Teams client. 

## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
