---
title: Demandes d’utilisateurs pour que les administrateurs autorisent les applications
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer et configurer la demande de l’utilisateur final pour autoriser les applications bloquées dans une organisation.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 122d41de6f1cb5ea67a5ce85ba9f8f7d02e26339
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647538"
---
# <a name="manage-user-requests"></a>Gérer les demandes des utilisateurs

Les applications que vous bloquez dans votre organisation peuvent affecter la productivité et la collaboration des utilisateurs finaux. Les applications qui sont disponibles dans le magasin Teams mais qui sont bloquées dans votre organisation ne peuvent pas être utilisées par les utilisateurs finaux. Toutefois, pour rester informés, les utilisateurs finaux peuvent afficher les applications bloquées, afficher les informations de l’application et les cas d’usage qu’elles serveurs. Les utilisateurs demandent l’approbation de l’administrateur afin qu’ils utilisent ces applications dans Teams, après avoir évalué la demande.

Cette fonctionnalité vous fournit un signal sur la demande d’une application au sein de votre organisation. Vous pouvez facilement afficher le nombre agrégé de demandes pour les applications. Il vous aide à prendre une décision éclairée sur les applications à évaluer pour autoriser dans votre organisation.

Vous conservez le contrôle total des applications autorisées ou bloquées pour les utilisateurs. Si vous choisissez d’autoriser une application, les contrôles et l’interface utilisateur pour gérer les applications restent les mêmes.

* L’option par défaut envoie les demandes utilisateur dans le Centre d’administration Teams, où vous pouvez [afficher les demandes des utilisateurs et autoriser les applications demandées](#view-user-requests).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Capture d’écran montrant l’option permettant de demander à un administrateur d’approuver une application bloquée.":::

* Une personnalisation vous permet de [configurer l’expérience de l’utilisateur final](#modify-the-default-setting-to-receive-end-user-requests) qui convient le mieux à votre organisation. Vous pouvez fournir une instruction personnalisée qui s’affiche aux utilisateurs finaux sur les applications bloquées dans l’App Store Teams et diriger les utilisateurs vers un site interne pour collecter leurs demandes.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Capture d’écran montrant l’expérience de l’utilisateur final pour les applications en magasin lorsqu’un administrateur redirige l’URL de demande d’application d’autorisation vers un site interne.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modifier le paramètre par défaut pour recevoir des demandes de l’utilisateur final

Pour configurer un message personnalisé et rediriger les utilisateurs vers une URL spécifique à l’organisation pour demander l’approbation de l’application, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à la page **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**  >  teams.

1. Sélectionnez les paramètres de l’application à l’échelle de l’organisation.

1. Pour afficher un message ou une instruction personnalisé dans le magasin client Teams, fournissez un sms dans la configuration des demandes utilisateur.

1. Pour fournir une URL spécifique à l’organisation pour collecter les demandes des utilisateurs, procédez comme suit :

   1. Remplacez les demandes de redirection vers l’option Outil externe par Activé.
   1. Indiquez l’URL personnalisée propre à votre organisation.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Capture d’écran permettant de désactiver la personnalisation de l’URL de la demande de l’utilisateur pour débloquer l’application dans l’interface utilisateur des paramètres à l’échelle de l’organisation.":::

1. Sélectionnez **Enregistrer**.

## <a name="view-user-requests"></a>Afficher les demandes des utilisateurs

Les demandes d’utilisateur final reçues par la méthode par défaut sont affichées dans le Centre d’administration Teams. Vous pouvez facilement afficher et gérer les demandes. Nous vous recommandons d’avoir un triage régulier pour rechercher les demandes des utilisateurs finaux. Pour afficher et autoriser les applications, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à la page **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**  >  teams.

1. Choisissez d’afficher la colonne **Demandes par utilisateur** . Vous pouvez également trier la colonne.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Capture d’écran montrant la colonne pour les demandes d’utilisateur dans le Centre d’administration Teams et indiquant qu’elle peut être triée." lightbox="media/user-requests-tac-expanded.png":::

1. Pour ouvrir la page de détails de l’application que vous souhaitez autoriser, sélectionnez le nom de l’application.

1. Sélectionnez **Gérer les demandes**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Capture d’écran montrant l’option gérer les demandes dans la page de détails de l’application." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Suivez une ou plusieurs des étapes suivantes, comme indiqué dans la boîte de dialogue contextuelle. Les étapes d’approbation d’une application varient en fonction de la méthode utilisée pour la bloquer.

   * Si l’application est bloquée à l’aide de stratégies d’autorisation, [modifiez les stratégies d’autorisation](teams-app-permission-policies.md).
   * Si l’application est bloquée pour tous les utilisateurs, [autorisez l’application](manage-apps.md#allow-and-block-apps).
   * Si toutes les applications sont bloquées pour tous les utilisateurs, [modifiez les paramètres à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

1. Si vous le souhaitez, pour basculer vers une configuration personnalisée vers l’URL propre à votre organisation, sélectionnez Le lien Configurer les demandes des utilisateurs dans la boîte de dialogue Gérer les demandes des utilisateurs. Il ouvre le volet paramètres de l’application à l’échelle de l’organisation dans lequel vous pouvez [configurer l’expérience de demande de l’utilisateur final](#modify-the-default-setting-to-receive-end-user-requests).

Si vous autorisez une application après avoir reçu des demandes dans le Centre d’administration Teams, Teams n’informe pas l’utilisateur final que sa demande est traitée. L’utilisateur peut vérifier l’application dans le Magasin Teams pour vérifier si l’application est autorisée. L’option d’ajout de l’application est disponible pour l’utilisateur une fois que vous l’avez autorisée. Si vous autorisez une application après avoir reçu des demandes via votre méthode spécifique à l’organisation, vos mécanismes internes pour fournir la mise à jour de l’état à l’utilisateur final s’appliquent.

Pour réinitialiser le nombre de demandes d’application à zéro, ignorez les demandes. L’autorisation d’une application ne réinitialise pas son compteur de demande à zéro.

## <a name="dismiss-user-requests"></a>Ignorer les demandes des utilisateurs

Pour ignorer les demandes d’autorisation de l’application, procédez comme suit :

1. Sélectionnez le nom de l’application pour laquelle vous souhaitez ignorer les demandes de l’utilisateur.
1. Sélectionnez **Gérer les demandes** , puis **Ignorer toutes les demandes** dans la boîte de dialogue.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Les administrateurs peuvent approuver une demande utilisateur en autorisant une application, ou peuvent rejeter la demande en n’effectuant aucune action.":::

Si vous ignorez une demande, elle n’informe pas l’utilisateur final que sa demande est exécutée. Lorsque vous ignorez une demande pour autoriser une application, le nombre de demandes dans le Centre d’administration est réinitialisé à zéro. En outre, après quelques heures de rejet d’une demande, les utilisateurs finaux peuvent à nouveau demander que la même application soit autorisée.

## <a name="related-article"></a>Article connexe

* [Vue d’ensemble de la gestion des applications tierces](manage-apps.md).
