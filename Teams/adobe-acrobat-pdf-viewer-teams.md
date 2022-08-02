---
title: Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Découvrez comment définir Adobe Acrobat en tant que visionneuse PDF par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156742"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat en tant que visionneuse PDF par défaut dans Microsoft Teams

> [!NOTE]
> Adobe Acrobat comme expérience PDF par défaut dans Microsoft Teams est actuellement disponible uniquement en préversion publique. Pour utiliser cette fonctionnalité, les administrateurs doivent [activer la préversion publique](public-preview-doc-updates.md#enable-public-preview) pour leur locataire et s’assurer que les utilisateurs finaux changent la version du client Teams en préversion publique.

En tant qu’administrateur, vous pouvez définir Adobe Acrobat comme application par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams. Vos utilisateurs finaux peuvent afficher, rechercher, commenter et annoter des fichiers PDF sans abonnement Adobe Acrobat ni ID Adobe.

## <a name="set-up-adobe-acrobat-app"></a>Configurer l’application Adobe Acrobat

Avant de configurer l’application, assurez-vous d’autoriser l’utilisation des applications dans votre locataire, que vous avez spécifiquement autorisé l’application Adobe Acrobat et que les stratégies d’autorisation de l’application l’autorisent. Pour configurer Adobe Acrobat en tant qu’application par défaut pour les fichiers PDF, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à **l’application** > **[Teams Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application Adobe Acrobat et sélectionnez-la.

1. Sous l’onglet **Autorisations** , **sélectionnez Vérifier l’autorisation**.

   :::image type="content" source="media/permission-policy.png" alt-text="Capture d’écran de l’autorisation d’application dans le Centre d’administration Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Sélectionnez **Accepter**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installer l’application Adobe Acrobat pour tous les utilisateurs

Pour affecter et rendre l’application Adobe Acrobat disponible pour tous les utilisateurs, procédez comme suit :

1. Dans le Centre d’administration Teams, accédez aux [**stratégies**](https://admin.teams.microsoft.com/policies/app-setup) **d’installation des applications** >  Teams.

1. Sous **l’onglet Gérer les stratégies** , sélectionnez **Global (par défaut à l’échelle de l’organisation),** puis **Modifier**.

   :::image type="content" source="media/setup-policies.png" alt-text="Capture d’écran des stratégies d’installation de l’application Adobe Acrobat dans le Centre d’administration Teams.":::

1. Sous Applications installées, sélectionnez **Ajouter des applications**.

1. Recherchez **Adobe Acrobat**, **sélectionnez Ajouter** en regard du nom de l’application, puis **sélectionnez Ajouter**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Capture d’écran montrant comment ajouter une application Adobe Acrobat pour tous les utilisateurs." lightbox="media/add-adobe-acrobat-app.png":::

1. Sélectionnez **Enregistrer**.

Après avoir sélectionné Enregistrer, Teams utilise l’application Adobe Acrobat comme gestionnaire de fichiers par défaut pour les fichiers PDF.

Si vous souhaitez autoriser de manière sélective l’application Adobe Acrobat pour quelques personnes ou pour un groupe, vous pouvez attribuer une stratégie [d’autorisation d’application personnalisée](teams-app-permission-policies.md).

Découvrez les informations suivantes sur cette fonctionnalité :

* Une fois la stratégie configurée, il faut généralement [quelques heures](teams-app-setup-policies.md) pour que l’application soit disponible pour les utilisateurs.
* Une fois la stratégie configurée, l’application installée est disponible pour les utilisateurs après quelques heures.
* L’affichage des fichiers PDF épinglés dans les canaux sous forme d’onglet et l’affichage des fichiers PDF dans l’application Affectations continuent d’être optimisés par l’expérience Teams native.
* Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams fonctionne uniquement sur les clients de bureau et web. Il n’est pas pris en charge sur le client mobile.
* Les utilisateurs ont besoin d’un plan Adobe Acrobat pour utiliser les outils Premium tels que Exporter pdf, Organiser des pages, Combiner des fichiers, Compresser pdf et Protéger LE PDF.
* Pour désinstaller l’application, les utilisateurs finaux peuvent supprimer l’application du client Teams. Administration pouvez supprimer l’application Adobe Acrobat à l’aide de la stratégie d’installation.
* Si vous bloquez l’application Adobe Acrobat, supprimez-la de la stratégie d’installation. Il garantit que l’expérience de l’utilisateur final revient à l’utilisation de la visionneuse de fichiers PDF native.
* À partir du client de bureau Teams, si vous rencontrez des problèmes lors de la connexion à l’application Adobe Acrobat, utilisez Teams dans le navigateur pour vous connecter.
