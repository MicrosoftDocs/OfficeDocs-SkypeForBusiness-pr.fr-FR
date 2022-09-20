---
title: Utiliser la personnalisation des applications pour personnaliser les applications en fonction des besoins de votre organisation
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment modifier les métadonnées et l’apparence d’une application pour la renommer pour une meilleure adoption dans votre organisation.
ms.openlocfilehash: 6903d6bcd190869046c6f2e1a134c43cde3a1f07
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837694"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Utiliser la personnalisation des applications pour mettre à jour la personnalisation des applications dans le Magasin Teams de votre organisation

Les administrateurs Microsoft Teams peuvent modifier l’apparence de certaines applications Teams pour fournir une expérience personnalisée de marque aux utilisateurs finaux de leur organisation. Ces modifications peuvent améliorer l’expérience du magasin Teams pour les utilisateurs finaux et contribuer à l’adhésion à la personnalisation de l’organisation. Par exemple, les administrateurs peuvent modifier la description et l’icône d’une application. La personnalisation permet aux utilisateurs finaux d’identifier facilement l’application comme outil interne, de comprendre son cas d’usage propre à l’organisation et de l’utiliser en toute confiance. Les administrateurs effectuent ces mises à jour en modifiant certaines métadonnées ou propriétés d’une application. Les modifications sont disponibles uniquement au sein de leur organisation. Cette fonctionnalité est appelée personnalisation d’application.

Les administrateurs peuvent uniquement personnaliser les applications si le développeur d’applications autorise la personnalisation de leur application. Bien que Teams offre une option pour personnaliser les propriétés suivantes, les développeurs d’applications contrôlent les propriétés qui peuvent être réellement personnalisées par n’importe quel administrateur.

* Nom court
* Description courte
* Description complète
* URL de la Politique de confidentialité
* URL du site web
* URL des conditions d'utilisation
* Icône de l’application
* Couleur de contour de l’icône
* Couleur de l'accentuation

Pour plus d’informations sur chacune de ces propriétés, consultez le [schéma de manifeste Teams](/microsoftteams/platform/resources/schema/manifest-schema) dans la documentation du développeur Teams.

> [!NOTE]
> Vous devez disposer d’une licence cliente Teams pour personnaliser les informations de l’application.

## <a name="verify-if-an-app-is-customizable"></a>Vérifier si une application est personnalisable

Toutes les applications ne sont pas personnalisables. Si un développeur d’applications autorise la personnalisation de son application, vous pouvez uniquement modifier l’apparence de l’application. Pour vérifier si l’application de votre choix est personnalisable ou non, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Si vous le souhaitez, si la colonne **personnalisable** n’est pas visible, sélectionnez Modifier les colonnes :::image type="icon" source="media/settings-icon-16px.svg"::: et basculez l’option **Personnalisable** sur **Activé**.

1. Recherchez l’application que vous souhaitez personnaliser à l’aide du nom de l’application. Vérifiez dans la colonne **Personnalisable** si le développeur d’applications autorise ou non la personnalisation de l’application.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="La capture d’écran montre que la colonne personnalisable dans le Centre d’administration vous aide à vérifier si une application est personnalisable ou non.":::

Pour connaître toutes les applications personnalisables dans le magasin Teams, triez la colonne **personnalisable** .

## <a name="customize-an-app"></a>Personnaliser une application

Pour modifier l’apparence d’une application dans le magasin Teams de votre organisation, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application que vous souhaitez personnaliser à l’aide du nom de l’application et [assurez-vous qu’elle peut être personnalisée](#verify-if-an-app-is-customizable).

1. Pour ouvrir l’interface utilisateur afin de personnaliser des champs de métadonnées individuels, effectuez l’une des étapes suivantes :

   * Sélectionnez la ligne d’une application, puis sélectionnez **Personnaliser** :::image type="icon" source="media/edit-pen-icon.png"::: dans la barre d’outils de la page Gérer les applications.

   * Sélectionnez le nom de l’application pour ouvrir la page de détails de l’application, puis sélectionnez l’icône :::image type="icon" source="media/edit-pen-icon.png"::: modifier sous **Personnalisable**.

   * Sélectionnez le nom de l’application pour ouvrir la page de détails de l’application, puis sélectionnez **Actions** > **personnaliser**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="La capture d’écran montre une option permettant de personnaliser une application en ouvrant le menu Actions et en sélectionnant l’option Personnaliser à partir de la page de détails de l’application." lightbox="media/customize-action-menu-expanded.png":::

1. Personnalisez un ou plusieurs des champs disponibles. Seuls ces champs de métadonnées sont affichés et personnalisables que le développeur d’applications a autorisés. Pour connaître les limitations de certains champs, consultez [les considérations et les limitations des champs personnalisables](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="La capture d’écran affiche le nom et la description sur l’interface utilisateur de personnalisation.":::

1. Après avoir personnalisé l’application, sélectionnez **Appliquer**. Pour vérifier les modifications que vous avez apportées, consultez [les détails de l’application en préversion](#preview-app-customizations). Pour annuler les modifications, consultez [réinitialiser les détails de l’application aux valeurs par défaut](#reset-app-details-to-default-values).

1. Sélectionnez **Publier** pour publier l’application personnalisée dans le magasin de votre organisation.

L’application est répertoriée dans la page **Gérer les applications** et dans le magasin et le client Teams (disponibles via le client web, mobile ou de bureau) avec les détails mis à jour. L’affichage de la modification peut prendre quelques heures.

## <a name="preview-app-customizations"></a>Préversion des personnalisations d’application

Pour afficher les modifications après avoir enregistré les personnalisations, consultez la page des détails de l’application.

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pour ouvrir la page de détails de l’application, sélectionnez le nom de l’application.

1. Affichez les détails de l’application, y compris le nom d’application d’origine dans le champ **Nom court de l’éditeur**. Le champ est visible uniquement si vous avez modifié le nom court de l’application.

   :::image type="content" source="media/original-app-version.png" alt-text="La capture d’écran montre le nom court modifié d’une application.":::

Après quelques heures, vos utilisateurs Teams peuvent voir l’application personnalisée dans le Magasin Teams dans leur client (web, mobile et bureau).

   :::image type="content" source="media/contoso-app.png" alt-text="La capture d’écran montre une application personnalisée dans le client Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considérations et limitations de la personnalisation des applications

Prenez en compte les détails suivants sur la fonctionnalité de personnalisation d’application :

* Vous pouvez uniquement personnaliser des [applications tierces](deploy-apps-microsoft-teams-landing-page.md#third-party-apps-validated-by-microsoft) et non [des applications personnalisées](deploy-apps-microsoft-teams-landing-page.md#custom-apps).

* Vous ne pouvez pas personnaliser d’application dans les environnements Government Community Cloud High (GCCH) et Department of Defense (DoD).

* Une application ne peut être personnalisée que si le développeur de l’application l’autorise.

* Les modifications apportées à toutes les applications sont disponibles uniquement au sein de votre organisation.

* Vous n’aurez qu’une seule version de l’application, car la personnalisation des détails de l’application ne crée pas de copie de l’application.

* Lorsque vous personnalisez des applications et toute description liée à une application, veillez à suivre les instructions fournies par les développeurs d’applications dans leur documentation ou conditions d’utilisation. Respecter les lois sur le droit d’auteur lors de l’utilisation d’images tierces.

* Administration données de personnalisation fournies sont stockées dans la région de stockage de données la plus proche.

* Vous devez vous assurer que les liens vers les conditions d’utilisation ou la politique de confidentialité sont valides.

* Si le développeur d’application n’autorise plus la personnalisation d’un champ, un message s’affiche sur la page de détails de l’application pour informer l’administrateur d’un tel champ. Toutes les modifications apportées au champ sont rétablies à la valeur d’origine.

* Nous vous recommandons de tester les modifications de personnalisation d’application dans un locataire de test Teams avant d’apporter ces modifications dans votre environnement de production. Pour obtenir un locataire de test, suivez les instructions fournies lors de la [création de votre locataire de test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* Mises à jour prendre jusqu’à 24 heures pour s’afficher dans le client pour tous les utilisateurs et comptes d’administrateur.

* Pour qu’une application existante devienne personnalisable, le développeur peut fournir une nouvelle version de l’application sur le Magasin Teams.

* Le [rapport d’utilisation de l’application](teams-analytics-and-reports/app-usage-report.md) affiche le nom d’origine de l’application fournie par l’éditeur, même si l’application personnalisée est utilisée par les utilisateurs finaux.

* La boîte de dialogue de consentement d’autorisation Microsoft Graph affiche le nom d’origine de l’application fournie par l’éditeur. Il vous aide à identifier avec précision une application tout en lui fournissant des autorisations.

* La personnalisation d’une application ne modifie aucune fonctionnalité d’application.

Les limitations de certains champs personnalisables sont les suivantes :

| Champ personnalisable | Considération |
|:---|:---|
| Tous les champs d’URL | Vérifiez les URL valides et sécurisées à l’aide de `https`. |
| Description courte | La courte description doit comporter moins de 80 caractères. Ne répétez pas ce qui se trouve dans la description complète. |
| Icône | Icône de contour transparent au format PNG d’une résolution de 32 x 32 pixels. |
| Icône couleur | Icône de couleurs complètes au format PNG de résolution de 192 x 192 pixels. |
| Couleur de l'accentuation | La couleur doit correspondre à l’arrière-plan de votre icône. |

## <a name="troubleshoot-app-customization"></a>Résoudre les problèmes de personnalisation de l’application

| Erreurs et problèmes | Résolution ou compréhension possibles du problème |
| --- | --- |
| Mes mises à jour ne sont pas disponibles pour mes utilisateurs finaux. | Attendez quelques heures que les modifications se propagent. |
| Je ne peux pas personnaliser une application. | Vérifiez si [l’application est personnalisable ou non](#verify-if-an-app-is-customizable).|
| J’ai commencé à personnaliser une application, mais je ne peux pas enregistrer ou appliquer mes modifications. | Respectez les limites des champs. Rechercher les erreurs sur l’interface utilisateur et [les limitations de la personnalisation de l’application](#considerations-and-limitations-of-app-customization) |
| Gérer le chargement de la page d’applications qui ne se charge pas correctement. La liste des applications n’est pas affichée. | Administration compte en service doit avoir la licence Teams attribuée. |

<!--- Check ICM for error string. --->

## <a name="reset-app-details-to-default-values"></a>Réinitialiser les détails de l’application aux valeurs par défaut

Vous pouvez réinitialiser les détails de l’application aux valeurs d’origine fournies par le développeur de l’application. L’option est disponible uniquement pour l’application que vous personnalisez.

1. Dans le Centre d’administration Teams, accédez à **Applications Teams** > **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pour ouvrir la page de détails de l’application, sélectionnez le nom de l’application.

1. Dans le menu **Actions** , sélectionnez **Rétablir la valeur par défaut**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="La capture d’écran montre l’option de réinitialisation à l’option par défaut pour une application personnalisée.":::

## <a name="related-articles"></a>Articles connexes

* [Personnaliser le magasin d’applications de votre organisation](customize-your-app-store.md)
* [Rebrand your apps community post](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
