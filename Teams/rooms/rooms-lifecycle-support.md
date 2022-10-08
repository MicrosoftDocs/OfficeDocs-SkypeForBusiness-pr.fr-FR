---
title: prise en charge des versions d’application Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Découvrez la prise en charge du cycle de vie des Salles Microsoft Teams, notamment la structure de support dynamique et ses phases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9025500bc8aff6ddded71df29b9280d964763bdc
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138477"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>prise en charge des versions d’application Salles Microsoft Teams
 
L’application Salles Microsoft Teams obtient des mises à jour via le Windows Store. L’application utilise un cycle de vie de produit persistant et seule la version actuelle et la version la plus récente de l’application sont prises en charge à un moment donné. L’application regroupe une version spécifique de l’application de bureau Teams qui est modifiée pour une utilisation en salle. L’application de bureau Teams est mise à jour toutes les deux semaines, tandis que l’application salles Teams est moins fréquemment mise à jour. Cela signifie salles Teams version actuelle de l’application 1 peut être mise à jour jusqu’à six mises à jour d’application de bureau Teams, il est donc recommandé de maintenir l’application salles Teams mise à jour vers la dernière version à tout moment. En savoir plus sur le [processus de mise à jour teams](../teams-client-update.md).

La structure de prise en charge de salles Teams est dynamique et dépend de la disponibilité de la dernière version. Lorsque vous rencontrez un défaut de code dans une version de l’application qui n’est pas la plus récente, vous devez installer la dernière version pour recevoir un correctif.

Toutes les versions sont répertoriées dans les [notes de publication Salles Microsoft Teams](rooms-release-note.md).

> [!IMPORTANT]
> Lors de l’installation d’un nouvel appareil avec une version antérieure de l’application salle Teams, il est recommandé de [mettre à jour manuellement l’application](manual-update.md) après avoir défini le compte, avant de télécharger les mises à jour Windows. Cela garantit que la version correcte du système d’exploitation et les mises à jour Windows sont installées sur votre appareil.  

## <a name="windows-10-release-support"></a>prise en charge des versions Windows 10

Salles Microsoft Teams nécessite les références SKU Windows 10 IoT Entreprise ou Windows 10 Entreprise sous Semi-Annual options de maintenance du canal. Ces autres éditions Windows 10 ne sont pas prises en charge :

- Windows 10 Entreprise éditions LTSB (Long-Term Servicing Branch) /LTSC (Long Term Servicing Channel)
- Windows 10 éditions De l’Internet des objets (IoT) Enterprise LTSB /LTSC
- toute autre édition de Windows telle que Windows 10 Professionnel ou Home

Les nouvelles mises à jour de fonctionnalités Windows 10 ne sont pas proposées immédiatement sur Salles Microsoft Teams appareils. Il existe un délai intentionnel pouvant aller jusqu’à six mois après la date de disponibilité générale publiée sur la page [d’informations de mise en production Windows 10](/windows/release-information/). Cette heure est utilisée pour valider Windows 10 compatibilité des versions pour l’application Salles Microsoft Teams, le matériel de l’appareil et les périphériques vidéo audio certifiés. La validation commence et se poursuit pendant le développement actif de chaque version majeure de Windows 10. Un délai supplémentaire est nécessaire pour vérifier que tous les fabricants d’appareils ont créé des images mises à jour pour leurs appareils, et pour que Microsoft certifie et teste ces images. Pendant la période de validation, l’application Salles Microsoft Teams utilise [des stratégies de groupe Windows Update for Business pour](/windows/deployment/update/waas-manage-updates-wufb) retarder Windows 10 mises à jour des fonctionnalités. Une fois les problèmes de compatibilité détectés et résolus, le bloc est levé via la mise à jour des stratégies de groupe via une nouvelle version d’application dans le Windows Store. Les appareils qui exécutent l’application Salles Microsoft Teams sont automatiquement mis à jour vers une version Windows 10 appropriée pendant le redémarrage de maintenance nocturne. Une version MSI est mise à la disposition des clients qui doivent gérer manuellement les mises à jour.  

> [!IMPORTANT]
> Pendant la période de validation, Salles Microsoft Teams appareils **ne doivent pas** être mis à jour vers la prochaine version de Windows 10 par aucun moyen. Cela inclut la substitution des stratégies de groupe en place, ou l’utilisation de System Center ou d’autres services de gestion d’appareils tiers. Tout cela peut entraîner des problèmes pour l’application Salles Microsoft Teams ou laisser les appareils inutilisables.  

Le tableau suivant présente les versions recommandées et prises en charge des Windows 10 qui sont vérifiées pour prendre en charge Salles Microsoft Teams. Toutes les dates sont répertoriées au format ISO 8601 : AAAA-MM-JJ.

| Version | Date de disponibilité | état du support Salles Microsoft Teams                    | Salles Microsoft Teams version minimale de l’application | Build de système d’exploitation recommandée |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | Soutenu<br>Recommandation                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | Pris en charge                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | Non pris en charge, <br/>Problèmes de compatibilité connus &#x2780;| &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |
| 1903    | 2019-05-21        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | Non pris en charge, <br/>Problèmes de compatibilité connus &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | Non pris en charge                                           | &#x2014;                                          | &#x2014;             |

&#x2780; Windows 10 version 2004 n’est pas recommandée en raison de problèmes de compatibilité détectés avec l’application Salles Microsoft Teams. Ce problème spécifique entraîne l’échec du démarrage de l’application Salles Microsoft Teams après le redémarrage nocturne.

&#x2781; Windows 10 version 1809 n’est pas recommandée en raison de problèmes de compatibilité rencontrés avec l’application Salles Microsoft Teams. Ce problème spécifique entraîne l’échec du démarrage de l’application Salles Microsoft Teams après le redémarrage nocturne. Ce problème a été résolu dans Windows 10 version 1903.  

Lorsque vous utilisez une version prise en charge de Windows 10, vous obtenez toujours les dernières mises à jour d’application pour l’application Salles Microsoft Teams.  


## <a name="related-topics"></a>Rubriques connexes

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salles Microsoft Teams notes de publication](rooms-release-note.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
