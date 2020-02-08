---
title: Présentation de l’appartenance dynamique pour les équipes
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: En savoir plus sur l’appartenance aux équipes dynamiques basée sur AAD.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44b7a87a003b59543c37feb278462e839d83bd1e
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863305"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Microsoft teams prend en charge les équipes associées aux groupes Office 365 à l’aide de l' *appartenance dynamique*. L’appartenance au groupe dynamique permet de définir l’appartenance d’une équipe à une ou plusieurs règles qui recherchent certains attributs d’utilisateur dans Azure Active Directory (Azure AD). Les utilisateurs sont ajoutés ou supprimés automatiquement aux équipes appropriées en tant qu’attributs utilisateur, mais ils rejoignent et quittent le client.

L’appartenance dynamique vous permet de configurer des équipes pour certaines cohortes d’utilisateurs au sein de votre organisation. Les scénarios possibles sont les suivants :
- Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les chirurgiens en communication de diffusion. Cela est particulièrement important si l’hôpital repose sur des employés temporaires.
- Une université peut créer une équipe pour toutes les universités au sein d’un collège particulier, y compris des enseignants qui changent fréquemment.
- Une compagnie aérienne veut créer une équipe pour chaque version d’évaluation (par exemple, un mardi de l’après-midi sans arrêt de Chicago vers Atlanta) et avoir modifié automatiquement l’équipe de volée ou supprimée en conséquence.

Cette fonctionnalité permet aux membres d’une équipe donnée de mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance. Pour cela, il est nécessaire d’affecter des licences d’Azure AD Premium P1 et des membres d’une équipe à l' [aide d’un administrateur client](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) aux propriétés Azure AD de chaque utilisateur, dans la mesure où vous disposez d’un client et d’un compte d’administrateur.

Microsoft Teams ne doit compter que de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamique une fois qu’ils ont été appliqués dans le groupe Office 365 d’une équipe.

> [!NOTE]
> - Les règles peuvent définir qui est membre d’une équipe, sans qui est le propriétaire de l’équipe.
> - Voir [limites et spécifications de Microsoft teams](limits-specifications-teams.md) pour les limites actuelles relatives aux tailles d’équipes et de canaux.
> - Les propriétaires ne seront pas en mesure d’ajouter ou de supprimer des utilisateurs en tant que membres de l’équipe, car ils sont définis par des règles de groupe dynamique.
> - Les membres ne seront pas en mesure de laisser des équipes sauvegardées par des groupes dynamiques.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Création et gestion d’un groupe Office 365 avec appartenance dynamique
Lorsque vous êtes connecté en tant qu’administrateur client, suivez les instructions de la procédure de [création d’un groupe dynamique et vérification](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)de l’État. Le cas échéant, voir [règles d’appartenance dynamique pour les groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Créer une équipe à l’aide de votre groupe O365

Autorisez désormais le temps nécessaire au changement d’appartenance pour que les modifications soient prises en compte, puis créez une nouvelle équipe comme décrit dans [améliorer les groupes Office 365 existants avec Microsoft teams](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Appliquer une appartenance dynamique à une équipe existante

Vous pouvez également prendre une équipe existante et la modifier pour qu’elle dispose d’une appartenance dynamique, comme décrit dans la rubrique [changer l’appartenance au groupe statique sur dynamique dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Modifications du comportement du client

Une fois l’appartenance dynamique activée pour une équipe, les clients teams n’autorisent plus la gestion des membres de l’équipe. Options permettant d’ajouter des membres, de modifier les rôles des membres, d’envoyer et d’approuver des demandes de jointure et de laisser l’équipe tout masquée.
