---
title: Réunions Microsoft Teams sur des navigateurs non pris en charge
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment Teams prend en charge l’audio et la vidéo dans les navigateurs non pris en charge.
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 71fb02fae88f2f61d2d6435e126e20093a5a3baf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267820"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>Réunions Microsoft Teams sur des navigateurs non pris en charge

Certains navigateurs, tels qu’Internet Explorer 11, Safari et Firefox, prennent en charge l’application web Microsoft Teams, mais ne prennent pas en charge certaines fonctionnalités d’appel et de réunion Teams. Pour contourner cette limitation, l’application web Teams permet aux utilisateurs de recevoir de l’audio via une connexion RTC et d’afficher le contenu présenté (partage d’écran) à un taux d’affichage réduit.

> [!Note]
> Les applications et services Microsoft 365 ne prendront pas en charge Internet Explorer 11 à compter du 17 août 2021 (Microsoft Teams ne prendra pas en charge Internet Explorer 11 plus tôt, à compter du 30 novembre 2020). [En savoir plus](https://aka.ms/AA97tsw). Veuillez noter que le navigateur Internet Explorer 11 restera un navigateur pris en charge. Internet Explorer 11 est un composant du système d’exploitation Windows et [suit la politique de cycle de vie](/lifecycle/faq/internet-explorer-microsoft-edge) du produit sur lequel il est installé.

Quand Teams détecte un navigateur non pris en charge, il affiche automatiquement un message expliquant le problème et les limitations de session. Le message fournit des instructions supplémentaires pour accéder à l’audio de la réunion, comme l’avis de l’utilisateur de laisser un numéro de rappel afin que Teams puisse appeler l’utilisateur, ou en demandant à l’utilisateur d’appeler le numéro de conférence inclus dans l’invitation à la réunion. Le message encourage également l’utilisateur à télécharger et à utiliser le [client de bureau Teams](https://teams.microsoft.com/downloads) pour l’expérience Teams complète.

Si PSTN n’est pas disponible, l’utilisateur ne voit pas les instructions d’accès à la réunion et ne peut pas participer à la réunion.

## <a name="browser-limitations"></a>Limitations du navigateur

Les personnes qui utilisent l’application web Teams sur des navigateurs non pris en charge rencontreront les limitations suivantes :

- L’audio est disponible via une connexion RTC uniquement. Les utilisateurs ne peuvent pas utiliser leur microphone.
- Les utilisateurs ne peuvent pas partager leur caméra ou voir les vidéos d’autres participants, mais peuvent afficher le contenu présenté par le biais du partage d’écran basé sur des images.
- Les utilisateurs ne peuvent pas partager leur écran, bien qu’ils puissent voir un écran partagé par un autre participant à la réunion.
- Les utilisateurs ne peuvent pas prendre le contrôle pendant une session de partage d’écran.
- Les utilisateurs ne recevront pas de notifications d’appel entrant.
- Si l’appel est interrompu, la réunion ne se reconnecte pas automatiquement.
- Les utilisateurs ne peuvent pas démarrer les réunions.

Pour plus d’informations sur la prise en charge des navigateurs dans Teams, consultez [Limites et spécifications pour Teams](./limits-specifications-teams.md#browsers).

## <a name="related-topics"></a>Voir aussi

- [Participer à une réunion Teams sur un navigateur non pris en charge](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)