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
description: Découvrez comment Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 à l’aide de l’appartenance dynamique.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff6a71978873d723f39a534f876696a0def2f756
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562573"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 à l’aide de *l’appartenance dynamique*. L’appartenance dynamique permet à l’appartenance d’une équipe d’être définie par une ou plusieurs règles qui vérifient certains attributs utilisateur dans Azure Active Directory (Azure AD). Les utilisateurs sont automatiquement ajoutés ou supprimés aux équipes appropriées à mesure que les attributs utilisateur changent ou que les utilisateurs rejoignent et quittent le locataire.

Avec l’appartenance dynamique, vous pouvez configurer des équipes pour certaines cohortes d’utilisateurs de votre organisation. Les scénarios possibles sont les suivants :
- Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les chirurgiens afin de diffuser des communications. Cela est particulièrement important si l’hôpital s’appuie sur des employés temporaires.
- Une université peut créer une équipe pour toutes les facultés d’un collège particulier, y compris une faculté auxiliaire qui change fréquemment.
- Une compagnie aérienne souhaite créer une équipe pour chaque vol (par exemple, un mardi après-midi sans arrêt de Chicago à Atlanta) et faire en sorte qu’un équipage de conduite qui change fréquemment soit automatiquement affecté ou supprimé en fonction des besoins.

À l’aide de cette fonctionnalité, les membres d’une équipe donnée se mettent à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance. Pour ce faire, Azure AD Premium P1 les licences et l’appartenance à l’équipe peuvent être [attribuées par un administrateur client](/azure/active-directory/users-groups-roles/groups-dynamic-membership) aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous ayez un locataire et un compte d’administrateur.

Microsoft Teams peut prendre de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils entrent en vigueur dans le groupe Microsoft 365 pour une équipe.

Lorsque vous utilisez des équipes avec des groupes dynamiques :

- Les règles peuvent définir qui est membre de l’équipe, mais pas qui est propriétaire de l’équipe.
- Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.
- Les clients Teams n’autorisent pas la gestion des membres pour l’équipe. Les options permettant d’ajouter des membres, de modifier des rôles de membre, d’envoyer et d’approuver des demandes de jointure et de quitter l’équipe sont toutes masquées.

Pour créer une équipe qui utilise l’appartenance dynamique, commencez par [créer un groupe Microsoft 365 dynamique](/azure/active-directory/users-groups-roles/groups-create-rule) , puis [créez une équipe à partir de ce groupe](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

Vous pouvez modifier une équipe existante pour qu’elle ait une appartenance dynamique. Pour plus d’informations, consultez [Modifier l’appartenance à un groupe statique en mode dynamique dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) .

## <a name="related-topics"></a>Sujets associés

[Limites et spécifications de Microsoft Teams](limits-specifications-teams.md)

[Règles d’appartenance dynamique pour les groupes dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
