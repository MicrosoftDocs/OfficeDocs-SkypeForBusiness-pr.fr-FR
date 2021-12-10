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
ms.openlocfilehash: 100d21338cf77642836793ab9cf69d426d1fd463
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410685"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Utilisez les fichiers journaux pour surveiller les données et résoudre les Microsoft Teams

Il existe trois types de fichiers journaux produits automatiquement par le client, qui peuvent être mis à profit pour faciliter la surveillance et la résolution des Teams :

-   [Journaux de débogage](#debug-logs)

-   [Journaux multimédias](#media-logs)

-   [Journaux du bureau](#desktop-logs)

Cet article décrit ces journaux et leur utilisation. Pour plus d’informations sur la résolution de problèmes spécifiques, voir : [Teams résolution des problèmes.](/MicrosoftTeams/troubleshoot/teams) Pour plus d’informations sur la façon de contacter le support technique, voir [Obtenir de l’aide.](/microsoft-365/business-video/get-help-support) Lorsque vous créez une demande de support auprès du Support Microsoft, l’ingénieur support a besoin des journaux de débogage. Disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de rapidement commencer à résoudre le problème. **Les journaux** **multimédias ou** de bureau ne sont requis que si Microsoft les demande.

> [!NOTE]
> Dans cet article, les journaux **de débogage** font référence aux journaux utilisés pour la résolution des problèmes. Toutefois, les fichiers générés pour ces journaux contiennent les journaux **de diagnostic de terme** dans leurs noms.  

## <a name="collect-and-enable-logging"></a>Collecter et activer la journalisation

Il est important de collecter les journaux dès qu’un problème se produit. Les journaux peuvent être collectés en quelques clics seulement.

- Windows : Cliquez avec le bouton droit sur l Teams dans la tray système, puis **sélectionnez Recueillir les fichiers de support.** 

- Mac : sélectionnez le menu Aide, puis **sélectionnez Recueillir les fichiers de support.**

Les journaux de débogage, de bureau et multimédia sont collectés dans un dossier avec le nom Journal de _diagnostic MSTeams. \<local date and time\>_ Ce dossier peut être compressé et partagé lorsque vous ouvrez une demande de support auprès du Support Microsoft. Le dossier contiendra des dossiers pour bureau, réunion (média) et débogage (web). Vous pouvez collecter les fichiers à l’aide des raccourcis clavier suivants :

- Windows : <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac : <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


La journalisation multimédia est désactivée par défaut. Pour activer la journalisation des médias, les utilisateurs doivent activer l’option dans Teams client. Allez à **Paramètres,** puis sélectionnez Activer la journalisation pour les diagnostics de réunion  >   **(nécessite un redémarrage Teams).** Le client Teams doit être redémarré pour que la journalisation commence (redémarrez-le en cliquant avec le bouton droit sur l’icône dans votre station d’accueil (Mac) ou barre des tâches (Windows), puis en sélectionnant **Quitter.** Après avoir quitté, cliquez simplement sur l’icône de l’application pour l’ouvrir à nouveau).

Si un problème se produit avec une réunion ou un événement en direct spécifique, il est utile que l’URL soit associée à la réunion. Cela fournit des informations supplémentaires pour identifier précisément la réunion ou l’événement en direct dans les journaux. Ces informations peuvent être collectées à partir de n’importe quel participant à une réunion ou du présentateur ou du producteur pour un événement en direct. Cette URL peut être capturée en pointant sur l’URL de jointage et en choisissant **Copier le lien hypertexte.**

> [!NOTE]
> Si la journalisation multimédia est activée, des fichiers supplémentaires seront inclus dans le dossier Réunion, lesquels seront nécessaires pour examiner les problèmes audio et vidéo. Si la journalisation multimédia n’est pas activée, le nombre de journaux sera limité.
  
> [!NOTE]
> Les journaux de débogage étaient précédemment collectés à l’aide des raccourcis clavier ci-dessous. Ceux-ci fonctionnent toujours et terminent la même capture de journal que l’option **Recueillir les fichiers de support.**
>
> - Windows : <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac : <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


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

Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac. Les journaux de débogage sont produits par les clients Windows bureau Mac et les clients de bureau basés sur le navigateur. Les journaux sont textuels et lus de bas en haut. Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.

Les journaux de débogage contiennent les flux de données suivants :

-   Connexion

-   Demandes de connexion à des services de niveau intermédiaire

-   Appel/conversation

Pour collecter des journaux pour Linux :
- Raccourci clavier : <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- Les fichiers seront disponibles dans `~/Downloads`

Pour collecter des journaux pour les navigateurs et les Windows :
- Raccourci clavier : <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- Les fichiers seront disponibles dans `%userprofile%\Downloads`

## <a name="media-logs"></a>Journaux des médias

Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac. Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran Teams réunions. Ils sont requis pour les cas de support liés à des problèmes liés aux appels.

La journalisation multimédia est désactivée par défaut. Pour enregistrer des données de diagnostic pour Teams réunions, les utilisateurs doivent activer l’option dans le Teams client. Allez à **Paramètres,** activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de  >   **Teams),** redémarrez Teams et reproduisez le problème. 

Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’heure et l’heure des fichiers journaux pour vous assurer que les journaux couvrent la période lors de la reproduction du problème.

Pour collecter des journaux pour Linux :  
- Les fichiers seront disponibles aux emplacements suivants :
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Pour collecter les journaux des Windows :  
- Les fichiers seront disponibles aux emplacements suivants :
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\media-stack\\\*\.blog`
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\skylib\\\*\.blog` 

Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.

<br/>

|Nom du fichier journal  |Description  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contient des informations relatives à la pile de médias. Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Événements de suivi de pile de fichiers multimédias d’enregistrements.         |
|`Debug-0-s2790420889.blog`    | Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.          |
|`tscalling-0-2061129496.blog`   |Enregistre les événements dans l’API ts-calling.       |

## <a name="desktop-logs"></a>Journaux du bureau

Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac. Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur. Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande. Les journaux sont textuels et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.

Pour collecter des journaux pour Linux :
- Cliquez sur l’Microsoft Teams de connexion dans votre bac système, puis **sélectionnez Obtenir les journaux.**
- Les fichiers seront disponibles dans `~/.config/Microsoft/Microsoft Teams/logs.txt` .
  
Pour collecter les journaux des Windows :
- Cliquez sur l’Microsoft Teams dans votre bac système, puis sélectionnez **Recueillir les fichiers de support.**
- Le `logs.txt` fichier est ouvert automatiquement dans Bloc-notes’application.

Lors de l’étude de problèmes Teams connexion, vous devrez peut-être recueillir manuellement les journaux du bureau. Ces fichiers journaux sont situés à l’emplacement %appdata%\Microsoft\Teams dans Windows.

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
  
## <a name="webrtc-logs-in-browsers"></a>Journaux WebRTC dans les navigateurs
Les journaux WebRTC peuvent aider le Support Microsoft en fournissant des détails de connexion pour les appels audio et vidéo. Suivez les étapes pour accéder aux journaux WebRTC dans Edge (Chromium) ou Chrome : 
  
1.  Ouvrez un nouvel onglet et allez à l’une des URL suivantes :
    -   Edge (Chromium) :`edge://webrtc-internals/`
    -   Chrome : `chrome://webrtc-internals/`
  
2.  Ouvrez l Teams application web et reproduisez le problème.
  
3.  Revenir à l’onglet accessible à l’étape 1 et vous verrez au moins deux onglets :
    -   Demandes GetUserMedia
    -   `https://teams.microsoft.com/url`

4.  Sélectionnez l’onglet avec le nom de l’Teams et enregistrez le contenu de la page.

## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
