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
ms.openlocfilehash: 7ecfd878b5d8aa22a19b4b2831c04a73e0d8911e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607027"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Salles Microsoft Teams prise en charge de la version de l’application
 
L Salles Microsoft Teams appil est mis à jour plusieurs fois par an. Chaque mise à jour est prise en charge pendant douze (12) mois à partir de sa date de publication générale (GA). Le support technique est fourni pour l’ensemble des douze (12) mois. Toutefois, la structure de prise en charge est dynamique, avec deux phases distinctes qui dépendent de la disponibilité de la dernière version :

- **Phase de maintenance** et de mise à jour critique : lorsque vous exécutez la dernière version de l’application Salles Microsoft Teams, vous recevez des mises à jour régulières qui contiennent des mises à jour de sécurité *et* de service.

- Phase uniquement des mises à jour de sécurité : lors de la publication d’une nouvelle  version de l’application Salles Microsoft Teams, les versions **antérieures** de l’application ont un niveau de support réduit avec les mises à jour de sécurité uniquement pour le reste du cycle de vie de douze (12) mois.

> [!NOTE]
> La dernière version est toujours dans la phase de maintenance et de mise à jour critique. Si vous rencontrez une défaillance de code qui justifie une mise à jour critique, vous devez également avoir installé la dernière version pour recevoir un correctif. Toutes les autres versions pris en charge ne seront éligibles qu’à la réception des mises à jour de sécurité.

Tout le support prend fin après le cycle de vie de douze (12) mois expiré pour une version ou si plus de deux mises à jour ont été publiées depuis. Ensuite, les clients doivent mettre à jour vers une version prise en charge.

Toutes les publication sont répertoriées dans les notes [Salles Microsoft Teams publication.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Windows 10 prise en charge de la publication

Salles Microsoft Teams requiert l’Windows 10 IoT Entreprise ou Windows 10 Entreprise s'Semi-Annual les options de maintenance de canal. Les autres éditions Windows 10 ne sont pas pris en charge :

- Windows 10 Entreprise Éditions de canal de service à long terme (LTSB) / Canal de service à long terme
- Windows 10 Internet of Things (IoT) Enterprise éditions LTSB/LTSC
- toute autre édition de Windows par exemple, Windows 10 Professionnel édition Famille

Les Windows 10 de fonctionnalités nouvelles ne sont pas immédiatement proposées sur Salles Microsoft Teams appareils mobiles. Un délai délibéré de six mois après la date de disponibilité générale publiée sur la page [Windows 10 d’informations de](/windows/release-information/) publication. Le délai est utilisé pour valider la compatibilité Windows 10 publication pour l’application Salles Microsoft Teams, le matériel de l’appareil et les périphériques audio vidéo certifiés. La validation commence et se poursuit pendant le développement actif de chaque version majeure de Windows 10. Un temps supplémentaire est nécessaire pour vérifier que tous les fabricants d’appareils ont créé des images mises à jour pour leurs appareils et pour que Microsoft Teams certifie et teste ces images. Pendant la période de validation, l’application Salle Microsoft Teams utilise Windows de groupe Mise à jour pour les entreprises pour retarder Windows 10 mises à jour des fonctionnalités. [](/windows/deployment/update/waas-manage-updates-wufb) Une fois les problèmes de compatibilité trouvés et résolus, le blocage est levée via la mise à jour des stratégies de groupe via une nouvelle version d’application dans Windows store. Les appareils qui exécutent l Salles Microsoft Teams appil sont automatiquement mis à jour vers une version appropriée Windows 10 le redémarrage de maintenance nocturne. Une version MSI est mise à la disposition des clients qui souhaitent gérer manuellement les mises à jour.  

> [!IMPORTANT]
> Pendant la période de validation,  les Salles Microsoft Teams ne doivent pas être mis à jour vers la prochaine version d’Windows 10 par quelque moyen que ce soit. Cela inclut le remplacement des stratégies de groupe en place, ou l’utilisation de System Center services de gestion des appareils tiers. Ces problèmes peuvent poser problème à l’application Salle Microsoft Teams ou laisser les appareils inutilisables.  

Le tableau suivant indique les versions recommandées et pris en charge des Windows 10 qui sont vérifiées pour prendre en charge Salles Microsoft Teams. Toutes les dates sont répertoriées au format ISO 8601 : AAAY-MM-JD.

|Version  |Date de disponibilité   |Salles Microsoft Teams d’assistance technique   |Salles Microsoft Teams Version minimale de l’application | Build du système d’exploitation recommandé  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Pris en charge, <br/>Recommandation|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |Ignoré, <br/> Non recommandé &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Pris en charge |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Non pris en charge  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Non pris en charge, <br/>Problèmes de compatibilité connus &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non pris en charge                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non pris en charge                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non pris en charge                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 version 2004 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l Salles Microsoft Teams application. Ce problème spécifique entraîne l’échec Salles Microsoft Teams’application de l’application après le redémarrage nocturne. 

&#x2781; Windows 10 version 1809 n’est pas recommandée en raison de problèmes de compatibilité trouvés avec l Salles Microsoft Teams application. Ce problème spécifique entraîne l’échec Salles Microsoft Teams’application de l’application après le redémarrage nocturne. Ce problème a été résolu dans Windows 10 version 1903.  

Lorsque vous utilisez une version prise en charge de Windows 10, vous obtenez toujours les dernières mises à jour des applications pour l Salles Microsoft Teams appeil.  

> [!IMPORTANT]
> La Windows 10 jour 20H2 n’est pas encore disponible pour les appareils mobiles salles Teams suivants en raison de problèmes de compatibilité. Les MXT de l’appareil travaillent à la résolution de ces problèmes dès que possible. Windows 10 20H2 ne sera pas proposé sur ces appareils. Ne mettez pas ces appareils à jour manuellement à 20H2 en remplacement des objets de stratégie de groupe ou de gestion des appareils mobiles. 
> 
> Les appareils avec des problèmes d’incompatibilité sont les :
> 
> - La UC-Engine(version/date BIOS) contient « KYSKLI » - indiquant un crâne Canyon BIOS) 

## <a name="related-topics"></a>Rubriques connexes

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Salles Microsoft Teams notes de publication](rooms-release-note.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)
