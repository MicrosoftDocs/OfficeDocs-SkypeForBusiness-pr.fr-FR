---
title: Mettre à jour les appareils Microsoft teams à distance
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
description: Mise à jour des téléphones et des barres de collaboration de Microsoft teams à l’aide du centre d’administration teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962885"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Mettre à jour les appareils Microsoft teams à distance

À l’aide du centre d’administration de Microsoft Teams, vous pouvez mettre à jour les appareils de votre équipe, tels que les téléphones et les barres de collaboration, et vous pouvez choisir le comportement de mise à jour automatique du microprogramme du périphérique. Vous pouvez mettre à jour les éléments suivants sur vos appareils à l’aide du centre d’administration teams :

- Application équipes et agent d’administration des équipes
- Application portail d’entreprise
- Application OEM agent
- Microprogramme du périphérique

Les mises à jour du microprogramme de périphériques peuvent être appliquées automatiquement ou planifiées pour des dates et heures ultérieures. Les autres mises à jour de périphériques disponibles ne s’appliquent pas automatiquement, mais peuvent être appliquées manuellement ou programmées pour des dates et heures ultérieures.

> [!NOTE]
> Si les mises à jour de microprogramme de périphériques peuvent être planifiées, si la date et l’heure planifiées se trouvent après le délai maximal configuré de 30 ou 90, la mise à jour du microprogramme est appliquée lorsque le délai maximal est atteint. La date et l’heure planifiées ne sont pas prises en compte. En outre, la mise à jour des appareils Microsoft teams à distance est une fonctionnalité qui n’est pas encore disponible pour les clients du Cloud fédéral des États-Unis (GCC-High).

Pour gérer les appareils, vous devez être un administrateur général, un administrateur de service teams ou un administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, voir [utiliser les rôles d’administrateur de Microsoft teams pour gérer teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Choisir le comportement de mise à jour automatique du microprogramme de périphérique

Les mises à jour du microprogramme du périphérique s’appliquent automatiquement. Vous pouvez décider si vous souhaitez appliquer les mises à jour dès qu’une mise à jour est activée (si vous choisissez cette option, les mises à jour sont appliquées le premier week-end après la sortie d’une mise à jour) ou 30 ou 90 jours après la sortie d’une mise à jour. Par défaut, les mises à jour du microprogramme de périphériques s’appliquent 30 jours après la sortie.

> [!IMPORTANT]
> La dernière mise à jour du microprogramme n’est pas appliquée sur votre appareil Teams. Au lieu de cela, la mise à jour appliquée automatiquement sur votre appareil est retardée d’une version. Par exemple, supposons que votre appareil dispose de la version « 10 » appliquée et qu’une version « 11 » soit publiée. La version « 11 » n’est pas encore appliquée. Votre appareil est mis à jour à la place de la version « 11 » après la version « 12 ».

> [!NOTE]
> Certains appareils ne prennent pas en charge la mise à jour automatique du microprogramme actuellement. L’application des paramètres de mise à jour automatique du microprogramme sur les appareils qui ne prennent pas en charge les mises à jour automatiques n’aura aucun impact sur ces appareils. Pour savoir si votre appareil prend en charge les mises à jour automatiques du microprogramme, contactez le fabricant de votre appareil.

Pour choisir le comportement de mise à jour automatique de vos appareils, procédez comme suit :

1. Connectez-vous au centre d’administration Microsoft teams en visitant https://admin.teams.microsoft.com
2. Parcourir les **appareils**  >  **mobiles** ou les **barres de collaboration**
3. Sélectionner un ou plusieurs appareils, puis sélectionner **mettre à jour**
4. Sous **mise à jour automatique du microprogramme**, sélectionnez l’une des options suivantes :
    - Dès **que possible** La seconde mise à jour du microprogramme du périphérique est appliquée le premier week-end après la sortie de la dernière mise à jour.
    - **Différer de 30 jours** La seconde mise à jour du microprogramme du périphérique est appliquée 30 jours après la sortie de la dernière mise à jour.
    - **Différer de 90 jours** La seconde mise à jour du microprogramme du périphérique est appliquée 90 jours après la mise à jour de la dernière mise à jour.
5. Sélectionnez **mettre à jour**

Si, pour une raison quelconque, vous devez revenir à une mise à jour de microprogramme de périphérique, vous devez réinitialiser votre appareil à ses paramètres d’usine. Réinitialisez votre appareil à l’aide des instructions du fabricant.  

## <a name="manually-update-remote-devices"></a>Mise à jour manuelle des appareils distants

Lorsque vous mettez à jour un ou plusieurs appareils à l’aide du centre d’administration, vous pouvez choisir de mettre à jour les appareils immédiatement ou de planifier une mise à jour pour des dates et heures ultérieures.

Pour mettre à jour manuellement des appareils distants, procédez comme suit :

1. Connectez-vous au centre d’administration Microsoft teams en visitant https://admin.teams.microsoft.com
2. Parcourir les **appareils**  >  **mobiles** ou les **barres de collaboration**
3. Sélectionner un ou plusieurs appareils, puis sélectionner **mettre à jour**
4. Sous **mises à jour manuelles**, sélectionnez **échéancier** si vous souhaitez planifier la mise à jour pour des dates et heures ultérieures. Les mises à jour sont appliquées à la date et l’heure du fuseau horaire sélectionné dans **TimeZone**.

Ce que vous voyez varie selon que vous avez sélectionné un ou plusieurs appareils. L’image de gauche ci-dessous montre plusieurs appareils sélectionnés alors que l’image de droite montre un seul appareil sélectionné.

:::image type="content" source="../media/device-update-status.png" alt-text="Affichages simples et multiples dans le volet État de la mise à jour de l’appareil":::

Lorsque vous sélectionnez plusieurs appareils, vous pouvez choisir les types de mise à jour à appliquer à chaque périphérique sélectionné. Sélectionnez les types de mise à jour que vous souhaitez appliquer, puis sélectionnez **mettre à jour**.

Lorsque vous sélectionnez un périphérique unique, les mises à jour disponibles pour l’appareil sont affichées. S’il existe plusieurs types de mise à jour pour l’appareil, sélectionnez chaque type de mise à jour à appliquer. Vous pouvez afficher la **version actuelle** appliquée à l’appareil et la **nouvelle version** qui sera appliquée. Sélectionnez la ou les mises à jour que vous souhaitez appliquer, puis sélectionnez **mettre à jour**.

Après avoir sélectionné **mise à jour**, les mises à jour sont appliquées à vos périphériques à la date et l’heure que vous avez sélectionnées si vous avez planifié une mise à jour. Si vous n’avez pas sélectionné de date et d’heure ultérieures, des mises à jour sont appliquées à vos périphériques en quelques minutes.
