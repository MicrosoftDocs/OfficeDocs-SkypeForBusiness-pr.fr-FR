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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51d19affd962b396af42f4efaec707388b186094
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778046"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Réunions Microsoft teams sur les navigateurs non pris en charge

Certains navigateurs tels qu’Internet Explorer 11, Safari et Firefox prennent en charge Microsoft teams Web App, mais ne prennent pas en charge certaines fonctionnalités d’appel et de réunion. Pour contourner cette limitation, Team Web App permet aux utilisateurs de recevoir du son par le biais d’une connexion RTC et de lui permettre d’afficher le contenu présenté (partage d’écran) à un tarif réduit.

> [!Note]
> Les applications et services Microsoft 365 ne prennent pas en charge Internet Explorer 11 au début du 17 août 2021 (Microsoft Teams ne prend pas en charge Internet Explorer 11 plus tôt, à compter du 30 novembre 2020). [En savoir plus](https://aka.ms/AA97tsw). Veuillez noter que le navigateur Internet Explorer 11 reste pris en charge. Internet Explorer 11 est un composant du système d’exploitation Windows et [suit la politique de cycle de vie](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) pour le produit sur lequel il est installé.

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

Pour plus d’informations sur la prise en charge du navigateur dans Teams, voir [limites et spécifications pour teams](/microsoftteams/limits-specifications-teams#browsers).

## <a name="related-topics"></a>Voir aussi

- [Participation à une réunion teams sur un navigateur non pris en charge](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
