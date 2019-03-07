---
title: Problèmes connus de stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Liste actuelle des problèmes connus pour les stratégies de rétention Teams Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 411ef4bf12d55af0b913443219a00f3f56c7eba2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461187"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problèmes connus de stratégies de rétention dans Microsoft Teams

Les éléments suivants sont des problèmes pour les stratégies de rétention dans les équipes qui sont en cours suivis et analysés.

- Sous Choisissez les équipes dans la ligne d’emplacement de messages canal équipes, vous pouvez voir les équipes pas également Office 365 les groupes. Cela sera traité ultérieurement.

- Sous Choisir les utilisateurs dans la ligne emplacement équipes conversation, vous pouvez voir les invités et les utilisateurs non-mailbox. Stratégies de rétention ne sont pas destinés à définir pour les visiteurs et nous effectuons fonctionne pour les supprimer de la liste.

- Assistant de Cycle de vie Exchange (ELC) s’exécute tous les jours, mais il a un SLA de 7 jours. Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention les équipes à supprimer les éléments antérieurs à 60 jours, ces éléments peuvent conserver 67 jours. Ce n’est pas une situation nouvelle : elle suit le modèle Exchange. Bien sûr, dans la plupart des cas, il n’existe aucun délai.


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Étapes suivantes         |Documenter vos fonctionnalités de sécurité et de conformité requises.         |
