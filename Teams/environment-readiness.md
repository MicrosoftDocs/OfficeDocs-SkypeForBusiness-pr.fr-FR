---
title: Vérifier la préparation de votre environnement pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Découvrez quelles données que vous devez rechercher lors de la vérification de la préparation de votre environnement pour Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 057493f42a4bbfa012fb57c2394c372dfc25c9fc
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264827"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Vérifier la préparation de votre environnement pour Microsoft Teams
===========================================

La transition vers le cloud varie pour chaque organisation et l'état actuel peut affecter le fonctionnement de Teams.

Les établissements d’enseignement sont vivement recommandés de [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams. Synchronisation des données de l’école utilise les données de liste de votre école SIS pour créer automatiquement les classes et les groupes pour Teams Microsoft et d’autres applications.

Pour obtenir la meilleure expérience sur les équipes, votre organisation doit avoir déployé Exchange Online et SharePoint Online. Vous devez également vous assurer que votre environnement est prêt pour les équipes.  Reportez-vous à ces liens pour une assistance :

-   Si votre organisation n'a déployé aucune charge de travail Office 365, reportez-vous à l'article [Prise en main d'Office 365 pour les entreprises.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

-   Si votre organisation n'a pas ajouté ni configuré un domaine vérifié pour Office 365, reportez-vous à l'article [Vérifier votre domaine Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Si votre organisation n'a pas synchronisé les identités dans Azure Active Directory, reportez-vous à la page [Identity models and authentication in Microsoft Teams](identify-models-authentication.md) (Modèles d'identité et authentification dans Microsoft Teams).

-   Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md) (Interaction entre Exchange et Microsoft Teams).

-   Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).

- Si votre organisation est un établissement scolaire et que vous utilisez un étudiant informations système (SIS), [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams.

- Si votre organisation a un Skype local existant pour le déploiement de serveur d’entreprise (ou Lync Server), vous devez configurer Azure AD se connecter pour synchroniser votre annuaire local avec Office 365.  Pour plus d’informations, voir [configurer les Azure AD Connect pour les équipes et Skype pour les entreprises](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).