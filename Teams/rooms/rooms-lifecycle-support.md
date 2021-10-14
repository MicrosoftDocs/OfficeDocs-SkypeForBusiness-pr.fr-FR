---
title: Salles Microsoft Teams prise en charge de la version de l’application
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
ms.localizationpriority: medium
description: Découvrez la prise en charge du cycle de Salles Microsoft Teams, notamment la structure de support dynamique et ses phases.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e7a82d7643a925d5c997c9d6fe5661a421d47ab
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356422"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salles Microsoft Teams prise en charge de la version de l’application
 
L’Salles Microsoft Teams mise à jour est mise à jour tous les trimestres via le Windows Store. Une mise à jour hors bande peut être mise en place entre deux choses pour résoudre les problèmes urgents. Microsoft Teams L’application Room utilise un cycle de vie de produit persistant et seules la version actuelle et la dernière version de l’application sont pris en charge à un moment donné. L’Microsoft Teams Room regroupe une version spécifique de l’application Teams de bureau modifiée pour une utilisation de salle. L Teams de bureau est mise à jour toutes les deux semaines. En savoir plus sur le [Teams de mise à jour.](../teams-client-update.md) Cela signifie que salles Teams la version actuelle de l’application 1 peut prendre jusqu’à six mises à jour de l’application de bureau Teams. Par conséquent, nous vous recommandons de mettre à jour régulièrement l’application Teams Room vers la dernière version de l’application salles Teams. 

La structure de prise en charge salles Teams est dynamique et dépend de la disponibilité de la version la plus récente. Lorsque vous rencontrez une faute de code dans une version de l’application qui n’est pas la dernière, vous devez installer la dernière version pour recevoir un correctif.

Toutes les publication sont répertoriées dans les notes [Salles Microsoft Teams publication.](rooms-release-note.md)

> [!IMPORTANT]
> Lors de l’installation d’un nouvel appareil avec une version antérieure de l’application de salle Teams, il est recommandé de mettre à jour [l’application](manual-update.md) manuellement après la configuration du compte, avant de télécharger les mises à jour Windows automatiques. Cela garantit la mise à jour et la version du système d’exploitation en correbt sur votre appareil.  

## <a name="windows-10-release-support"></a>Windows 10 prise en charge de la publication

Salles Microsoft Teams requiert l’Windows 10 IoT Entreprise ou Windows 10 Entreprise s'Semi-Annual les options de service de canal. Les autres éditions Windows 10 ne sont pas pris en charge :

- Windows 10 Entreprise Éditions de canal de service à long terme (LTSB) / Canal de service à long terme
- Windows 10 Internet of Things (IoT) Enterprise éditions LTSB/LTSC
- toute autre édition de Windows par exemple, Windows 10 Professionnel édition Famille

De Windows 10 mises à jour de fonctionnalités ne sont pas immédiatement proposées Salles Microsoft Teams vos appareils. Il y a un délai délibéré de six mois ou plus après la date de disponibilité générale publiée sur la page Windows 10 [d’informations de](/windows/release-information/) publication. Ce moment est utilisé pour valider Windows 10 compatibilité de la publication pour l’application Salles Microsoft Teams, le matériel de l’appareil et les périphériques vidéo audio certifiés. La validation commence et se poursuit pendant le développement actif de chaque version majeure de Windows 10. Un temps supplémentaire est nécessaire pour vérifier que tous les fabricants d’appareils ont créé des images mises à jour pour leurs appareils et pour que Microsoft Teams certifie et teste ces images. Pendant la période de validation, l’application Salle Microsoft Teams utilise Windows de groupe Mise à jour pour les entreprises pour retarder Windows 10 mises à jour des fonctionnalités. [](/windows/deployment/update/waas-manage-updates-wufb) Une fois les problèmes de compatibilité trouvés et résolus, le blocage est levée via la mise à jour des stratégies de groupe via une nouvelle version d’application dans Windows store. Les périphériques qui exécutent l Salles Microsoft Teams appil sont automatiquement mis à jour vers une version appropriée Windows 10 le redémarrage de maintenance nocturne. Une version MSI est mise à la disposition des clients qui souhaitent gérer manuellement les mises à jour.  

> [!IMPORTANT]
> Pendant la période de validation,  les Salles Microsoft Teams ne doivent pas être mis à jour vers la prochaine version d’Windows 10 par quelque moyen que ce soit. Cela inclut le remplacement des stratégies de groupe en place, ou l’utilisation de System Center services de gestion des appareils tiers. Ces problèmes peuvent poser problème à l’application Salle Microsoft Teams ou laisser les appareils inutilisables.  

Le tableau suivant indique les versions recommandées et pris en charge des Windows 10 qui sont vérifiées pour prendre en charge Salles Microsoft Teams. Toutes les dates sont répertoriées au format ISO 8601 : AAAY-MM-JD.

|Version  |Date de disponibilité   |Salles Microsoft Teams d’assistance technique   |Salles Microsoft Teams Version minimale de l’application | Build du système d’exploitation recommandé  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Pris en charge, <br/>Recommandation|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |Ignoré, <br/> Non recommandé &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Pris en charge |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Non pris en charge  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Non pris en charge, <br/>Problèmes de compatibilité connus &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non pris en charge                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non pris en charge                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non pris en charge                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 version 2004 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l Salles Microsoft Teams application. Ce problème spécifique entraîne l’échec Salles Microsoft Teams’application de l’application après le redémarrage nocturne. 

&#x2781; Windows 10 version 1809 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l Salles Microsoft Teams application. Ce problème spécifique entraîne l’échec Salles Microsoft Teams’application de l’application après le redémarrage nocturne. Ce problème a été résolu dans Windows 10 version 1903.  

Lorsque vous utilisez une version d’Windows 10 prise en charge, vous obtenez toujours les dernières mises à jour des applications pour l Salles Microsoft Teams appeil.  


## <a name="related-topics"></a>Sujets associés

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salles Microsoft Teams notes de publication](rooms-release-note.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
