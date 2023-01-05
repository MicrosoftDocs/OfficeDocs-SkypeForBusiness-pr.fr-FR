---
title: Gérer l’accès des utilisateurs à Education Insights
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gérez l’accès des utilisateurs à Education Insights dans Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707806"
---
# <a name="manage-user-access-to-education-insights"></a>Gérer l’accès des utilisateurs à Education Insights

Ce document indique les étapes nécessaires pour gérer l’accès des utilisateurs à [Education Insights dans Microsoft Teams](class-insights.md).

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

Pour fournir des informations au niveau de l’organisation, vous devez [importer des données du système d'informations sur les élèves (SIE)](education-insights-sis-data-sync.md). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée.

> [!NOTE]
> Seul l’administrateur général peut gérer l’accès des utilisateurs à Insights.

> [!TIP]
> Nous vous recommandons d’activer Insights pour tous les responsables de l’éducation. Ainsi, ils disposeront des données permettant de comprendre chaque établissement scolaire, et pourront identifier rapidement les problèmes, puis fournir un support aux enseignants concernés. Même si vous gérez un pilote, il peut être utile de maintenir Insights activé pour tous les responsables de l’éducation, mais de cibler les communications uniquement sur le groupe pilote d’utilisateurs.

## <a name="manage-permissions"></a>Gérer les autorisations

* Ouvrez l’application Insights, cliquez **Paramètres**, puis sélectionnez **Autorisations utilisateur**.

:::image type="content" source="media/insights-user-permissions.png" alt-text="Paramètres.":::

> [!NOTE]
> Lorsque vous fournissez une autorisation pour un niveau de l’organisation, l’utilisateur peut voir toutes les unités d’organisation en dessous.
> 
> Accordez uniquement les autorisations aux responsables de l’éducation qui en ont besoin, ainsi qu’aux unités d’organisation dont ils sont responsables. Si vous ne savez pas si une autorisation d’utilisateur est nécessaire pour une organisation spécifique, veuillez consulter les experts en matière de confidentialité de votre établissement, tels que le personnel juridique ou celui des ressources humaines.

> [!IMPORTANT]
> Après avoir attribué des autorisations pour la première fois, les utilisateurs peuvent afficher les données au sein de l’application uniquement si au moins **deux** utilisateurs ont accédé à l’application. Cette exigence permet de s’assurer que le fuseau horaire des données est correctement configuré et que les données sont affichées avec précision pour tous les utilisateurs. Si les utilisateurs rencontrent des problèmes d’accès aux données une fois les autorisations accordées, vérifiez si au moins deux utilisateurs ont accédé à l’application.

## <a name="role-based-permissions"></a>Autorisations basées sur des rôles

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> Lorsqu’un utilisateur se voit affecter un rôle, il reçoit automatiquement les autorisations appropriées pour consulter les données qui les intéressent.
>
> Si un utilisateur n’est plus dans un rôle, son autorisation pour celui-ci est automatiquement révoquée (bien qu’il puisse encore avoir des autorisations individuelles).

* Au besoin, cliquez sur l’onglet **Autorisations basées sur des rôles**.

  Vous verrez une liste des rôles dans votre organisation éducative, le niveau dans cette hiérarchie pour chacun d’entre eux, le nombre d’utilisateurs affectés à ce rôle et le niveau d’autorisation du rôle. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="Autorisations basées sur des rôles.":::
  
  S’il existe un rôle sur plus d’un niveau de l’organisation, celui-ci s’affiche plusieurs fois, une fois par niveau. Dans la capture d'écran, nous avons des directeurs au niveau de l'école, du district et du département, il y a donc trois lignes pour « directeur ».
  
* Pour chaque rôle, cliquez sur l’icône crayon pour sélectionner le niveau d'autorisation. Le rôle par défaut ne dispose pas de l’autorisation pour afficher des informations.
* Sélectionnez le niveau d'autorisation : **Afficher les données pour leur organisation** ou **Aucun**.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="Panneau de permissions basé sur les rôles.":::
  
  Si vous voyez sur la liste un utilisateur qui a besoin d'un niveau de permission plus nuancé, ajustez son rôle et/ou son organisation dans les données [importées de votre SIS](education-insights-sis-data-sync.md) et [accordez-lui des permissions](#grant-individual-permission-to-a-user) individuelles (si nécessaire).

* Cliquez sur **Enregistrer les modifications**.

  Ce niveau d'autorisation est désormais automatiquement affecté à tous les nouveaux utilisateurs ayant ce rôle ou niveau d’organisation. L’utilisateur affiche les données pour toutes les unités d’organisation à son niveau de hiérarchie et en dessous.  


## <a name="individual-permissions"></a>Autorisations individuelles

Utilisez les autorisations individuelles pour ajuster l’autorisation d’un utilisateur ou pour affecter des autorisations à chaque utilisateur si vous n’avez pas utilisé SDS V2 pour importer les données SIS pour votre organisation.

* Cliquez sur l’onglet **Autorisations individuelles**.
  
  Les utilisateurs auxquels une autorisation individuelle est accordée s’affichent dans votre organisation éducative. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="Autorisations individuelles.":::
  
### <a name="grant-individual-permission-to-a-user"></a>Accorder des autorisations individuelles à une utilisateur
* Cliquez sur **Accorder des autorisations individuelles** dans le côté gauche de l’écran.
* Entrez le nom d’utilisateur ou l’adresse e-mail de chaque utilisateur.
* Sélectionnez le niveau d’autorisation :
  * **L’accès à toute l’organisation** signifie que l’utilisateur a accès à toutes les unités d’organisation à tous les niveaux. Il est rarement utilisé.
  * **Organisation spécifique** signifie que l’utilisateur voit l’unité d’organisation sélectionnée et toutes les unités d’organisation en dessous. Commencez à taper, puis sélectionnez l’unité d’organisation dans la liste.
* Cliquez sur **Accorder des autorisations** pour enregistrer.

### <a name="change-the-individual-permission-of-a-user"></a>Modifier les autorisations individuelles d’un utilisateur
* Pour l’utilisateur concerné, cliquez sur l’icône crayon pour sélectionner le niveau d'autorisation individuelle.
* Sélectionnez le niveau d’autorisation :
  * **L’accès à toute l’organisation** signifie que l’utilisateur a accès à toutes les unités d’organisation à tous les niveaux. Il est rarement utilisé.
  * **Organisation spécifique** signifie que l’utilisateur voit l’unité d’organisation sélectionnée et toutes les unités d’organisation en dessous. Commencez à taper, puis sélectionnez l’unité d’organisation dans la liste.
  * **Aucun** signifie que l’utilisateur ne voit que les unités d’organisation automatiquement affectées par son rôle (le cas échéant).
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="Panneau de permissions individuelles.":::

* Cliquez sur **Enregistrer les modifications** pour enregistrer.
