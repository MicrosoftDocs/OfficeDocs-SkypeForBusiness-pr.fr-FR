---
title: Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Découvrez comment définir Adobe Acrobat en tant que visionneuse PDF par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 6a2e6c7ef80258ba07b3450ee983818f0b6ea6e1
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738770"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat en tant que visionneuse PDF par défaut dans Microsoft Teams

> [!NOTE]
> Adobe Acrobat comme expérience PDF par défaut dans Microsoft Teams est actuellement disponible uniquement en préversion publique. Pour utiliser cette fonctionnalité, les administrateurs doivent [activer la préversion publique](public-preview-doc-updates.md#enable-public-preview) pour leur client et s’assurer que les utilisateurs finaux changent la version du client Teams en préversion publique.

En tant qu’administrateur, vous pouvez définir Adobe Acrobat comme application par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams. Vos utilisateurs finaux peuvent afficher, rechercher, commenter et annoter des fichiers PDF sans abonnement Adobe Acrobat ni ID Adobe.

Pour configurer l’application Adobe Acrobat en tant que gestionnaire par défaut pour les fichiers PDF dans votre client, effectuez les étapes suivantes en tant que prérequis :

* [Autorisez l’application Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Installez l’application Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Autorisez l’application Adobe Acrobat dans votre client.

Avant de configurer l’application, assurez-vous d’autoriser l’utilisation des applications dans votre client, que vous avez spécifiquement autorisé l’application Adobe Acrobat et que les stratégies d’autorisation de l’application l’autorisent. Pour configurer Adobe Acrobat en tant qu’application par défaut pour les fichiers PDF, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à **l’application** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application Adobe Acrobat et sélectionnez-la. Elle ouvre la page des détails de l’application.

1. Sélectionnez l’onglet **Autorisations** , puis sélectionnez **Vérifier l’autorisation**.

   :::image type="content" source="media/permission-policy.png" alt-text="Capture d’écran de la stratégie de configuration d’application dans le Centre d’administration Teams" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Sélectionnez **Accepter**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installez l’application Adobe Acrobat pour tous les utilisateurs.

Pour attribuer et rendre l’application Adobe Acrobat disponible pour tous les utilisateurs, procédez comme suit :

1. Dans le Centre d’administration Teams, accédez aux **stratégies d’installation** > [**des applications Teams**](https://admin.teams.microsoft.com/policies/app-setup).

1. Sous l’onglet **Gérer les stratégies**, sélectionnez **Global (par défaut à l’échelle de l’organisation),** puis **Modifier**.

   :::image type="content" source="media/setup-policies.png" alt-text="Capture d’écran des stratégies d’installation de l’application Adobe Acrobat dans le Centre d’administration Teams":::

1. Sous Applications installées, sélectionnez **Ajouter des applications**.

1. Recherchez **Adobe Acrobat**, sélectionnez **Ajouter** à côté du nom de l’application, puis sélectionnez **Ajouter**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Capture d’écran montrant comment ajouter une application Adobe Acrobat pour tous les utilisateurs" lightbox="media/add-adobe-acrobat-app.png":::

1. Sélectionnez **Enregistrer**.

Après avoir sélectionné Enregistrer, Teams utilise l’application Adobe Acrobat comme gestionnaire de fichiers par défaut pour les fichiers PDF.

Si vous souhaitez autoriser de manière sélective l’application Adobe Acrobat pour quelques individus ou pour un groupe, vous pouvez attribuer une [stratégie personnalisée pour les autorisations d’application](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Considérations et limitations

Découvrez les informations suivantes sur cette fonctionnalité :

* Une fois la stratégie configurée, il [faut généralement quelques heures](teams-app-setup-policies.md#considerations-and-limitations) pour que l’application soit disponible pour les utilisateurs.
* L’affichage des fichiers PDF épinglés dans les canaux sous forme d’onglet et l’affichage des fichiers PDF dans l’application Devoirs continuent d’être optimisés par l’expérience Teams native.
* Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams fonctionne uniquement sur les clients de bureau et de Web. Il n’est pas pris en charge sur le client mobile.
* Les utilisateurs ont besoin d’un plan Adobe Acrobat pour utiliser les outils Premium tels que Exporter en PDF, Organiser des pages, Combiner des fichiers, Compresser les PDF et Protéger le PDF.
* Pour désinstaller l’application, les utilisateurs finaux peuvent supprimer l’application du client Teams. Les administrateurs peuvent supprimer l’application Adobe Acrobat à l’aide de la stratégie d’installation.
* Si vous bloquez l’application Adobe Acrobat, supprimez l’application de la stratégie d’installation. Il garantit que l’expérience de l’utilisateur final revient à l’utilisation de la visionneuse de fichiers PDF native.
* Si vous rencontrez des problèmes lors de la connexion à l’application Adobe Acrobat dans le client de bureau Teams, utilisez [Teams dans le navigateur](https://teams.microsoft.com/) pour vous connecter.
