---
title: Demandes d’utilisateurs pour les administrateurs
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer et configurer la demande d’approbation des applications bloquées dans une organisation par l’utilisateur final.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 382d3923d008f0bf70b2d9b9a4f3364709b4f2e1
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377602"
---
# <a name="manage-user-requests"></a>Gérer les demandes des utilisateurs

Les applications bloquées dans votre organisation peuvent affecter la productivité et la collaboration des utilisateurs finaux. Les utilisateurs finaux ne peuvent pas utiliser d’applications bloquées, mais afficher ces applications et leurs informations dans le magasin Teams et demander l’approbation des administrateurs. Après avoir évalué la demande, vous pouvez choisir d’autoriser une application ou de rejeter la demande.

Cette fonctionnalité vous fournit un signal sur la demande d’une application au sein de votre organisation. Vous pouvez facilement afficher le nombre agrégé de demandes pour chaque application demandée. Il vous aide à prendre une décision éclairée sur les applications à évaluer pour l’autorisation.

Vous conservez le contrôle total des applications autorisées ou bloquées pour les utilisateurs. Si vous choisissez d’autoriser une application, les contrôles et l’interface utilisateur pour gérer les applications restent les mêmes.

* L’option par défaut envoie les demandes utilisateur au Centre d’administration Teams, où vous pouvez [afficher les demandes des utilisateurs et autoriser les applications demandées](#view-and-act-on-user-requests-in-teams-admin-center).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Capture d’écran montrant l’option permettant de demander à un administrateur d’approuver une application bloquée.":::

* Une personnalisation vous permet de [configurer l’expérience de l’utilisateur final](#modify-the-default-setting-to-receive-end-user-requests) qui convient le mieux à votre organisation. Vous pouvez fournir une instruction ou un message personnalisé qui s’affiche dans l’App Store Teams et l’option d’approbation de demande dirige les utilisateurs vers une URL spécifique à l’organisation pour collecter leurs demandes.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Capture d’écran montrant l’expérience de l’utilisateur final pour les applications en magasin lorsqu’un administrateur redirige l’URL de demande d’application autoriser vers une URL spécifique à l’organisation.":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>Afficher et agir sur les demandes des utilisateurs dans le Centre d’administration Teams

Les demandes d’utilisateur final reçues par la méthode par défaut sont affichées dans le Centre d’administration Teams. Vous pouvez facilement afficher et gérer les demandes. Nous vous recommandons un triage régulier pour rechercher les demandes des utilisateurs finaux. Pour afficher et autoriser les applications, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à Teams **Apps** > [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Choisissez d’afficher la colonne **Demandes par utilisateur** . Vous pouvez également trier la colonne.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Capture d’écran montrant la colonne pour les demandes d’utilisateur dans le Centre d’administration Teams et indiquant qu’elle peut être triée." lightbox="media/user-requests-tac-expanded.png":::

1. Pour ouvrir la page de détails de l’application que vous souhaitez autoriser, sélectionnez le nom de l’application.

1. Sélectionnez **Gérer les demandes**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Capture d’écran montrant l’option gérer les demandes dans la page de détails de l’application." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Suivez une ou plusieurs des étapes suivantes, comme indiqué dans la boîte de dialogue contextuelle. Les étapes d’approbation d’une application varient en fonction de la méthode utilisée pour la bloquer.

   * Si l’application est bloquée à l’aide de stratégies d’autorisation, [modifiez les stratégies d’autorisation](teams-app-permission-policies.md).
   * Si l’application est bloquée pour tous les utilisateurs, [autorisez l’application](manage-apps.md#allow-and-block-apps).
   * Si toutes les applications sont bloquées pour tous les utilisateurs, [modifiez les paramètres à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

Les utilisateurs finaux peuvent afficher l’option **Ajouter** pour une application dans le Magasin Teams pour vérifier si l’application est autorisée. Lorsque vous autorisez une application après avoir reçu des demandes dans le Centre d’administration Teams, Teams n’informe pas les utilisateurs finaux que leur demande est traitée. Lorsque vous autorisez une application, le compteur de demande n’est pas réinitialisé à zéro.

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modifier le paramètre par défaut pour recevoir des demandes de l’utilisateur final

Teams fournit un message par défaut permettant aux utilisateurs de demander l’approbation d’une application. Vous pouvez modifier le paramètre par défaut pour ajouter un message personnalisé avec des instructions, une URL spécifique à l’organisation ou les deux. Les modifications sont affichées pour chaque application dans le Magasin Teams.

Pour configurer un message personnalisé et rediriger les utilisateurs vers une URL spécifique à l’organisation, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à Teams **Apps** > [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Dans le coin supérieur droit, sélectionnez **Paramètres de l’application à l’échelle de l’organisation**.

1. Pour afficher un message ou une instruction personnalisé dans le magasin Teams, entrez un sms dans le champ de texte sous **Configuration des demandes de l’utilisateur**. Le champ a une limite de 300 caractères.

1. Pour fournir une URL spécifique à l’organisation pour collecter les demandes des utilisateurs, procédez comme suit :

   1. Activez le bouton bascule **Des demandes de redirection vers un lien externe** .
   1. Indiquez l’URL propre à votre organisation.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Capture d’écran permettant de désactiver la personnalisation de l’URL des demandes utilisateur dans l’interface utilisateur des paramètres à l’échelle de l’organisation.":::

1. Sélectionnez **Enregistrer**.

Si vous choisissez de le faire, les méthodes permettant d’évaluer des applications tierces et d’autoriser les applications demandées restent les mêmes.

## <a name="dismiss-user-requests"></a>Ignorer les demandes des utilisateurs

Pour ignorer les demandes, procédez comme suit :

1. Sélectionnez le nom de l’application pour laquelle vous souhaitez ignorer les demandes de l’utilisateur.
1. Sélectionnez **Gérer les demandes**.
1. Dans la boîte de dialogue Gérer les demandes des utilisateurs, **sélectionnez Ignorer toutes les demandes**.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Les administrateurs peuvent approuver une demande utilisateur en autorisant une application, ou peuvent rejeter la demande en n’effectuant aucune action.":::

Si vous ignorez une demande, elle n’informe pas l’utilisateur final que sa demande est exécutée. Lorsque vous ignorez une demande pour autoriser une application, le nombre de demandes dans le Centre d’administration est réinitialisé à zéro. En outre, après quelques heures de rejet d’une demande, les utilisateurs finaux peuvent à nouveau demander que la même application soit autorisée.

## <a name="related-article"></a>Article connexe

* [Vue d’ensemble de la gestion des applications tierces](manage-apps.md).
