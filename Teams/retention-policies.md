---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Découvrez comment les stratégies de rétention et comment les gérer dans les équipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3c253569f642a8833d9bfad6677fe1a17624447
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205122"
---
# <a name="retention-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams

Conversations équipes sont persistantes et conservés indéfiniment par défaut. Avec l’introduction des stratégies de rétention, les administrateurs peuvent configurer des stratégies de rétention (conservation et suppression) dans le centre de conformité de & sécurité pour les messages de conversation et de canal équipes. Cela permet aux organisations de conserver les données de conformité (à savoir, stratégie de conservation) pour une période spécifique ou de vous débarrasser de données (à savoir, stratégie de suppression) s’il est considéré comme un passif après une période spécifique. Stratégies de rétention équipes Assurez-vous que lorsque vous supprimez des données, il est supprimé de tous les emplacements de stockage des données permanentes dans le service d’équipes. 

Pour gérer les stratégies de rétention équipes, utilisez les paramètres et les applets de commande dans le centre de conformité sous **La gouvernance des données**de & Office 365 sécurité > **rétention**.

Stratégies de rétention équipes prennent en charge : 
    
- Conservation : Conserver les données d’équipes pour une durée spécifiée et ne fait rien
- Conservation et supprimer puis : conserver les données des équipes pendant une durée spécifiée, puis supprimer
- Suppression : Supprimer des données d’équipes après une durée spécifiée

Stratégies de rétention équipes ne prennent pas encore charge :

- Stratégies de rétention avancées ne s’appliquent pas conversation équipes et emplacements de message de canal équipes
- Durée de moins de 30 jours

Administrateurs peuvent définir des stratégies de rétention distinct de salles de conversation privées équipes (1:1 ou 1:Many conversations) et les messages de canal équipes. Dans de nombreux cas, aux organisations de considérer les données de conversation privée comme un passif que les messages de canal, qui sont généralement plus conversations liés au projet. Configurer ces stratégies dans le centre de conformité, & de sécurité **la gouvernance des données** > **rétention**. Activer de **messages du canal équipes** et **équipes conversations** , puis définissez les stratégies de rétention pour ces emplacements (également indiqués dans le diagramme ci-dessous). 

Lorsque vous activez des **messages du canal équipes**, vous pouvez spécifier les équipes auxquels cette stratégie s’applique. Par exemple, pour les équipes X, Y et Z, l’administrateur peut définir les stratégies de suppression pendant 1 an (en sélectionnant individuellement ces équipes) et appliquer une stratégie de suppression de 3 ans pour le reste des équipes. 

Faire la même chose pour **les équipes conversations** sélectionner des utilisateurs spécifiques et appliquer des stratégies de rétention unique. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Les emplacements de message de canal équipes et les emplacements de conversations équipes adresse uniquement les conversations équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres utilisateur et de groupe). Les messages sont supprimés de tous les emplacements de stockage appropriées, à savoir les boîtes aux lettres, Network substrate et service de conversation. 
> 
> Pour gérer les stratégies de rétention pour les fichiers d’équipes, qui sont stockés dans OneDrive pour l’activité et de SharePoint, utilisez les stratégies de rétention.

Par leur conception, les stratégies de suppression pour les fichiers d’équipes sont configurés par le biais de SharePoint Online et OneDrive pour des sites. Par conséquent, il est possible qu’une stratégie peut supprimer un fichier référencé dans un message de conversation ou canal équipes avant la suppression d’obtient ces messages. Dans ce cas, le fichier s’afficheront toujours dans le message d’équipes, mais si vous cliquez sur le fichier, vous obtiendrez une erreur « Fichier introuvable » (Cela peut également se produire en l’absence d’une stratégie, si un utilisateur supprime manuellement un fichier à partir de SharePoint Online ou OneDrive entreprise).

Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, consultez [vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
