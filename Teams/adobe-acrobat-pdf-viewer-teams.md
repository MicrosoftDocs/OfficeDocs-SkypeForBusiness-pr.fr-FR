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
ms.openlocfilehash: 67be332ee916f30b0341dc3ac03e047558cead0c
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343280"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Définir Adobe Acrobat comme visionneuse PDF par défaut dans Microsoft Teams

En tant qu’administrateur, vous pouvez définir Adobe Acrobat comme application par défaut pour afficher et modifier des fichiers PDF dans Microsoft Teams. Vos utilisateurs finaux peuvent afficher et rechercher les fichiers PDF. Les utilisateurs peuvent également commenter et annoter les fichiers PDF gratuitement après s’être connectés.

Pour configurer l’application Adobe Acrobat en tant que gestionnaire par défaut pour les fichiers PDF dans votre client, effectuez les étapes suivantes en tant que prérequis :

* [Autorisez l’application Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Installez l’application Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Autorisez l’application Adobe Acrobat dans votre client.

Pour configurer l’application en tant que visionneuse PDF par défaut, veillez [à autoriser l’utilisation d’une application tierce](manage-apps.md#manage-org-wide-app-settings) dans votre locataire. Suivez ensuite les instructions ci-dessous pour configurer Adobe Acrobat comme application par défaut pour les fichiers PDF.

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

1. Si vous le souhaitez, vous pouvez autoriser l’authentification unique avec Microsoft Azure Active Directory identité si vous possédez une licence d’Adobe Acrobat. Nous vous recommandons de configurer l’authentification unique en suivant les instructions fournies dans [Configurer l’identité et l’authentification unique](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Une fois la configuration terminée, Teams utilise l’application Adobe Acrobat comme gestionnaire de fichiers par défaut pour les fichiers PDF.

Si vous souhaitez autoriser de manière sélective l’application Adobe Acrobat pour quelques individus ou pour un groupe, vous utilisez des [stratégies d’autorisation d’application](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Considérations et limitations

Découvrez les informations suivantes sur cette fonctionnalité :

* Une fois la stratégie configurée, il [faut généralement quelques heures](teams-app-setup-policies.md#considerations-and-limitations) pour que l’application soit disponible pour les utilisateurs.
* L’expérience PDF native de l’application Teams est disponible pour afficher les fichiers PDF épinglés dans les canaux sous forme d’onglet et disponibles dans l’application Affectations.
* Adobe Acrobat en tant que visionneuse PDF par défaut dans Teams fonctionne uniquement sur les clients de bureau et de Web. Il n’est pas pris en charge sur le client mobile.
* Les utilisateurs ont besoin d’un plan Adobe Acrobat pour utiliser les outils Premium tels que Exporter en PDF, Organiser des pages, Combiner des fichiers, Compresser les PDF et Protéger le PDF.
* Pour désinstaller l’application, les utilisateurs finaux peuvent supprimer l’application de leur client Teams. Administration pouvez supprimer l’application Adobe Acrobat à l’aide de la stratégie de configuration.
* Si vous bloquez l’application Adobe Acrobat, supprimez l’application de la stratégie d’installation. Il garantit que l’expérience de l’utilisateur final revient à l’utilisation de la visionneuse de fichiers PDF native.
* Si vous rencontrez des problèmes pour vous connecter à l’application Adobe Acrobat dans le client de bureau Teams, utilisez [Teams dans le navigateur](https://teams.microsoft.com/) pour vous connecter.
* Connectez-vous à un [compte Adobe](https://acrobat.adobe.com/us/en/) gratuit pour commenter ou annoter les fichiers PDF. L’application dans Teams peut offrir des fonctionnalités telles que l’annotation, l’organisation, la compression et la protection des fichiers PDF. Pour obtenir la liste complète des fonctionnalités et des prérequis, consultez [Gérer les fichiers PDF dans Teams avec l’application Acrobat](https://www.adobe.com/content/dam/dx-dc/pdf/ue/acrobat-msft-teams-feature-comp-ue.pdf).
* Lorsque vous collaborez sur un document PDF, celui-ci est temporairement stocké (jusqu’à 24 heures) sur les serveurs Adobe de la région dans laquelle vous vous trouvez. Ce stockage temporaire est destiné à faciliter le traitement temporaire. Vos documents sont chiffrés de bout en bout lors du transfert de votre système de fichiers local vers le serveur et restent également chiffrés sur le serveur. consultez [Sécurité pour Acrobat](https://aka.ms/Adobe_Acrobat_Security).
