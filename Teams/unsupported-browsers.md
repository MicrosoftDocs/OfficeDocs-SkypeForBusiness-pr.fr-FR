---
title: Réunions Microsoft Teams sur des navigateurs non pris en compte
author: cichur
ms.author: v-cichur
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
description: Découvrez comment Teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121312"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Réunions Microsoft Teams sur des navigateurs non pris en compte

Certains navigateurs, tels qu’Internet Explorer 11, Safari et Firefox, ne supportent pas l’application web Microsoft Teams, mais pas certaines des fonctionnalités d’appel et de réunion de Teams. Pour contourner cette limitation, l’application web Teams permet aux utilisateurs de recevoir de l’audio via une connexion PSTN et leur permet d’afficher du contenu présenté (partage d’écran) à une vitesse d’affichage réduite.

> [!Note]
> Les applications et services Microsoft 365 ne prendra pas en charge Internet Explorer 11 à compter du 17 août 2021 (Microsoft Teams ne prendra pas en charge Internet Explorer 11 plus tôt, à compter du 30 novembre 2020). [En savoir plus](https://aka.ms/AA97tsw). Veuillez noter que le navigateur Internet Explorer 11 restera un navigateur pris en charge. Internet Explorer 11 est un composant [](/lifecycle/faq/internet-explorer-microsoft-edge) du système d’exploitation Windows et suit la politique de cycle de vie du produit sur lequel il est installé.

Lorsque Teams détecte un navigateur non pris en défaut, il affiche automatiquement un message expliquant le problème et les limites de la session. Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, par exemple en conseillant à l’utilisateur de laisser un numéro de rappeler pour que Teams puisse appeler l’utilisateur, ou en lui demandez d’appeler le numéro de conférence inclus dans l’invitation à la réunion. Ce message encourage également l’utilisateur à télécharger et à utiliser le client de [bureau Teams](https://teams.microsoft.com/downloads) pour une expérience Teams complète.

Si PSTN n’est pas disponible, l’utilisateur ne voit pas les instructions pour accéder à la réunion et ne peut pas participer à la réunion.

## <a name="browser-limitations"></a>Limites du navigateur

Les personnes qui utilisent l’application web Teams sur des navigateurs non pris en défaut rencontreront les limitations suivantes :

- Le son est disponible uniquement via une connexion RSTN. Les utilisateurs ne peuvent pas utiliser leur microphone.
- Les utilisateurs ne peuvent pas partager leur caméra ni voir les vidéos des autres participants, mais peuvent afficher le contenu présenté via le partage d’écran basé sur les images.
- Les utilisateurs ne peuvent pas partager leur écran, même s’ils peuvent voir un écran partagé par un autre participant à la réunion.
- Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.
- Les utilisateurs ne recevront pas de notifications d’appel entrant.
- Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.
- Les utilisateurs ne peuvent pas démarrer de réunions.

Pour plus d’informations sur la prise en charge du navigateur dans Teams, voir [Limites et spécifications pour Teams.](./limits-specifications-teams.md#browsers)

## <a name="related-topics"></a>Rubriques connexes

- [Participer à une réunion Teams sur un navigateur non pris en défaut](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)