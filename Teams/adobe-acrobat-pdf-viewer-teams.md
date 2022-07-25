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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002337"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams

> [!NOTE]
> Adobe Acrobat en tant qu’expérience PDF par défaut dans Teams est actuellement disponible uniquement en préversion publique. [Activez la préversion publique](public-preview-doc-updates.md#enable-public-preview) pour votre locataire avant d’utiliser cette fonctionnalité. Vérifiez que les utilisateurs finaux changent la version du client Teams en préversion publique pour découvrir Adobe Acrobat en tant que visionneuse PDF dans Teams.

En tant qu’administrateur, vous pouvez définir Adobe Acrobat comme application par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams. Vos utilisateurs finaux n’ont pas besoin d’un abonnement Adobe Acrobat ou d’un ID Adobe pour afficher, rechercher, commenter et annoter des fichiers PDF.

## <a name="set-up-adobe-acrobat-app"></a>Configurer l’application Adobe Acrobat

Pour configurer Adobe Acrobat en tant qu’application par défaut pour afficher les fichiers PDF, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à **l’application** > **[Teams Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Recherchez l’application Adobe Acrobat et sélectionnez **l’application Adobe Acrobat** .

   > [!NOTE]
   >
   > * Vérifiez que l’état de l’application Adobe Acrobat est défini sur **Autoriser**. Sinon, activez le bouton bascule **Autorisé** .
   > * S’il existe un paramètre administrateur existant dans la stratégie d’autorisation d’application ou les paramètres d’application à l’échelle de l’organisation qui ont bloqué l’application, veillez à autoriser l’application dans la [stratégie d’autorisation d’application](teams-app-permission-policies.md) ou [dans les paramètres d’application à l’échelle de l’organisation](teams-app-permission-policies.md).

1. Sous l’onglet **Autorisations** , **sélectionnez Vérifier l’autorisation**.

1. Sélectionnez **Accepter**.

   :::image type="content" source="media/permission-policy.png" alt-text="Capture d’écran de l’autorisation d’application dans le Centre d’administration Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>Installer l’application Adobe Acrobat pour tous les utilisateurs

Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) pour affecter et rendre l’application Adobe Acrobat disponible pour tous les utilisateurs. Cette étape déclenche un signal dans Teams pour définir l’application comme gestionnaire de fichiers par défaut pour les fichiers PDF. Pour affecter l’application Adobe Acrobat à tous les utilisateurs, procédez comme suit :

1. Dans le Centre d’administration Teams, accédez aux [**stratégies**](https://admin.teams.microsoft.com/policies/app-setup) **d’installation des applications** >  Teams.

1. Sous **l’onglet Gérer les stratégies** , sélectionnez **Global (par défaut à l’échelle de l’organisation),** puis **Modifier**.

   :::image type="content" source="media/setup-policies.png" alt-text="Capture d’écran des stratégies d’installation de l’application Adobe Acrobat dans le Centre d’administration Teams.":::

1. Sous Applications installées, sélectionnez **Ajouter des applications**.

1. Recherchez **Adobe Acrobat**, **sélectionnez Ajouter** en regard du nom de l’application, puis **sélectionnez Ajouter**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Capture d’écran montrant comment ajouter une application Adobe Acrobat pour tous les utilisateurs." lightbox="media/add-adobe-acrobat-app.png":::

1. Sélectionnez **Enregistrer**.

Après avoir sélectionné Enregistrer, l’application Adobe Acrobat est configurée avec Teams pour ouvrir tous les fichiers PDF de l’application Adobe Acrobat à partir de l’application de conversation, de canal ou de fichiers.

Si vous souhaitez autoriser de manière sélective l’application Adobe Acrobat pour quelques individus spécifiques ou pour un groupe, vous pouvez attribuer une stratégie [d’autorisation d’application personnalisée](teams-app-permission-policies.md).

Découvrez les informations suivantes sur cette fonctionnalité :

* Une fois la stratégie configurée, il faut généralement [quelques heures](teams-app-setup-policies.md) pour que l’application soit disponible pour les utilisateurs.
Une fois la stratégie configurée, l’application installée est disponible pour les utilisateurs après quelques heures.
* L’affichage des fichiers PDF épinglés dans les canaux sous la forme d’un onglet et l’affichage des fichiers PDF dans l’application Affectations continuent d’être optimisés par l’expérience Teams native.
* Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams fonctionne uniquement sur les clients de bureau et web. Il n’est pas pris en charge sur le client mobile.
* Les utilisateurs ont besoin d’un plan Adobe Acrobat pour utiliser des outils Premium tels que l’exportation pdf, l’organisation de pages, la combinaison de fichiers, la compression pdf et la protection PDF.

> [!NOTE]
> À partir du client de bureau Teams, si vous rencontrez des problèmes lors de la connexion à l’application Adobe Acrobat, vous pouvez ouvrir Teams dans le navigateur et vous connecter. Il s’agit d’un problème connu qui sera résolu d’ici septembre 2022.

## <a name="faqs"></a>Faq

* Comment supprimer l’application Adobe Acrobat du client Teams ?
  
  Les utilisateurs finaux peuvent désinstaller l’application du client Teams et l’administrateur peut supprimer l’application Adobe Acrobat de la stratégie d’installation.

* Les administrateurs peuvent-ils bloquer l’application Adobe Acrobat une fois qu’elle est définie comme gestionnaire par défaut ?
  
  Oui, mais avant que l’administrateur ne bloque l’application, supprimez la stratégie d’installation pour vous assurer que les utilisateurs finaux sont ramenés en toute sécurité à l’expérience par défaut teams.
