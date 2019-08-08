---
title: Problèmes connus pour les stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Liste actuelle des problèmes connus pour les stratégies de rétention de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b13fc5347338b28c877b224f758c79513e379391
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243607"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problèmes connus pour les stratégies de rétention dans Microsoft Teams

Vous trouverez ci-après des problèmes connus liés aux stratégies de rétention dans les équipes qui sont suivies et examinées.

- Sous choisir des équipes dans la ligne d’emplacement des messages de canal Teams, vous pouvez voir les groupes Office 365 qui ne sont pas également équipes. Ce problème sera résolu dans le futur.

- Sous choisir les utilisateurs dans la ligne d’emplacement de conversation de l’équipe, il est possible que les utilisateurs invités et non-boîte aux lettres apparaissent. Les stratégies de rétention ne sont pas destinées à être définies pour les invités et nous travaillons à la suppression de celles-ci dans la liste.

- L’Assistant ELC (Exchange Life cycle Assistant) s’exécute quotidiennement, mais il dispose d’un SLA de 7 jours. Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention teams pour supprimer des éléments de plus de 60 jours, ces éléments peuvent persister pendant 67 jours maximum. Ce n’est pas une nouvelle situation: elle suit le modèle Exchange. Dans la plupart des cas, il n’y a aucun retard.


| | | |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône représentant les étapes suivantes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Étapes suivantes         |Documentez les fonctionnalités de sécurité et de conformité requises.         |
