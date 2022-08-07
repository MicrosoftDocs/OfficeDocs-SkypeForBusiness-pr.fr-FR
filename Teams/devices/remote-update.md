---
title: Mettre à jour des appareils Microsoft Teams à distance
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Mettre à jour les téléphones Microsoft Teams, les panneaux Teams et les barres de collaboration à distance à l’aide du Centre d’administration Teams
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269459"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Mettre à jour des appareils Microsoft Teams à distance

À l’aide du Centre d’administration Microsoft Teams, vous pouvez mettre à jour vos appareils Teams, tels que les téléphones Teams, les panneaux Teams et les barres de collaboration, à distance, et vous pouvez choisir le comportement de mise à jour automatique du microprogramme de l’appareil. Vous pouvez mettre à jour les éléments suivants sur vos appareils à l’aide du Centre d’administration Teams :

- Application Teams et agent d’administration Teams
- Application portail d’entreprise
- Application d’agent OEM
- Microprogramme de l’appareil

Les mises à jour du microprogramme de l’appareil peuvent être appliquées automatiquement ou planifiées pour une date et une heure ultérieures. Les autres mises à jour d’appareils disponibles ne sont pas appliquées automatiquement, mais peuvent être appliquées manuellement ou planifiées pour une date et une heure futures.

> [!NOTE]
> Bien que les mises à jour du microprogramme de l’appareil puissent être planifiées, si la date et l’heure planifiées tombent après le délai maximal de 30 ou 90 jours configuré, la mise à jour du microprogramme est appliquée lorsque le délai maximal est atteint. La date et l’heure planifiées sont ignorées. En outre, la mise à jour à distance des appareils Microsoft Teams est une fonctionnalité qui n’est pas encore disponible sur les locataires cloud du gouvernement des États-Unis (GCC-High).

Pour gérer les appareils, vous devez être administrateur général, administrateur du service Teams ou administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, consultez [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Choisir le comportement de mise à jour automatique du microprogramme de l’appareil

Les mises à jour du microprogramme de l’appareil sont appliquées automatiquement. Vous pouvez décider d’appliquer des mises à jour dès qu’une mise à jour est publiée (si vous choisissez cette option, les mises à jour sont appliquées le premier week-end après la publication d’une mise à jour), ou 30 ou 90 jours après la publication d’une mise à jour. Par défaut, les mises à jour du microprogramme de l’appareil sont appliquées 30 jours après leur publication.

> [!IMPORTANT]
> La dernière mise à jour du microprogramme n’est pas appliquée sur votre appareil Teams. Au lieu de cela, la mise à jour appliquée automatiquement sur votre appareil est retardée d’une version. Par exemple, supposons que la version « 10 » de votre appareil est appliquée et que la version « 11 » est publiée. La version « 11 » n’est pas encore appliquée. Au lieu de cela, votre appareil ne sera mis à jour vers la version « 11 » qu’une fois la version « 12 » publiée.

> [!NOTE]
> Certains appareils ne prennent pas encore en charge la mise à jour automatique du microprogramme. L’application des paramètres de mise à jour automatique du microprogramme sur les appareils qui ne prennent pas en charge les mises à jour automatiques n’aura aucune incidence sur ces appareils. Pour toute question sur la prise en charge des mises à jour automatiques du microprogramme par votre appareil, contactez le fabricant de votre appareil.

Pour choisir le comportement de mise à jour automatique de vos appareils, procédez comme suit :

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Naviguez sur **les téléphones IP** **des appareils** >  Teams, **les barres de collaboration** ou **les panneaux Teams**.
3. Sélectionnez un ou plusieurs appareils, puis sélectionnez **Mettre à jour**.
4. Sous **Mise à jour automatique du microprogramme**, sélectionnez l’une des options suivantes :
    - **Dès que disponible** La deuxième mise à jour la plus récente du microprogramme d’appareil est appliquée le premier week-end après la publication de la dernière mise à jour.
    - **Différer 30 jours** La deuxième mise à jour la plus récente du microprogramme d’appareil est appliquée 30 jours après la publication de la dernière mise à jour.
    - **Différer 90 jours** La deuxième mise à jour la plus récente du microprogramme d’appareil est appliquée 90 jours après la publication de la dernière mise à jour.
5. Sélectionnez **Mettre à jour**.

Si, pour une raison quelconque, vous devez rétablir une mise à jour du microprogramme de l’appareil, vous devez réinitialiser votre appareil à ses paramètres d’usine. Réinitialisez votre appareil en suivant les instructions de son fabricant.  

## <a name="manually-update-remote-devices"></a>Mettre à jour manuellement les appareils distants

Lorsque vous mettez à jour un ou plusieurs appareils à l’aide du Centre d’administration, vous pouvez décider s’il faut mettre à jour les appareils immédiatement ou planifier une mise à jour pour une date et une heure futures.

Pour mettre à jour manuellement les appareils distants, procédez comme suit :

1. Connectez-vous au Centre d’administration Microsoft Teams en visitant https://admin.teams.microsoft.com.
2. Naviguez sur **les téléphones IP** **des appareils** >  Teams, **les barres de collaboration** ou **les panneaux Teams**.
3. Sélectionnez un ou plusieurs appareils, puis sélectionnez **Mettre à jour**.
4. Sous **Mises à jour manuelles**, sélectionnez **Planifier** si vous souhaitez planifier la mise à jour pour une date et une heure futures. Les mises à jour sont appliquées à la date et à l’heure du fuseau horaire sélectionné dans le **fuseau horaire**.

Ce que vous verrez dépend de la sélection d’un ou de plusieurs appareils. L’image de gauche ci-dessous montre plusieurs appareils sélectionnés, tandis que l’image à droite affiche un seul appareil sélectionné.

:::image type="content" source="../media/device-update-status.png" alt-text="Affichages d’appareils uniques et multiples dans le volet d’état de mise à jour de l’appareil.":::

Lorsque vous sélectionnez plusieurs appareils, vous pouvez choisir les types de mises à jour à appliquer à chaque appareil sélectionné. Sélectionnez les types de mise à jour que vous souhaitez appliquer, puis sélectionnez **Mettre à jour**.

Lorsque vous sélectionnez un seul appareil, les mises à jour disponibles pour l’appareil s’affichent. Si plusieurs types de mises à jour sont disponibles pour l’appareil, sélectionnez chaque type de mise à jour à appliquer. Vous pouvez afficher la **version actuelle** appliquée sur l’appareil et la **nouvelle version** qui sera appliquée. Sélectionnez la ou les mises à jour que vous souhaitez appliquer, puis sélectionnez **Mettre à jour**.

Après avoir sélectionné **Mettre à jour**, les mises à jour sont appliquées à vos appareils à la date et à l’heure que vous avez sélectionnées si vous avez planifié une mise à jour. Si vous n’avez pas sélectionné de date et d’heure futures, les mises à jour sont appliquées à vos appareils en quelques minutes.
