---
title: Mettre à jour Microsoft appareils Teams à distance
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
description: Mettez à jour Microsoft téléphones Teams, les panneaux Teams et les salles Teams sur Android, des appareils à distance à l’aide du centre d’administration Teams.
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438262"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Mettre à jour Microsoft appareils Teams à distance

À l’aide du centre d’administration Microsoft Teams, vous pouvez mettre à jour vos appareils Teams, tels que les téléphones Teams, les panneaux Teams et les salles Teams sur Android, à distance. Les composants logiciels suivants sur votre appareil peuvent être mis à jour à partir du Centre d’administration Teams :

- Application Teams
- Microprogramme de l’appareil

Les mises à jour du microprogramme de l’appareil se produisent automatiquement par défaut. Toutefois, vous pouvez mettre à jour manuellement le microprogramme et d’autres composants logiciels. Lors de l’application manuelle des mises à jour, elles peuvent être appliquées immédiatement ou planifiées pour une date et une heure ultérieures.

Seules les versions de microprogramme qui ont été testées par Microsoft sont disponibles pour une mise à jour automatique ou manuelle via le Centre d’administration Teams. Les versions de microprogramme testées par Microsoft sont **étiquetées Vérifié par Microsoft**. Les versions de microprogramme qui n’ont pas été testées par Microsoft sont étiquetées **Version inconnue**. Les appareils exécutant une version de microprogramme inconnue ne peuvent pas être automatiquement mis à jour ; ces appareils ne peuvent être mis à jour que manuellement.

Pour gérer les appareils, vous devez être administrateur général, administrateur de service Teams ou administrateur d’appareils Teams. Pour plus d’informations sur les rôles d’administrateur, consultez [Utiliser Microsoft rôles d’administrateur Teams pour gérer Teams](../using-admin-roles.md).

## <a name="assign-devices-to-an-automatic-update-phase"></a>Affecter des appareils à une phase de mise à jour automatique

L’attribution d’appareils à une phase de mise à jour automatique est une fonctionnalité Salles Teams Pro pour salles Teams sur les appareils Android. Les appareils dotés d’une licence salles Teams De base seront affectés à la phase Général. Toutes les phases préconfigurées sont conservées et aucune autre modification n’est autorisée. Pour plus d’informations, consultez [licences Salles Microsoft Teams](../rooms/rooms-licensing.md).  

Les mises à jour automatiques des appareils Teams à l’aide du Centre d’administration Teams ne sont pas disponibles dans GCC High. Toutefois, les organisations de GCC High peuvent [mettre à jour manuellement les appareils Teams](#manually-update-remote-devices) à l’aide du centre d’administration Teams.

> [!IMPORTANT]
> La fonctionnalité de mise à jour automatique est actuellement en version préliminaire. Mises à jour peut être déployé plus lentement que la phase que vous avez sélectionnée. Au cours des prochains mois, la vitesse à laquelle les mises à jour sont déployées automatiquement augmentera jusqu’à ce qu’elles atteignent la phase que vous avez sélectionnée.

> [!NOTE]
> Certains appareils ne prennent pas encore en charge les mises à jour automatiques du microprogramme. L’application des paramètres de mise à jour automatique du microprogramme sur les appareils qui ne prennent pas en charge les mises à jour automatiques n’aura aucun effet sur ces appareils. Si vous souhaitez savoir si votre appareil prendra en charge les mises à jour automatiques du microprogramme, contactez le fabricant de votre appareil.
>
> Mises à jour sont appliquées les week-ends et en dehors des heures normales d’ouverture pour éviter les interruptions. Au cours d’une phase, les appareils seront mis à jour progressivement sur quelques semaines plutôt que tous à la fois.

Pour choisir la phase de mise à jour automatique pour vos appareils, procédez comme suit :

1. Connectez-vous à Microsoft Centre d’administration Teams en visitant https://admin.teams.microsoft.com.
2. Accédez à **Appareils Teams**, puis sélectionnez **Téléphones**, **Affichages**, **Panneaux** ou **salles Teams sur Android**.  
3. Sélectionnez un ou plusieurs appareils, puis sélectionnez **Mettre à jour**.
4. Sous **Mise à jour automatique du microprogramme**, sélectionnez l’une des options suivantes :
    - **Test** Cette option est idéale pour les appareils de laboratoire ou de test sur lesquels vous pouvez effectuer toute validation que vous devez effectuer. Mises à jour démarrer le déploiement dès que la dernière version du microprogramme est publiée. Précédemment appelé **Dès que possible**.
    - **Générales** Il s’agit de l’option par défaut qui convient le mieux à la plupart de vos appareils à usage général. Mises à jour démarrer le déploiement seulement après 30 jours écoulés à partir de la publication de la nouvelle version du microprogramme. Précédemment appelé **Différer de 30 jours**.
    - **Final** Cette option est idéale pour les appareils utilisés par les adresses IP virtuelles et dans des paramètres volumineux une fois la validation à grande échelle terminée. Mises à jour démarrer le déploiement uniquement après 90 jours à partir de la publication de la nouvelle version du microprogramme. Précédemment appelé **Différer de 90 jours**.
5. Sélectionnez **Mettre à jour**.

Pour connaître les appareils de phase dans lesquels se trouvent, consultez la colonne **Mise à jour automatique du microprogramme** dans le Centre d’administration Teams. Pour voir quels appareils font partie d’une phase spécifique, utilisez l’option **Filtrer** avec le paramètre **phase de mise à jour** automatique.

Pour rétablir une mise à jour du microprogramme d’appareil, vous devez réinitialiser votre appareil à ses paramètres d’usine. Réinitialisez votre appareil en suivant les instructions de son fabricant.  

## <a name="manually-update-remote-devices"></a>Mettre à jour manuellement les appareils distants

Si vous souhaitez mettre à jour manuellement des appareils à l’aide du Centre d’administration Teams, vous pouvez décider de mettre à jour les appareils immédiatement ou de planifier une mise à jour pour une date et une heure ultérieures.

Pour mettre à jour manuellement des appareils distants, procédez comme suit :

1. Connectez-vous à Microsoft Centre d’administration Teams en visitant https://admin.teams.microsoft.com.
2. Accédez aux **appareils Teams**, puis sélectionnez **Téléphones**, **Affichages**, **Panneaux** ou **salles Teams sur Android**.
3. Sélectionnez un ou plusieurs appareils, puis sélectionnez **Mettre à jour**.
4. Sous **Mises à jour manuelles**, sélectionnez **Planifier** si vous souhaitez planifier la mise à jour pour une date et une heure ultérieures. Les mises à jour sont appliquées à la date et à l’heure dans le fuseau horaire sélectionné dans **Fuseau horaire**.

Ce que vous verrez varie selon que vous avez sélectionné un ou plusieurs appareils. L’image de gauche ci-dessous montre plusieurs appareils sélectionnés, tandis que l’image de droite montre un seul appareil sélectionné.

:::image type="content" source="../media/device-update-status.png" alt-text="Affichages d’appareils uniques et multiples dans le volet d’état de mise à jour de l’appareil.":::

Lorsque vous sélectionnez plusieurs appareils, vous pouvez choisir les types de mise à jour à appliquer à chaque appareil sélectionné. Sélectionnez les types de mise à jour que vous souhaitez appliquer, puis sélectionnez **Mettre à jour**.

Lorsque vous sélectionnez un seul appareil, les mises à jour disponibles pour l’appareil s’affichent. Si plusieurs types de mise à jour sont disponibles pour l’appareil, sélectionnez chaque type de mise à jour à appliquer. Vous pouvez afficher la **version actuelle** appliquée sur l’appareil et la **nouvelle version** qui sera appliquée. Sélectionnez la ou les mises à jour que vous souhaitez appliquer, puis sélectionnez **Mettre à jour**.

Une fois que vous avez sélectionné **Mettre à jour**, les mises à jour sont appliquées à vos appareils à la date et à l’heure que vous avez sélectionnées si vous avez planifié une mise à jour. Si vous n’avez pas sélectionné de date et d’heure ultérieures, les mises à jour sont appliquées à vos appareils en quelques minutes.
