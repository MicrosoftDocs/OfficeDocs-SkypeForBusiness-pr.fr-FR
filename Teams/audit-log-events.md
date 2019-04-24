---
title: Rechercher des événements Microsoft Teams dans le journal d'audit
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Découvrez comment récupérer des données Microsoft Teams à partir du journal d'audit d’Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194991"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le journal d’audit peut vous aider à vérifier des activités spécifiques dans les services Office 365. Pour Teams, voici certaines des activités qui sont vérifiées :

-   Création d'une équipe

-   Suppression d'une équipe

-   Ajout d'un canal

-   Modification d'un paramètre

Pour la liste complète des activités qui sont vérifiées dans Office 365, consultez la rubrique [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité et de conformité d'Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Activer l’audit dans Teams

Avant d’examiner les données d’audit, vous devez activer l’audit de la **sécurité & centre de conformité**premier (https://protection.office.com). Pour obtenir de l’aide sur la fonctionnalité d’audit, consultez la rubrique [Activer ou désactiver la recherche du journal d’audit d’Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).


> [!IMPORTANT]
> Les données d'audit sont disponibles uniquement à partir du point d'activation de la fonctionnalité d'audit.



## <a name="retrieve-teams-data-from-the-audit-log"></a>Récupérer des données Teams à partir du journal d'audit

1.  Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous **Recherche et examen**, sélectionnez **Recherche du journal d'audit**.![Capture d'écran de la page de recherche du journal d'audit du Centre de sécurité et de conformité.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.

3.  Pour une analyse plus approfondie, exportez les résultats dans Excel.


> [!IMPORTANT]
> Les données d’audit sont visibles dans le journal d’audit si la fonctionnalité d’audit est activée.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Vidéo : Conseil technique : utilisation de la recherche du journal d’audit dans Teams

Rejoignez Ansuman Acharya, gestionnaire de programmes pour Teams, qui explique comment effectuer une recherche du journal d’audit pour Teams dans la Centre de sécurité et de conformité d’Office 365. 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






