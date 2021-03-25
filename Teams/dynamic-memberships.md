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
description: Découvrez comment Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 en utilisant l’appartenance dynamique.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120766"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Microsoft Teams prend en charge les équipes associées aux groupes Microsoft 365 en utilisant *l’appartenance dynamique.* L’appartenance dynamique permet de définir l’appartenance d’une équipe par une ou plusieurs règles qui vérifient certains attributs d’utilisateur dans Azure Active Directory (Azure AD). Les utilisateurs sont ajoutés ou supprimés automatiquement des équipes correctes à mesure que les attributs des utilisateurs changent ou que des utilisateurs rejoignent et quittent le client.

L’appartenance dynamique vous permet de configurer des équipes pour certains utilisateurs de votre organisation. Les scénarios possibles sont les suivants :
- Un hôpital peut créer des équipes distinctes pour les infirmières, les médecins et les infirmières pour diffuser les communications. Ceci est particulièrement important si l’hôpital s’appuie sur des employés temporaires.
- Une université peut créer une équipe pour tous les enseignants d’une université en particulier, y compris un enseignant agrégé qui change fréquemment.
- Une compagnie aérienne souhaite créer une équipe pour chaque vol (par exemple, un mardi après-midi sans s’arrêter de Chicago à Atlanta) et supprimer automatiquement ou automatiquement une équipe de vol en modification fréquente, si nécessaire.

Cette fonctionnalité permet aux membres d’une équipe donnée de se mettre à jour automatiquement en fonction d’un ensemble spécifique de critères, au lieu de gérer manuellement l’appartenance. Pour ce faire, les licences Azure AD [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) Premium P1 et l’appartenance à une équipe peuvent être attribuées par un administrateur client aux propriétés Azure AD de n’importe quel utilisateur, à condition que vous utilisiez un client et un compte administrateur.

Microsoft Teams peut prendre de quelques minutes à 2 heures pour refléter les changements d’appartenance dynamiques une fois qu’ils prennent effet dans le groupe Microsoft 365 d’une équipe.

> [!NOTE]
> - Les règles peuvent définir qui est membre d’une équipe, mais pas qui est propriétaire de l’équipe.
> - Consultez [les limites et les spécifications de Microsoft Teams pour](limits-specifications-teams.md) les limites actuelles sur la taille des équipes et des canaux.
> - Les propriétaires ne pourront pas ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, car les membres sont définis par des règles de groupe dynamiques.
> -    Les membres ne peuvent pas laisser les équipes dosées par des groupes dynamiques.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Création et gestion d’un groupe Microsoft 365 avec une appartenance dynamique

Lorsque vous êtes connecté en tant qu’administrateur client, suivez les instructions dans Créer un groupe [dynamique et vérifiez l’état.](/azure/active-directory/users-groups-roles/groups-create-rule) Selon les besoins, reportez-vous aux règles [d’appartenance dynamique pour les groupes dans Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Créer une équipe avec votre groupe Microsoft 365

Accordez à présent le temps que les changements d’appartenance prennent effet et créez une équipe comme décrit dans Créer une équipe à partir [d’un groupe existant.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Appliquer une appartenance dynamique à une équipe existante

Vous pouvez également prendre une équipe existante et la modifier pour avoir une appartenance dynamique, comme décrit dans Modifier l’appartenance à un groupe statique en dynamique dans [Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Modifications du comportement du client

Une fois l’appartenance dynamique activée pour une équipe, les clients Teams n’autoriseront plus la gestion des membres de l’équipe. Les options pour ajouter des membres, modifier les rôles de membre, envoyer et approuver des demandes d’adhésion et quitter l’équipe sont masquées.