---
title: Mettre à jour les appareils Microsoft Teams à distance
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Mettre à jour les téléphones et les barres de collaboration de Microsoft Teams à distance à l’aide du Centre d’administration Teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962885"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Mettre à jour les appareils Microsoft Teams à distance

Le Centre d’administration Microsoft Teams vous permet de mettre à jour vos appareils Teams, tels que les téléphones et les barres de collaboration, à distance, et vous pouvez choisir le comportement de mise à jour automatique du microprogramme de l’appareil. Vous pouvez mettre à jour ce qui suit sur vos appareils à l’aide du Centre d’administration Teams :

- Application Teams et agent d’administration teams
- Application portail d’entreprise
- Application agent OEM
- Microprogramme de l’appareil

Les mises à jour du microprogramme de l’appareil peuvent être appliquées automatiquement ou prévues pour une date et une heure futures. Les autres mises à jour disponibles sur les appareils ne sont pas appliquées automatiquement, mais peuvent être appliquées manuellement ou pour une date et une heure futures.

> [!NOTE]
> Si des mises à jour du microprogramme de l’appareil peuvent être programmées, si la date et l’heure prévues tombent après le délai maximal de 30 ou 90 jours configuré, la mise à jour du microprogramme est appliquée lorsque le délai maximal est atteint. La date et l’heure prévues sont ignorées. En outre, la mise à jour des appareils Microsoft Teams à distance est une fonctionnalité qui n’est pas encore disponible sur les clients Cloud du gouvernement américain (GCC-High).

Pour gérer les appareils, vous devez être administrateur global, administrateur du service Teams ou administrateur de périphériques Teams. Pour plus d’informations sur les rôles d’administrateur, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Choisir le comportement de mise à jour automatique du microprogramme de l’appareil

Les mises à jour du microprogramme de l’appareil sont appliquées automatiquement. Vous pouvez choisir d’appliquer les mises à jour dès leur publication (si vous choisissez cette option, les mises à jour sont appliquées le premier week-end suivant la publication d’une mise à jour) ou 30 ou 90 jours après la publication d’une mise à jour. Par défaut, les mises à jour du microprogramme de l’appareil sont appliquées 30 jours après leur publication.

> [!IMPORTANT]
> La dernière version de mise à jour du microprogramme n’est pas appliquée à votre appareil Teams. Au lieu de cela, la mise à jour appliquée automatiquement sur votre appareil est retardée d’une version. Par exemple, supposons que la version « 10 » soit appliquée à votre appareil et que la version « 11 » soit publiée. La version « 11 » ne sera pas encore appliquée. Au lieu de cela, votre appareil sera mis à jour vers la version « 11 » une fois la version « 12 » publiée.

> [!NOTE]
> Certains appareils ne supportent pas encore la mise à jour automatique du microprogramme. L’application de paramètres de mise à jour automatique du microprogramme sur les appareils qui ne supportent pas les mises à jour automatiques n’aura aucun effet sur ces appareils. Pour plus d’informations sur la prise en charge des mises à jour automatiques du microprogramme par votre appareil, contactez le fabricant de votre appareil.

Pour choisir le comportement de mise à jour automatique pour vos appareils, vous pouvez :

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com
2. Naviguer dans **les téléphones**  >  **d’appareils** **ou les barres de collaboration**
3. Sélectionnez un ou plusieurs appareils, puis sélectionnez Mettre **à jour**
4. Sous **Mise à jour automatique du microprogramme,** sélectionnez l’une des actions suivantes :
    - **Dès que disponible** La mise à jour du microprogramme de l’appareil le deuxième plus récent est appliquée le premier week-end après la publication de la dernière mise à jour.
    - **Différer 30 jours** La mise à jour de microprogramme de l’appareil la plus récente est appliquée 30 jours après la publication de la dernière mise à jour.
    - **Différer 90 jours** La mise à jour de microprogramme de l’appareil la plus récente est appliquée 90 jours après la publication de la dernière mise à jour.
5. Sélectionnez **Mettre à jour**

Si, pour une raison quelconque, vous devez rétablir la mise à jour d’un microprogramme d’appareil, vous devez rétablir les paramètres par usine de votre appareil. Réinitialisez votre appareil en utilisant les instructions de son fabricant.  

## <a name="manually-update-remote-devices"></a>Mettre à jour manuellement les appareils distants

Lorsque vous mettez à jour un ou plusieurs appareils à l’aide du Centre d’administration, vous pouvez décider de les mettre à jour immédiatement ou de planifier une mise à jour pour des date et heure ultérieures.

Pour mettre à jour manuellement les appareils distants, vous pouvez :

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com
2. Naviguer dans **les téléphones**  >  **d’appareils** **ou les barres de collaboration**
3. Sélectionnez un ou plusieurs appareils, puis mettre à **jour**
4. Sous **Mises à jour manuelles,** **sélectionnez Planifier** si vous voulez planifier la mise à jour pour une date et une heure futures. Les mises à jour sont appliquées à la date et l’heure du fuseau horaire sélectionné dans **le fuseau horaire.**

Ce que vous voyez dépend de la sélection d’un ou plusieurs appareils. L’image de gauche ci-dessous montre plusieurs appareils sélectionnés, tandis que l’image de droite affiche un seul appareil sélectionné.

:::image type="content" source="../media/device-update-status.png" alt-text="Affichages d’un ou plusieurs appareils dans le volet d’état de mise à jour de l’appareil":::

Lorsque vous sélectionnez plusieurs appareils, vous pouvez choisir les types de mises à jour à appliquer à chaque périphérique sélectionné. Sélectionnez les types de mises à jour que vous voulez appliquer, puis **sélectionnez Mettre à jour.**

Lorsque vous sélectionnez un seul appareil, les mises à jour disponibles pour l’appareil sont affichées. Si plusieurs types de mises à jour sont disponibles pour l’appareil, sélectionnez chaque type de mise à jour à appliquer. Vous pouvez afficher **la version actuelle appliquée** sur l’appareil et la nouvelle **version** qui sera appliquée. Sélectionnez la ou les mises à jour que vous voulez appliquer, puis sélectionnez **Mettre à jour.**

Après avoir sélectionné **Mettre à** jour, les mises à jour sont appliquées à vos appareils à la date et l’heure que vous avez sélectionnées si vous avez prévu une mise à jour. Si vous n’avez pas sélectionné de date et d’heure futures, les mises à jour sont appliquées à vos appareils en quelques minutes.
