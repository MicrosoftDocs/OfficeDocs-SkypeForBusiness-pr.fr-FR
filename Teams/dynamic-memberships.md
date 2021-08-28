---
title: Présentation de l’appartenance dynamique pour les équipes
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment votre Microsoft Teams prend en charge les équipes associées Microsoft 365 groupes à l’aide de l’appartenance dynamique.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a18e2cbe1a34fe78f5e84b4df4ae9a95c46fd9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613633"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Microsoft Teams prend en charge les équipes associées Microsoft 365 groupes à l’aide *d’une appartenance dynamique.* L’appartenance dynamique permet de définir l’appartenance d’une équipe par une ou plusieurs règles qui vérifient certains attributs d’utilisateur dans Azure Active Directory (Azure AD). Les utilisateurs sont ajoutés ou supprimés automatiquement des équipes correctes à mesure que les attributs des utilisateurs changent ou que des utilisateurs rejoignent et quittent le client.

L’appartenance dynamique vous permet de configurer des équipes pour certains utilisateurs de votre organisation. Les scénarios possibles sont les suivants :
- Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les infirmières pour diffuser les communications. Ceci est particulièrement important si l’hôpital s’appuie sur des employés temporaires.
- Une université peut créer une équipe pour tous les enseignants d’une université en particulier, y compris un enseignant agrégé qui change fréquemment.
- Une compagnie aérienne souhaite créer une équipe pour chaque vol (par exemple, un mardi après-midi sans s’arrêter de Chicago à Atlanta) et supprimer automatiquement ou automatiquement une équipe de vol en modification fréquente, si nécessaire.

Cette fonctionnalité permet aux membres d’une équipe donnée de se mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance. Pour ce faire, Azure AD Premium P1 licences et [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) l’appartenance à une équipe peuvent être attribuées par un administrateur de client aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous utilisiez un client et un compte administrateur.

Microsoft Teams peuvent prendre de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils prennent effet dans le groupe Microsoft 365 d’une équipe.

Lors de l’utilisation d’équipes avec des groupes dynamiques :

- Les règles peuvent définir qui est membre d’une équipe, mais pas qui est propriétaire de l’équipe.
- Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.
- Teams clients n’autorisent pas la gestion des membres de l’équipe. Les options pour ajouter des membres, modifier les rôles de membre, envoyer et approuver des demandes d’adhésion et quitter l’équipe sont masquées.

Pour créer une équipe qui utilise [](/azure/active-directory/users-groups-roles/groups-create-rule) une appartenance dynamique, commencez par créer un groupe de Microsoft 365 dynamique, puis créez une équipe à partir [de ce groupe.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

Vous pouvez modifier une équipe existante pour avoir une appartenance dynamique. Voir [Modifier l’appartenance aux groupes statiques](/azure/active-directory/users-groups-roles/groups-change-type) en dynamique dans Azure Active Directory pour plus d’informations.

## <a name="related-topics"></a>Rubriques connexes

[Limites et spécifications de Microsoft Teams](limits-specifications-teams.md)

[Règles d’appartenance dynamique pour les groupes dans Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
