---
title: Prise en charge des versions
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: Cet article décrit la prise en charge du cycle de vie des salles Microsoft Teams.
ms.openlocfilehash: dc4f8c0997ee64f4011aed6056be506738012639
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427686"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Prise en charge de la version de l’application Microsoft teams
 
Microsoft envisage de publier des mises à jour de Microsoft teams dans quelques cas par an avec chaque mise à jour prise en charge pour douze (12) mois à partir de la date de publication de la disponibilité générale (GA). Le support technique est fourni pour l’intégralité de douze (12) mois. Toutefois, la structure de prise en charge est désormais dynamique, en évoluant en deux phases de maintenance distinctes qui varient en fonction de la disponibilité de la version la plus récente.

**Phases de maintenance et de maintenance des mises à jour critiques** \- Lorsque vous exécutez la dernière version de Microsoft Teams, vous recevez des mises à jour régulières qui contiennent des mises à jour de sécurité et de service.

**Mises à jour de sécurité (uniquement) phase de maintenance** \- Après la sortie d’une nouvelle version, la prise en charge des succursales plus anciennes réduit les mises à jour de sécurité uniquement pour le reste du mois (12) mois de maintenance du support technique.

> [!NOTE]
> La version la plus récente est toujours dans la phase de maintenance des mises à jour critiques et de maintenance. Cela signifie que si vous rencontrez une erreur de code qui justifie une mise à jour critique, vous devez disposer de la version la plus récente pour pouvoir recevoir un correctif. Toutes les autres versions prises en charge seront uniquement éligibles pour recevoir des mises à jour de sécurité.

Tout le support prend fin après le douze (12) mois de cycle de vie d’une version a expiré ou si plus de deux mises à jour ont été publiées depuis ce dernier. Ensuite, les clients doivent procéder à la mise à jour vers une version prise en charge.

Toutes les versions sont répertoriées dans les [notes de publication de Microsoft teams](srs2-release-note.md).

# <a name="os-version-support"></a>Version du système d’exploitation pris en charge
Les mises à jour de fonctionnalité de Windows 10 pour les appareils exécutant des salles Microsoft Teams ne sont pas proposées dans un délai de six mois après la mise à jour de Windows. Pour cela, il suffit de placer un bloc spécial pour les périphériques de salle Microsoft teams sur Windows Update pour les canaux d’entreprise (qui est le canal semi-annuel) et d’utiliser les paramètres de l’application. Au cours de cette période bloquée, Microsoft effectue différents tests en interne et par le biais de nos partenaires OEM de l’appareil pour s’assurer que le fonctionnement de nouvelle version de Windows 10 est en harmonie avec l’application et les périphériques connectés à l’application Microsoft Teams. Il est important de garantir la sécurité de l’appareil et de garantir une expérience utilisateur cohérente et de garantir la qualité des expériences proposées par le biais de l’application Microsoft teams salles. 

Depuis le bloc de temps, la mise à jour de fonctionnalité de Windows 10 est proposée en téléchargement sur ces appareils), Microsoft teams salle prend en charge la version spécifique de l’application Windows 10 prévue pour une période de 12 mois. Dans la mesure où les mises à jour de fonctionnalité de Windows 10 sont proposées dans un délai de six mois, cela signifie également que Microsoft teams dispose de deux versions supplémentaires à tester à la fin de la prise en charge de la version actuelle. Cela signifie également qu’une version de Windows 10 n’est pas bloquée tous les six mois pour tous les clients de Microsoft Teams. L’application est en perpétuelle évolution et développée par rapport à la dernière version de Windows. Pour vous assurer que vous obtenez le correctif d’application pour un problème que vous rencontrez sur votre appareil Microsoft Teams, nous vous conseillons vivement à tous les clients de mettre à niveau ces appareils vers la dernière mise à jour de fonctionnalité de Windows 10 proposée pour suivre les recommandations en matière de version de Windows 10.

Par exemple, les appareils Microsoft teams salle requièrent Windows 10 version 1709, car la version minimale prise en charge est 2019. Aucune nouvelle version de l’application n’est proposée aux systèmes sur Windows 10 versions 1703 ou ultérieures.

> [!NOTE]
> Lorsqu’un appareil de salle Microsoft teams est compatible avec la version suivante du système d’exploitation Windows 10, l’appareil est automatiquement mis à jour vers la version suivante par le biais de Windows Update. Les appareils de salle Microsoft Teams ne doivent pas être mis à niveau vers la prochaine version de Windows 10 manuellement ou par le biais des stratégies de groupe Windows Update entreprise (WUFB) à l’aide du «sélectionner le niveau de préparation de Windows pour les mises à jour que vous voulez recevoir» et «sélectionner quand Les versions Preview et les mises à jour de fonctionnalités sont reçues par le biais d’un objet de stratégie de groupe. L’activation de ces stratégies de groupe peut entraîner des problèmes entre la mise à jour du système d’exploitation Windows 10 et l’application Microsoft Teams. 
 
<a name="See"> </a> 
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notes de publication de Microsoft teams](srs2-release-note.md)

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)
