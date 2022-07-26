---
title: Journaux d’activité et suivi du navigateur pour Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux d’activité de Navigateur et WebRTC produits par Microsoft Teams, où ils se trouvent, comment collecter des journaux avec Support Microsoft et comment ils peuvent vous aider à surveiller et à résoudre les problèmes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005460"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Journaux d’activité et suivi du navigateur pour Teams

Pour certaines catégories d’erreurs, Support Microsoft devrez peut-être collecter une trace de navigateur. Ces informations peuvent fournir des détails importants sur l’état du client Teams lorsque l’erreur se produit. Cet article explique comment collecter les journaux de navigateur et webRTC pour Teams.

## <a name="browser-logs"></a>Journaux d’activité du navigateur

Avant de démarrer la trace du navigateur, vérifiez que vous êtes connecté à Teams. Il est important de le faire avant de démarrer la trace afin que la trace ne contienne pas d’informations de connexion sensibles.

Une fois connecté, sélectionnez l’un des liens suivants, le cas échéant pour votre navigateur, puis suivez les étapes fournies. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Dans les étapes, remplacez toutes les références au Portail Azure par le client Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Journaux WebRTC dans les navigateurs

Les journaux WebRTC peuvent aider Support Microsoft en fournissant des détails de connexion pour les appels audio et vidéo. Suivez les étapes pour accéder aux journaux WebRTC dans Edge (Chromium) ou Chrome :
  
1. Ouvrez un nouvel onglet et accédez à l’une des URL suivantes :
    - Edge (Chromium) :`edge://webrtc-internals/`
    - Chrome: `chrome://webrtc-internals/`
  
2. Ouvrez l’application web Teams et reproduisez le problème.
  
3. Retour à l’onglet accessible à l’étape 1 et vous verrez au moins deux onglets :
    - Demandes GetUserMedia
    - `https://teams.microsoft.com/url`

4. Choisissez l’onglet portant le nom de l’application Teams et enregistrez le contenu de la page.

## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)

[Configurer des fichiers journaux pour la surveillance et la résolution des problèmes dans Teams](/MicrosoftTeams/log-files)
