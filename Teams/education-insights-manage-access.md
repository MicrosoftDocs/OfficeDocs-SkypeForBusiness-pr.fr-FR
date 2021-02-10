---
title: Gérer l’accès des utilisateurs à Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Gérez l’accès des utilisateurs à Education Insights dans Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145934"
---
# <a name="manage-user-access-to-education-insights"></a>Gérer l’accès des utilisateurs à Education Insights

Ce document indique les étapes nécessaires pour gérer l’accès des utilisateurs à [Education Insights dans Microsoft Teams](class-insights.md).

Vous devez accorder des autorisations aux responsables de l’éducation, aux chefs de district, aux directeurs d’école, aux chefs d’établissement, aux conseillers, aux responsables de domaine d’étude, aux responsables de programmes, aux travailleurs sociaux et aux psychologues. Les enseignants bénéficient *automatiquement* d’une autorisation lorsqu’ils sont propriétaires d’une équipe de classe.

Pour fournir des informations au niveau de l’organisation, vous devez [importer des données du système d'informations sur les élèves (SIE)](education-insights-sis-data-sync.md). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée.

> [!NOTE]
> Seul l’administrateur général peut gérer l’accès des utilisateurs à Insights.

> [!TIP]
> Nous vous recommandons d’activer Insights pour tous les responsables de l’éducation. Ainsi, ils disposeront des données permettant de comprendre chaque établissement scolaire, et pourront identifier rapidement les problèmes, puis fournir un support aux enseignants concernés. Même si vous gérez un pilote, il peut être utile de maintenir Insights activé pour tous les responsables de l’éducation, mais de cibler les communications uniquement sur le groupe pilote d’utilisateurs.



## <a name="grant-permissions"></a>Accorder des autorisations

* Ouvrez l’application Insights, cliquez **Paramètres**, puis sélectionnez **Autorisations utilisateur**.

:::image type="content" source="media/insights-user-permissions.png" alt-text="Paramètres":::

* Sélectionnez **Ajouter des utilisateurs**.
* Entrez le nom d’utilisateur ou l’adresse e-mail de chaque utilisateur.
* Sélectionnez le niveau d’autorisation :
  * **L’accès à toute l’organisation** signifie que l’utilisateur a accès à toutes les unités de l’organisation à tous les niveaux.
  * **L’accès à des établissements spécifiques** signifie que l’utilisateur a accès aux établissements scolaires sélectionnés. Commencez à taper, puis sélectionnez l’établissement dans la liste. Vous pouvez ajouter plusieurs établissements scolaires simultanément.
* Cliquez sur **Ajouter de nouveaux utilisateurs**.

:::image type="content" source="media/insights-add-users.png" alt-text="Accorder des autorisations":::

> [!NOTE]
> Accordez uniquement les autorisations aux responsables de l’éducation qui en ont besoin, ainsi qu’aux unités d’organisation dont ils sont responsables. Si vous ne savez pas si une autorisation d’utilisateur est nécessaire pour une organisation spécifique, veuillez consulter les experts en matière de confidentialité de votre établissement, tels que le personnel juridique ou celui des ressources humaines.

## <a name="edit-permissions"></a>Modifier les autorisations
* Sélectionnez un utilisateur spécifique, puis sélectionnez **Modifier les autorisations**.
* Mettez à jour le niveau d’autorisation ou la liste des établissements scolaires, puis cliquez sur **Mettre à jour les autorisations**.

:::image type="content" source="media/insights-edit-users.png" alt-text="Modifier les autorisations":::

## <a name="remove-permissions"></a>Supprimer les autorisations
* Sélectionnez les utilisateurs à supprimer, puis sélectionnez **Supprimer les utilisateurs**.
* Ces utilisateurs n’auront plus accès à Insights au niveau de l’organisation, mais pourront toujours accéder à Insights au niveau de la classe s’ils sont membres d’une équipe de classe.

:::image type="content" source="media/insights-remove-users.png" alt-text="Supprimer des autorisations":::
