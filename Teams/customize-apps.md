---
title: Utiliser la personnalisation des applications pour personnaliser les applications en fonction des besoins de votre organisation
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
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
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647478"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>Utiliser la personnalisation des applications pour mettre à jour la personnalisation des applications dans le Magasin Teams de votre organisation

Les administrateurs Microsoft Teams peuvent modifier l’apparence de certaines applications Teams pour fournir une expérience personnalisée de marque aux utilisateurs finaux de leur organisation. Ces modifications peuvent améliorer l’expérience du magasin Teams pour les utilisateurs finaux et contribuer à l’adhésion à la personnalisation de l’organisation. Par exemple, les administrateurs peuvent modifier la description et l’icône d’une application, ce qui permet aux utilisateurs finaux de leur organisation d’identifier plus facilement l’application, de comprendre son utilisation et d’ajouter de l’importance. Les administrateurs apportent ces modifications en modifiant certaines métadonnées ou propriétés d’une application. Les modifications sont disponibles uniquement au sein de leur organisation. Cette fonctionnalité est appelée personnalisation d’application.

Les administrateurs peuvent uniquement personnaliser les applications si le développeur d’applications autorise la personnalisation de leur application. Bien que Teams offre la possibilité de personnaliser quelques propriétés, les développeurs d’applications contrôlent les propriétés qui peuvent être réellement personnalisées par n’importe quel administrateur.

En tant qu’administrateur, vous pouvez personnaliser les propriétés suivantes.

* Nom court
* Description courte
* Description complète
* URL de la Politique de confidentialité
* URL du site web
* URL des conditions d'utilisation
* Icône de l’application
* Couleur de contour de l’icône
* Couleur de l'accentuation

Pour plus d’informations sur chacun de ces champs de métadonnées, consultez le [schéma de manifeste Teams](/microsoftteams/platform/resources/schema/manifest-schema) dans la documentation du développeur Teams.

> [!NOTE]
> La fonctionnalité de personnalisation des applications n’est pas disponible pour les applications personnalisées. Les administrateurs ne peuvent pas personnaliser d’application dans les environnements Government Community Cloud High (GCCH) et Department of Defense (DoD).

## <a name="verify-if-an-app-is-customizable"></a>Vérifier si une application est personnalisable

Toutes les applications ne sont pas personnalisables. Si un développeur d’applications vous permet de personnaliser son application, vous pouvez uniquement utiliser la fonctionnalité de personnalisation de l’application pour modifier l’apparence de l’application. Pour vérifier si l’application de votre choix est personnalisable ou non, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application que vous souhaitez personnaliser à l’aide du nom de l’application. Vérifiez dans la colonne **Personnalisable** si le développeur d’applications autorise ou non la personnalisation de l’application. Si la colonne n’est pas visible, sélectionnez Modifier les colonnes :::image type="icon" source="media/settings-icon-16px.svg"::: et basculez l’option **Personnalisable** **sur Activé**.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="La capture d’écran montre que la colonne personnalisable dans le Centre d’administration vous aide à vérifier si une application est personnalisable ou non.":::

Pour connaître toutes les applications personnalisables dans le magasin Teams, triez la colonne personnalisable.

## <a name="customize-the-details-of-an-app"></a>Personnaliser les détails d’une application

Pour modifier l’apparence d’une application tel qu’elle apparaît dans le magasin Teams de votre organisation, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application que vous souhaitez personnaliser à l’aide du nom de l’application et assurez-vous qu’elle peut être personnalisée.

1. Pour ouvrir l’interface utilisateur afin de personnaliser des champs de métadonnées individuels, effectuez l’une des étapes suivantes :

   * Sélectionnez la ligne d’une application, puis sélectionnez **Personnaliser** :::image type="icon" source="media/edit-pen-icon.png"::: dans la barre d’outils de la page Gérer les applications.

   * Sélectionnez le nom de l’application pour ouvrir la page de détails de l’application, puis sélectionnez l’icône :::image type="icon" source="media/edit-pen-icon.png"::: modifier sous **Personnalisable**.

   * Sélectionnez le nom de l’application, sélectionnez **Actions**, puis **Personnaliser**.

     :::image type="content" source="media/customize-action-menu.png" alt-text="La capture d’écran montre une option permettant de personnaliser une application en ouvrant le menu Actions et en sélectionnant l’option Personnaliser à partir de la page de détails de l’application." lightbox="media/customize-action-menu-expanded.png":::

1. Personnalisez un ou plusieurs des champs disponibles. Un développeur d’applications peut autoriser uniquement la personnalisation de quelques champs de métadonnées. Consultez [les considérations et limitations des champs personnalisables](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="La capture d’écran affiche le nom et la description sur l’interface utilisateur de personnalisation.":::

1. Après avoir personnalisé l’application, sélectionnez **Appliquer**. Pour vérifier les modifications que vous avez apportées, consultez [les détails de l’application en préversion](#preview-app-details). Pour annuler les modifications, consultez [réinitialiser les détails de l’application aux valeurs par défaut](#reset-app-details-to-default-values).

1. Sélectionnez **Publier** pour publier l’application personnalisée et la voir répertoriée dans la page **Gérer les applications** .

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>Aperçu des détails de l’application

Pour afficher les modifications après avoir enregistré la personnalisation, consultez la page des détails de l’application.

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pour ouvrir la page de détails de l’application, sélectionnez le nom de l’application.

1. Affichez les détails de l’application, y compris le nom d’application d’origine dans le champ **Nom court de l’éditeur**. Le champ est visible uniquement si vous avez modifié le nom court de l’application.

   :::image type="content" source="media/original-app-version.png" alt-text="La capture d’écran montre le nom court modifié d’une application.":::

Vos utilisateurs Teams peuvent voir l’application personnalisée dans le Magasin Teams dans leur client.

   :::image type="content" source="media/contoso-app.png" alt-text="La capture d’écran montre une application personnalisée dans le client Teams.":::

## <a name="considerations-and-limitations-of-app-customization"></a>Considérations et limitations de la personnalisation des applications

Prenez en compte les détails suivants sur la fonctionnalité de personnalisation d’application :

* Vous n’aurez qu’une seule version de l’application, car la personnalisation des fonctionnalités de l’application ne crée pas de copie de l’application.

* Lorsque vous personnalisez des applications et toute description liée à une application, veillez à suivre les instructions fournies par les développeurs d’applications dans leur documentation ou leurs conditions d’utilisation. Respecter les lois sur le droit d’auteur lors de l’utilisation d’images tierces.

* Les données de personnalisation fournies par l’administrateur sont stockées dans la région la plus proche.

* Vous devez vous assurer que les liens vers les conditions d’utilisation ou la politique de confidentialité sont valides.

* Si le développeur d’application n’autorise plus la personnalisation d’un champ, un message s’affiche sur la page de détails de l’application pour informer l’administrateur des champs qui ne peuvent plus être personnalisés. Toutes les modifications apportées à ce champ seront rétablies aux valeurs d’origine.

* Nous vous recommandons de tester les modifications de personnalisation d’application dans un locataire de test Teams avant d’apporter ces modifications dans votre environnement de production. Pour obtenir un locataire de test, suivez les instructions fournies lors de la [création de votre locataire de test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant).

* La propagation des modifications à tous les utilisateurs prend jusqu’à 24 heures.

* Pour qu’une application devienne personnalisable, les développeurs peuvent fournir une nouvelle version de l’application. Vous chargez la nouvelle version et supprimez la version précédente de l’application. Si vous avez personnalisé une application et l’avez publiée, la nouvelle application personnalisée à l’aide de la fonctionnalité de personnalisation de l’application ne remplacera pas l’application actuelle.

* Le [rapport d’utilisation de l’application](teams-analytics-and-reports/app-usage-report.md) affiche le nom d’origine de l’application fournie par l’éditeur.

* La boîte de dialogue de consentement d’autorisation Microsoft Graph affiche le nom d’origine de l’application fournie par l’éditeur. Il vous aide à identifier avec précision une application tout en lui fournissant des autorisations.

Les limitations sur les champs personnalisables sont les suivantes :

| Champ personnalisable | Considération |
|:---|:---|
| Tous les champs d’URL | Vérifiez les URL valides et sécurisées à l’aide de `https`. |
| Description courte | La description courte doit comporter moins de 80 caractères et ne pas répéter ce qui figure dans la description complète. |
| Icône | Icône de contour transparent au format PNG d’une résolution de 32 x 32 pixels. |
| Icône couleur | Icône de couleurs complètes au format PNG de résolution de 192 x 192 pixels. |
| Couleur de l'accentuation | La couleur doit correspondre à l’arrière-plan de votre icône. |

## <a name="reset-app-details-to-default-values"></a>Réinitialiser les détails de l’application aux valeurs par défaut

Vous pouvez réinitialiser les détails de l’application aux valeurs d’origine fournies par le développeur de l’application. L’option est disponible uniquement pour l’application que vous personnalisez.

1. Dans le Centre d’administration Teams, accédez à **Applications Teams** > **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Pour ouvrir la page de détails de l’application, sélectionnez le nom de l’application.

1. Dans le menu **Actions** , sélectionnez **Rétablir la valeur par défaut**.

   :::image type="content" source="media/reset-app-customization.png" alt-text="La capture d’écran montre l’option de réinitialisation à l’option par défaut pour une application personnalisée.":::

## <a name="related-articles"></a>Articles connexes

* [Personnaliser l’App Store de votre organisation](customize-your-app-store.md)
* [Renommer vos applications](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
