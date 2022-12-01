---
title: Présentation de l’appartenance dynamique pour les équipes
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment Microsoft Teams prend en charge les équipes associées à Microsoft 365 groupes à l’aide de l’appartenance dynamique.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c747fea2b33f2fd18b004e9a16a2302702ec59
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198726"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Microsoft Teams prend en charge les équipes associées à Microsoft 365 groupes à l’aide de *l’appartenance dynamique*. L’appartenance dynamique permet à l’appartenance d’une équipe d’être définie par une ou plusieurs règles qui vérifient certains attributs utilisateur dans Azure Active Directory (Azure AD). Les utilisateurs sont automatiquement ajoutés ou supprimés dans les équipes appropriées à mesure que les attributs utilisateur changent ou que les utilisateurs rejoignent et quittent le locataire.

Avec l’appartenance dynamique, vous pouvez configurer des équipes pour certaines cohortes d’utilisateurs de votre organisation. Les scénarios possibles sont les suivants :
- Un hôpital peut créer des équipes distinctes pour que les infirmières, les médecins et les chirurgiens diffusent des communications. Cela est particulièrement important si l’hôpital compte sur des employés temporaires.
- Une université peut créer une équipe pour toutes les facultés au sein d’un collège particulier, y compris une faculté auxiliaire qui change fréquemment.
- Une compagnie aérienne souhaite créer une équipe pour chaque vol (comme un mardi après-midi sans escale de Chicago à Atlanta) et avoir un équipage de conduite qui change fréquemment d’affectation ou de retrait automatiquement en fonction des besoins.

À l’aide de cette fonctionnalité, les membres d’une équipe donnée se mettent à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance. Pour ce faire, vous devez Azure AD Premium P1 licences et l’appartenance à l’équipe peuvent être [attribuées par un administrateur client](/azure/active-directory/users-groups-roles/groups-dynamic-membership) aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous ayez un locataire et un compte administrateur.

Microsoft Teams peut prendre entre quelques minutes et 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils entrent en vigueur dans le groupe Microsoft 365 pour une équipe.

Lors de l’utilisation d’équipes avec des groupes dynamiques :

- Les règles peuvent définir qui est un membre de l’équipe, mais pas qui est un propriétaire d’équipe.
- Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.
- Les clients Teams n’autorisent pas la gestion des membres pour l’équipe. Les options permettant d’ajouter des membres, de modifier les rôles de membre, d’envoyer et d’approuver des demandes de participation et de quitter l’équipe sont toutes masquées.

Pour créer une équipe qui utilise l’appartenance dynamique, commencez par [créer un groupe dynamique Microsoft 365](/azure/active-directory/users-groups-roles/groups-create-rule), puis [créez une équipe à partir de ce groupe](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

Vous pouvez modifier une équipe existante pour qu’elle ait une appartenance dynamique. Pour plus d’informations [, consultez Modifier l’appartenance à un groupe statique en dynamique dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) .

## <a name="related-topics"></a>Rubriques connexes

[Limites et spécifications de Microsoft Teams](limits-specifications-teams.md)

[Règles d’appartenance dynamique pour les groupes dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
