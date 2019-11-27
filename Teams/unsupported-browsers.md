---
title: Réunions Microsoft teams sur les navigateurs non pris en charge
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3412d195e560ee2be1e850d9fcb146d0a0f54d25
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615904"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Réunions Microsoft teams sur les navigateurs non pris en charge

Certains navigateurs tels qu’Internet Explorer 11, Safari et Firefox prennent en charge Microsoft teams Web App, mais ne prennent pas en charge certaines fonctionnalités d’appel et de réunion. Pour contourner cette limitation, Team Web App permet aux utilisateurs de recevoir du son par le biais d’une connexion RTC et de lui permettre d’afficher le contenu présenté (partage d’écran) à un tarif réduit.

Lorsque teams détecte un navigateur non pris en charge, un message s’affiche automatiquement pour vous expliquer le problème et les limites de la session. Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, par exemple pour indiquer à l’utilisateur de laisser un numéro d’appel pour que les équipes puissent appeler l’utilisateur, ou pour demander à l’utilisateur d’appeler le numéro de la Conférence incluse dans l’invitation à la réunion. Le message encourage également l’utilisateur à télécharger et utiliser le [client de bureau teams](https://teams.microsoft.com/downloads) pour l’expérience complète de teams.

Si RTC n’est pas disponible, l’utilisateur ne verra pas les instructions d’accès à la réunion et ne pourra pas participer à la réunion.

## <a name="browser-limitations"></a>Limitations du navigateur

Les utilisateurs d’Team Web App sur les navigateurs non pris en charge sont soumis aux limitations suivantes :

- L’audio est disponible via une connexion RTC uniquement. Les utilisateurs ne peuvent pas utiliser leur micro.
- Les utilisateurs ne peuvent pas partager leur caméra ou voir les vidéos des autres participants, mais peuvent afficher le contenu présenté par le biais du partage d’écran basé sur une image.
- Les utilisateurs ne peuvent pas partager leur écran, même s’ils peuvent voir un écran qu’un autre participant à une réunion partage.
- Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.
- Les utilisateurs ne reçoivent pas les notifications d’appel entrant.
- Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.
- Les utilisateurs ne peuvent pas démarrer de réunions.

## <a name="related-topics"></a>Voir aussi

- [Participation à une réunion teams sur un navigateur non pris en charge](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
- [Spécifications et limites de Teams](/microsoftteams/limits-specifications-teams#browsers)