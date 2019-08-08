---
title: Vérifier la préparation de votre environnement pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Découvrez quelles données que vous devez rechercher lors de la vérification de la préparation de votre environnement pour Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c0609efd8ac0286857b44996939378e57ce2702f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234920"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Vérifier la préparation de votre environnement pour Microsoft Teams
===========================================

La transition vers le cloud varie pour chaque organisation et l'état actuel peut affecter le fonctionnement de Teams.

Les établissements d’enseignement sont fortement encouragés à [déployer School Data Sync](https://docs.microsoft.com/schooldatasync/) avant le déploiement de Microsoft Teams. School Data Sync utilise les données de la liste du SIS de votre établissement scolaire pour créer automatiquement des classes et des groupes pour Microsoft teams et d’autres applications.

Pour tirer le meilleur parti de teams, votre organisation doit avoir déployé Exchange Online et SharePoint Online. Vous devez également vous assurer que votre environnement actuel est prêt pour Teams.  Pour obtenir de l’aide, consultez les liens suivants:

-   Si votre organisation n'a déployé aucune charge de travail Office 365, reportez-vous à l'article [Prise en main d'Office 365 pour les entreprises.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

-   Si votre organisation n'a pas ajouté ni configuré un domaine vérifié pour Office 365, reportez-vous à l'article [Vérifier votre domaine Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Si votre organisation n'a pas synchronisé les identités dans Azure Active Directory, reportez-vous à la page [Identity models and authentication in Microsoft Teams](identify-models-authentication.md) (Modèles d'identité et authentification dans Microsoft Teams).

-   Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md) (Interaction entre Exchange et Microsoft Teams).

-   Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).

- Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, vous devez [déployer School Data Sync](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams.

- Si votre organisation dispose d’un déploiement Skype entreprise Server (ou Lync Server) local existant, vous devez configurer Azure AD Connect pour synchroniser votre annuaire local avec Office 365.  Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).