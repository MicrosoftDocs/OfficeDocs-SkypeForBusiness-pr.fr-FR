---
title: Prise en charge des versions
ms.author: dstrome
author: dstrome
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
description: Découvrez la prise en charge du cycle de vie des salles Microsoft Teams, notamment la structure de support dynamique et ses phases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e22bf9759920a5b4233fab9a6f6169f3a1153f0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117442"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Prise en charge de la version de l’application Salles Microsoft Teams
 
L’application Salles Microsoft Teams est mise à jour plusieurs fois par an. Chaque mise à jour prise en charge pendant douze (12) mois à partir de sa date de publication générale (GA). Le support technique est fourni pour l’ensemble des douze (12) mois. Toutefois, la structure de prise en charge est dynamique, avec deux phases distinctes qui dépendent de la disponibilité de la dernière version :

- **Phase de maintenance et de mises à jour critiques** \- Lorsque vous exécutez la dernière version de l’application Salles Microsoft Teams, vous recevez des mises à jour régulières qui contiennent des mises à jour de sécurité *et* de maintenance.

- **Phase uniquement des mises à jour de sécurité** \- Lors de la publication d’une nouvelle version de l’application Salles  Microsoft Teams, les versions antérieures de l’application disposent d’un niveau de support réduit avec les mises à jour de sécurité uniquement pour le reste du cycle de vie de douze (12) mois.

> [!NOTE]
> La dernière version est toujours dans la phase de maintenance et de mise à jour critique. Lorsque vous rencontrez une défaillance de code qui justifie une mise à jour critique, vous devez également avoir installé la dernière version pour recevoir un correctif. Toutes les autres versions pris en charge ne seront éligibles qu’à la réception des mises à jour de sécurité.

Tout le support prend fin après le cycle de vie de douze (12) mois expiré pour une version ou si plus de deux mises à jour ont été publiées depuis. Ensuite, les clients doivent mettre à jour vers une version prise en charge.

Toutes les publication sont répertoriées dans les notes de publication de [salles Microsoft Teams.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Prise en charge de Windows 10 Release

Les salles Microsoft Teams nécessitent les SDK Windows 10 IoT Entreprise ou Windows 10 Entreprise sous Semi-Annual options de service de canal. Ces autres éditions de Windows 10 ne sont pas prise en charge :

- LTSB (Enterprise Long-Term Servicing Branch) / Canal de maintenance à long terme (LTSC) de Windows 10 Entreprise
- Éditions Internet des objets (IoT) Entreprise LTSB/LTSC de Windows 10
- toute autre édition de Windows, comme Windows 10 Professionnel ou Famille

Une mise à jour des fonctionnalités de Windows 10 n’est pas proposée ou mise à jour immédiatement sur les appareils Microsoft Teams Rooms. Un délai délibéré de six mois après la date de disponibilité générale publiée sur la page d’informations de publication de [Windows 10.](/windows/release-information/) Le délai est utilisé pour valider la compatibilité de la version de Windows 10 pour l’application Salles Microsoft Teams, le matériel de l’appareil et les périphériques vidéo audio certifiés. La validation commence et se poursuit pendant le développement actif de chaque version majeure de Windows 10. Un temps supplémentaire est nécessaire pour vérifier que tous les fabricants d’appareils ont créé des images mises à jour pour leurs appareils et que Microsoft Teams peut certifier et tester ces images. Pendant la période de validation, l’application Salle Microsoft Teams utilise des stratégies de groupe  [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) pour retarder les mises à jour des fonctionnalités de Windows 10. Une fois les problèmes de compatibilité trouvés et résolus, le blocage est levée via la mise à jour des stratégies de groupe via une nouvelle version d’application dans le Windows Store. Les appareils qui exécutent l’application Salles Microsoft Teams sont automatiquement mis à jour vers une version Windows 10 appropriée pendant le redémarrage de maintenance nocturne. Une version MSI est mise à la disposition des clients qui souhaitent gérer manuellement les mises à jour.  

> [!IMPORTANT]
> Pendant la période de validation,  les appareils salles Microsoft Teams ne doivent pas être mis à jour vers la prochaine version de Windows 10 par quelque moyen que ce soit. Cela inclut le remplacement des stratégies de groupe en place, ou l’utilisation de System Center ou d’autres services tiers de gestion des appareils. Tout cela peut entraîner des problèmes pour l’application Salle Microsoft Teams ou laisser les appareils inutilisables.  

Le tableau suivant indique les versions recommandées et pris en charge de Windows 10 qui sont vérifiées pour prendre en charge les salles Microsoft Teams. Toutes les dates sont répertoriées au format ISO 8601 : AAAY-MM-JD.

|Version  |Date de disponibilité   |État du support des salles Microsoft Teams   |Version minimale de l’application Salles Microsoft Teams | Build du système d’exploitation recommandé  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |En cours de validation, <br/>Pas encore pris en charge|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Ignoré, <br/> Non recommandé|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Pris en charge, <br/>Recommandation |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Pris en charge  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |Non pris en charge, <br/>Problèmes de compatibilité connus &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non pris en charge                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non pris en charge                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non pris en charge                         |&#x2014; |&#x2014; |

&#x2780; la version 1809 de Windows 10 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l’application Salles Microsoft Teams. Ce problème spécifique entraîne l’échec du démarrage de l’application Salles Microsoft Teams après le redémarrage nocturne. Ce problème a été résolu dans Windows 10 version 1903.  

&#x2781; la version 2004 de Windows 10 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l’application Salles Microsoft Teams. Ce problème spécifique entraîne l’échec du démarrage de l’application Salles Microsoft Teams après le redémarrage nocturne. 

Lorsque vous utilisez une version prise en charge de Windows 10, vous obtenez toujours les dernières mises à jour des applications pour l’application Salles Microsoft Teams.  

## <a name="related-topics"></a>Rubriques connexes

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Notes de publication de salles Microsoft Teams](rooms-release-note.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)