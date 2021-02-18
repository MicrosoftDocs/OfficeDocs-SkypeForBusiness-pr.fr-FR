---
title: Installer, gérer et attribuer des autorisations pour l’application Teams Learning (prévisualisation privée)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Utilisez l’application Microsoft Teams Learning pour créer un hub central d’apprentissage où les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein d’une organisation.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285618"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Installer, gérer et attribuer des autorisations pour l’application Teams Learning (prévisualisation privée)

*Cet article contient du contenu préliminaire pour l’application Teams Learning, qui est en version d’évaluation privée.*

L’application Microsoft Teams Learning (pré-version préliminaire privée) permet aux équipes et aux membres de votre organisation de faire de l’apprentissage une partie naturelle de leur journée. L’application crée un hub central dans Teams dans lequel les employés peuvent partager, attribuer et apprendre des bibliothèques de contenu au sein de votre organisation. Les administrateurs définissent des autorisations et autorisent les sources de contenu d’apprentissage pour l’application. Le contenu d’apprentissage peut inclure LinkedIn Learning, Microsoft Learn, une formation Microsoft 365, le contenu de votre organisation stocké dans SharePoint Online et des fournisseurs tiers pris en charge par l’application.

Pour configurer l’application Teams Learning (prévisualisation privée), vous devez impliquer :

-   Administrateur du Centre d’administration Teams
-   Administrateur du Centre d’administration Microsoft 365 (autrement dit, administrateur global)

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Gérer l’application Teams Learning (prévisualisation privée) dans le Centre d’administration Teams

L’administrateur Teams installe l’application Teams Learning (prévisualisation privée) à partir du magasin d’applications et applique les stratégies de configuration, de gestion et d’autorisations de l’application via le Centre d’administration Teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Gérer l’application Teams Learning (prévisualisation privée)

Pour gérer les paramètres de l’application, suivez ces étapes :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **l’application Teams** Gérer  >  **les applications.**

   ![Navigation gauche dans le Centre d’administration Teams affichant les applications Teams et la section Gérer les applications](media/learning-app-teams-manage-apps-nav.png)

2. Dans la page **Gérer les applications,** dans la zone de recherche, tapez *Apprentissage* pour rechercher l’application Teams Learning (prévisualisation privée).

   ![Page Gérer les applications dans le Centre d’administration Teams affichant la zone de recherche](media/learning-app-teams-manage-apps-page.png)

3. Sur la page **Apprentissage** :
   1. Sous **État,** **sélectionnez Autorisé** pour activer l’application.
   2. Sous **l’onglet Paramètres,** dans la section **Paramètres** des applications, allez au Centre d’administration Microsoft 365 pour configurer les sources de contenu d’apprentissage.

   ![Page d’apprentissage dans le Centre d’administration Teams affichant la section Paramètres de statut et d’application](media/learning-app-teams-learning-page.png)

4. Après  avoir gérer les paramètres de l’application, accédez aux autorisations et aux stratégies de configuration pour accorder des **autorisations** aux employés qui doivent avoir accès à l’application dans le cadre de la participation de votre organisation à la prévisualisation privée.

> [!NOTE]
>  Si votre organisation fait partie de l’anneau 4.0 dans le cadre du programme Teams TAP100, vous devrez peut-être faire ce qui suit pour permettre aux utilisateurs approuvés de l’anneau 3.0 d’accéder à l’application Teams Learning (prévisualisation privée).

Dans le cadre de la prévisualisation privée, l’application Teams Learning (prévisualisation privée) est publiée dans l’anneau 3.0. Si votre organisation est sous l’anneau 4.0, l’application n’est pas dans l’App Store. Pour tester l’application, vous devez créer une stratégie d’autorisation d’applications personnalisée, la définir sur Autoriser toutes les applications et l’affecter aux utilisateurs approuvés Ring 3.0.

   ![Page TAP-AppsPermission-Plcy affichant l’affichage Autoriser toutes les applications sélectionné](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurer des sources de contenu d’apprentissage dans le Centre d’administration Microsoft 365

Les administrateurs du Centre d’administration Microsoft 365 peuvent gérer les paramètres liés à l’application Teams Learning (prévisualisation privée) et configurer les sources de contenu d’apprentissage.

L’administrateur peut sélectionner les sources de contenu d’apprentissage supplémentaires (par exemple, SharePoint ou les sources de fournisseurs de contenu tiers pris en charge) qui seront disponibles pour les utilisateurs de l’application. L’administrateur configure ensuite ces sources pour s’assurer que le contenu est disponible pour la recherche et la découverte et peut être consulté par les employés qui utilisent l’application.

> [!NOTE]
>  Les utilisateurs se connectent aux apprentissages non-Microsoft et LinkedIn Learning Pro dans un navigateur ou une visionneuse incorporée. Cet apprentissage configuré est soumis aux conditions distinctes de licence, de confidentialité et de service entre votre organisation et le tiers, et non aux conditions d’apprentissage (prévisualisation). Avant de sélectionner cet apprentissage dans Learning (Preview), vérifiez que vous avez un contrat en place pour votre organisation et les utilisateurs.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Configurer les paramètres des sources de contenu d’apprentissage pour l’application

Ces étapes doivent être effectuées par l’administrateur Microsoft 365.

1.  Dans le panneau de navigation gauche du Centre d’administration Microsoft 365, allez dans  >  **Paramètres de l’organisation.**

2.  Dans la page **Paramètres,** dans l’onglet & des **modules,** sélectionnez **Application d’apprentissage.**

   ![Page Paramètres du Centre d’administration Microsoft 365 affichant l’application Learning répertoriée](media/learning-app-365-settings-page.png)

3.  Dans le **panneau Application d’apprentissage,** sélectionnez les sources de contenu d’apprentissage que vous voulez configurer pour l’organisation, puis **sélectionnez Enregistrer.**

   ![Panneau des applications d’apprentissage dans le Centre d’administration Microsoft 365 affichant les options de sources de contenu](media/learning-app-365-settings-learning-app-panel.png)

Parmi toutes les sources d’apprentissage existantes, certaines seront activées par défaut. Elles incluent les éléments suivants :

- LinkedIn Learning (contenu gratuit)
- Microsoft Learn
- Formation Microsoft 365

> [!NOTE]
> Si votre organisation a un abonnement LinkedIn Learning Standard ou Professionnel, le référentiel de contenu sera déverrouillé pour les employés de votre organisation. Seuls les employés autorisés pourront utiliser l’ensemble du référentiel de contenu.

D’autres sources doivent peut-être être activées ou configurées manuellement. Les sources d’apprentissage qui ne sont pas de Microsoft sont sous licence distinctes entre votre organisation et le tiers. Vous devrez vérifier que vous êtes inscrit à l’apprentissage pour vous et vos utilisateurs.

Pour activer ou désactiver une source de contenu d’apprentissage, activez la case à cocher en regard de la source. Si une source est activée, une coche est visible.

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a>Configurer SharePoint comme source de contenu d’apprentissage (bientôt disponible)

Vous configurez SharePoint comme source de contenu d’apprentissage pour l’application Teams Learning (prévisualisation privée) dans le Centre d’administration Microsoft 365.

### <a name="overview"></a>Présentation

L’administrateur fournit une URL de site dans laquelle le service d’apprentissage peut créer un référentiel de contenu d’apprentissage centralisé vide sous la forme d’une liste SharePoint structurée. Cette liste peut être utilisée par l’organisation pour contenir des liens vers des dossiers SharePoint entre entreprises contenant du contenu pédagogique. Les administrateurs sont responsables de la collecte et de l’organisation d’une liste d’URL pour les dossiers. Ces dossiers doivent inclure uniquement le contenu qui peut être mis à disposition dans l’application Teams Learning (prévisualisation privée).

### <a name="permissions"></a>Autorisations

Les URL des dossiers peuvent être collectées à partir de n’importe quel site SharePoint de l’organisation. Tout contenu de ces dossiers pourra faire l’effet d’une recherche, mais seul le contenu auquel l’employé dispose des autorisations individuelles peut être utilisé.
 
### <a name="learning-service"></a>Service d’apprentissage

Le service d’apprentissage utilise les URL des dossiers fournis pour obtenir les métadonnées de tout le contenu stocké dans ces dossiers. Après 24 heures de fourniture de l’URL du dossier dans le référentiel centralisé, les employés peuvent rechercher et utiliser le contenu de l’entreprise au sein de l’application. À ce stade, la suppression du contenu du référentiel n’est pas prise en charge. Le contenu accidentellement surface ne peut être supprimé qu’en fournissant une nouvelle URL de site SharePoint dans le Centre d’administration Microsoft 365.

### <a name="configure-sharepoint-as-a-source"></a>Configurer SharePoint en tant que source

Ces étapes doivent être effectuées par l’administrateur Microsoft 365.

1.  Dans le panneau de navigation gauche du Centre d’administration Microsoft 365, allez dans **Paramètres.**
 
2.  Dans la page **Paramètres,** dans l’onglet & des **modules,** sélectionnez **Application d’apprentissage.**

   ![Page Paramètres du Centre d’administration Microsoft 365 affichant l’application Learning répertoriée](media/learning-app-365-settings-page.png)

3.  Dans le **panneau Application d’apprentissage,** fournissez l’URL du site au site SharePoint où vous souhaitez que l’application crée un référentiel centralisé.

   ![Panneau de l’application d’apprentissage dans le Centre d’administration Microsoft 365 avec SharePoint sélectionné](media/learning-app-365-panel-sharepoint-selected.png)

4.  Une liste SharePoint est créée automatiquement dans le site SharePoint de l’organisation fournie. Dans le navigation gauche du site SharePoint, sélectionnez Référentiel de **contenu d’application d’apprentissage.** 

   ![Navigation gauche dans SharePoint affichant la section Référentiel de contenu d’application d’apprentissage](media/learning-app-content-repository-nav.png)

 
5. Dans la page **Référentiel** de contenu d’application d’apprentissage, insérez la liste SharePoint avec des URL dans les dossiers de contenu d’apprentissage.

   1.   Sélectionnez Nouveau pour afficher **le panneau Nouvel** élément.  

   ![Page référentiel de contenu d’application d’apprentissage dans SharePoint affichant l’option Nouvelle](media/learning-app-content-repository-new.png)
 
   2.   Dans le **panneau Nouvel élément,** dans le champ **Titre,** ajoutez le nom d’annuaire de votre choix. Dans le champ **URL du** dossier, ajoutez l’URL au dossier de contenu d’apprentissage. Sélectionnez **Enregistrer**.

   ![Panneau Nouvel élément dans SharePoint affichant les champs URL de titre et de dossier](media/learning-app-new-item-panel.png)

   3. La page référentiel de contenu des applications d’apprentissage est mise à jour avec le nouveau contenu d’apprentissage.

   ![Page référentiel de contenu d’application d’apprentissage dans SharePoint affichant les informations mises à jour](media/learning-app-content-repository-populated.png)


 


