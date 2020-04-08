---
title: Prise en charge des versions
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article décrit la prise en charge du cycle de vie des salles Microsoft Teams.
ms.openlocfilehash: 27610cd7a7ed5c2bca1fcb118b3687149d2872d0
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190829"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Prise en charge de la version de l’application Microsoft teams
 
L’application Microsoft teams salles obtient des mises à jour de quelques fois par an. Chacune des mises à jour prises en charge pour douze (12) mois à partir de la date de publication de la disponibilité générale (GA). Le support technique est fourni pour l’intégralité de douze (12) mois. Toutefois, la structure de support technique est dynamique, avec deux phases distinctes qui dépendent de la disponibilité de la version la plus récente :

- \- **Phase de maintenance et de mise à jour critique** lorsque vous exécutez la dernière version de l’application Microsoft Teams, vous recevez des mises à jour régulières contenant des mises à jour de *sécurité et de maintenance* .

- **Mises à jour de sécurité : phase** \- uniquement lors de la publication d’une nouvelle version de l’application Microsoft teams salles, les versions plus anciennes de l’application disposent d’un niveau de prise en charge limité, avec des *mises à jour de sécurité* pour le reste du cycle de vie de douze (12) mois.

> [!NOTE]
> La version la plus récente est toujours dans la phase de maintenance et les mises à jour critiques. Lorsque vous rencontrez un problème de code qui justifie une mise à jour critique, vous devez également installer la version la plus récente pour recevoir un correctif. Toutes les autres versions prises en charge seront uniquement éligibles pour recevoir des mises à jour de sécurité.

Tout le support prend fin après le douze (12) mois de cycle de vie d’une version a expiré ou si plus de deux mises à jour ont été publiées depuis ce dernier. Ensuite, les clients doivent procéder à la mise à jour vers une version prise en charge.

Toutes les versions sont répertoriées dans les [notes de publication de Microsoft teams](rooms-release-note.md).

## <a name="windows-10-release-support"></a>Prise en charge de Windows 10

Dans les options de maintenance du canal semi-annuel de Microsoft Teams, il est nécessaire de disposer des références SKU Windows 10 IoT entreprise ou Windows 10 entreprise. Ces autres éditions de Windows 10 ne sont pas prises en charge :

- Éditions de Windows 10 entreprise de maintenance à long terme (LTSB)/canal de maintenance à long terme (LTSC)
- Internet sur Windows 10 d’objets (IoT) Enterprise LTSB/LTSC éditions
- toute autre version de Windows, telle que Windows 10 professionnel ou édition familiale

Une mise à jour de fonctionnalité de Windows 10 n’est pas disponible ou mise à jour sur les appareils Microsoft teams Un délai intentionnel de six mois après la date de disponibilité générale publiée sur la page [informations de publication de Windows 10](https://docs.microsoft.com/windows/release-information/) . Le délai est utilisé pour valider la compatibilité de la version de Windows 10 pour l’application Microsoft Teams, le matériel et les périphériques audio certifiés. La validation commence et continue pendant le développement actif de chaque version majeure de Windows 10. Un temps supplémentaire est nécessaire pour vérifier que tous les fabricants d’appareils ont créé des images mises à jour pour leurs appareils, et pour que Microsoft teams certifie et teste ces images. Pendant la période de validation, l’application Microsoft teams salle utilise [Windows Update pour les stratégies de groupe pour les entreprises](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) afin de différer les mises à jour de fonctionnalité de Windows 10. Suite à la détection et à la résolution des problèmes de compatibilité, le blocage est levé via la mise à jour des stratégies de groupe par le biais d’une nouvelle version de l’application dans le Windows Store. Les appareils qui exécutent l’application Microsoft teams se mettent automatiquement à jour vers une version de Windows 10 appropriée lors du redémarrage de la maintenance nocturne. Une version MSI est mise à la disposition des clients qui souhaitent gérer manuellement les mises à jour.  

> [!IMPORTANT]
> Pendant la période de validation, il est préférable de **ne pas** mettre à jour la version de Microsoft teams pour les périphériques de la version ultérieure de Windows 10. Cela inclut le remplacement des stratégies de groupe en place, l’utilisation de System Center ou d’autres services de gestion des appareils tiers. Ces problèmes peuvent entraîner des problèmes pour l’application Microsoft teams salle ou laisser des appareils inutilisables.  

Le tableau suivant indique les versions recommandées et prises en charge de Windows 10 qui ont été vérifiées pour prendre en charge Microsoft teams salles. Toutes les dates sont indiquées au format ISO 8601 : AAAA-MM-JJ.

|Version  |Date de disponibilité   |État du support de Microsoft teams   |Version d’application minimum de Microsoft teams | Build recommandée du système d’exploitation  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1909 |2019-11-12 |En cours de validation, <br/>Déconseillé|&#x2014; |&#x2014; |
| 1903 |2019-05-21 |Pris en charge <br/>Recommandation  |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Ignoré <br/>Déconseillé &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Pris en charge                             |4.1.22.0 |17134,191|
| 1709 |2018-01-18 |Non pris en charge                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non pris en charge                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 version 1809 est déconseillé en raison de problèmes de compatibilité détectés dans l’application Microsoft Teams. Ce problème particulier entraîne le démarrage de l’application Microsoft teams rooms après le redémarrage nocturne. Ce problème a été résolu dans la version 1903 de Windows 10.  

Lorsque vous utilisez une version prise en charge de Windows 10, vous obtiendrez toujours les dernières mises à jour de l’application pour l’application Microsoft teams salles.  

## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notes de publication de Microsoft teams](rooms-release-note.md)

[Plan pour les salles de Microsoft teams](rooms-plan.md)
