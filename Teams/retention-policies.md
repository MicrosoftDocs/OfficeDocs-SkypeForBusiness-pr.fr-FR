---
title: Stratégies de conservation dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Apprenez-en davantage sur les stratégies de rétention et la façon de les gérer dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793520"
---
# <a name="retention-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams

Les conversations d’équipes sont permanentes et conservées définitivement par défaut. Avec la présentation des stratégies de rétention, les administrateurs peuvent configurer des stratégies de rétention (conservation et suppression) dans le centre de sécurité & conformité pour les conversations et les messages de canal. Cela permet aux organisations de conserver les données relatives à la conformité (politique de conservation) pour une période donnée ou d’éliminer les données (c’est-à-dire, la politique de suppression) si elle est considérée comme une responsabilité après une période donnée. Les stratégies de rétention de teams garantissent que, lorsque vous supprimez des données, les emplacements de stockage des données permanentes du service équipes sont supprimés.

> [!NOTE]
> Nous ne prenons pas encore en charge la configuration de la conservation des messages de canal privé. La conservation des fichiers partagés dans des canaux privés est prise en charge.

Pour gérer les stratégies de rétention aux équipes, utilisez les paramètres et les applets de la section sécurité du centre de sécurité & conformité d’Office 365 sous**rétention**de la **gouvernance** > des informations.

Les stratégies de rétention teams prennent en charge : 
    
- Préservation : conserver les données d’équipe pour une durée spécifiée et ne rien faire
- Préservation et suppression : conservez les données d’équipe pour une durée spécifiée, puis supprimez
- Suppression : supprimer les données de l’équipe après une durée spécifiée

Les stratégies de rétention Teams ne sont pas encore prises en charge :

- Les stratégies de rétention avancées ne s’appliquent pas aux emplacements discussions et équipes des messages de canal
- Durée de moins de 30 jours

Les administrateurs peuvent configurer des stratégies de rétention distinctes pour les discussions privées d’équipes (1:1 ou 1 : nombreux messages de discussion) et équipes de canal. Dans de nombreux cas, une entreprise considère qu’il s’agit d’une plus grande responsabilité par le biais de messages de canal, qui sont généralement davantage des conversations relatives au projet. Définissez ces stratégies dans le centre de sécurité & conformité, **** > **rétention**de la gouvernance des informations. Activez les **messages du canal équipes** et les **discussions d’équipe** , puis définissez les stratégies de rétention pour ces emplacements (également illustrées ci-dessous). 

Lorsque vous activez **les messages de canal teams**, vous pouvez spécifier les équipes auxquelles s’applique cette stratégie. Par exemple, pour les équipes X, Y et Z, l’administrateur peut définir les stratégies de suppression pour 1 an (en les sélectionnant individuellement) et appliquer une stratégie de suppression de 3 ans au reste des équipes. 

Vous pouvez effectuer la même opération pour les **discussions d’équipe** en sélectionnant des utilisateurs spécifiques et en appliquant des stratégies de rétention uniques. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Les emplacements des messages du canal équipes et des discussions d’équipes sont uniquement conformes aux conversations d’équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres d’utilisateur et de groupe). Les messages sont supprimés des emplacements de stockage appropriés, à savoir les boîtes aux lettres, le substrat et le service Chat. 
> 
> Pour gérer les stratégies de rétention pour les fichiers teams stockés dans OneDrive entreprise et SharePoint, utilisez leurs stratégies de rétention.

Par conception, les stratégies de suppression des fichiers d’équipe sont configurées par le biais des emplacements SharePoint Online et OneDrive entreprise. Par conséquent, il est possible qu’une stratégie supprime un fichier référencé dans une conversation ou un message de canal teams avant que ces messages soient supprimés. Dans ce cas, le fichier s’affichera toujours dans le message Teams, mais si vous cliquez sur le fichier, vous recevez un message d’erreur « fichier introuvable » (cela peut également se produire en l’absence d’une stratégie, si une personne a supprimé manuellement un fichier à partir de SharePoint Online ou OneDrive entreprise).

Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, voir [vue d’ensemble des stratégies de](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)rétention.
 
