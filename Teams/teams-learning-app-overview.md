---
title: Installer, gérer et affecter des autorisations pour l’application formations Teams (préversion privée)
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
description: Utilisez l’application formations de Microsoft teams pour créer un hub central permettant de partager, d’affecter et d’apprendre des bibliothèques de contenu au sein d’une organisation.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703425"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a>Installer, gérer et affecter des autorisations pour l’application formations Teams (préversion privée)

*Cet article contient le contenu préliminaire de l’application formations Teams, qui est en préversion privée.*

L’application Microsoft teams Learning (préversion privée) donne aux équipes et aux individus de votre organisation une partie naturelle de la journée. L’application crée un concentrateur central dans teams pour permettre aux employés de partager, d’affecter et d’apprendre des bibliothèques de contenu au sein de votre organisation. L’administrateur a défini les autorisations et autorise les sources de contenu d’apprentissage pour l’application. Le contenu de l’apprentissage peut inclure LinkedIn Learning, Microsoft Learning, formation Microsoft 365, le contenu de votre organisation stocké dans SharePoint Online et les fournisseurs tiers pris en charge par l’application.

Pour configurer l’application formations d’équipe (préversion privée), vous devez faire appel aux éléments suivants :

-   Administrateur du centre d’administration teams
-   Administration du centre d’administration 365 Microsoft (c’est-à-dire un administrateur global)
-   Administrateur de connaissances (un nouveau rôle dans le centre d’administration 365 Microsoft) qui peut être attribué à n’importe quel utilisateur de l’organisation par un administrateur général (également appelé administrateur informatique ou administrateur 365). Ce rôle gère les sources de contenu d’apprentissage de l’organisation par le biais du centre d’administration Microsoft 365.) 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a>Gérer l’application formations Teams (préversion privée) dans le centre d’administration teams

L’administrateur d’équipes installe l’application d’apprentissage en équipe (préversion privée) à partir de l’App Store et applique les stratégies de configuration, de gestion et d’autorisation des applications par le biais du centre d’administration Teams.

### <a name="manage-the-teams-learning-app-private-preview"></a>Gérer l’application formations Teams (préversion privée)

Pour gérer les paramètres de l’application, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.

   ![Navigation gauche dans le centre d’administration teams montrant les applications équipes et la section gérer les applications](media/learning-app-teams-manage-apps-nav.png)

2. Dans la page **gérer les applications** , dans la zone de recherche, tapez *apprendre* pour Rechercher l’application formations Teams (préversion publique).

   ![Page gérer les applications dans le centre d’administration Teams, montrant la zone de recherche](media/learning-app-teams-manage-apps-page.png)

3. Sur la page d' **apprentissage** :
   1. Sous **statut**, sélectionnez **autorisé** pour activer l’application.
   2. Dans l’onglet **paramètres** , dans la section paramètres de l' **application** , accédez au centre d’administration 365 Microsoft pour configurer les sources de contenu d’apprentissage.

   ![Page d’apprentissage dans le centre d’administration teams affichant les sections État et paramètres de l’application](media/learning-app-teams-learning-page.png)

4. Après avoir géré les paramètres de l' **application** , accédez à **autorisations et stratégies de configuration** pour octroyer des autorisations aux employés qui doivent avoir accès à l’application dans le cadre de la participation de votre organisation à la version d’évaluation privée.

> [!NOTE]
>  Si votre organisation est 4,0 dans le cadre du programme TAP100 Teams, il est possible que vous deviez procéder comme suit pour permettre aux utilisateurs approuvés de sonner 3,0 d’accéder à l’application formations Teams (préversion privée).

Dans le cadre de la préversion privée, l’application formations Teams (préversion privée) est publiée dans la sonnerie 3,0. Si votre organisation utilise l’anneau 4,0, vous ne verrez pas l’application dans l’App Store. Pour tester l’application, vous devez créer une stratégie d’autorisations d’applications personnalisées, définir celle-ci pour **autoriser toutes les applications** et l’affecter à des utilisateurs approuvés de 3,0.

   ![Appuyez sur-AppsPermission-plcy avec l’option autoriser toutes les applications sélectionnée](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a>Configurer les sources de contenu d’apprentissage dans le centre d’administration Microsoft 365

Les administrateurs pour le centre d’administration 365 Microsoft (par eux-mêmes ou en attribuant le rôle d’administrateur de connaissances à certaines personnes de votre organisation) peuvent gérer les paramètres liés à l’application d’apprentissage en équipe (préversion privée) et peuvent configurer les sources de contenu d’apprentissage.

> [!TIP]
> L’administrateur de connaissances doit être modérément technique et disposer d’informations d’identification d’administrateur SharePoint, de préférence à une personne qui est correctement reportée dans le cadre de l’éducation, de l’éducation, de la formation ou des employés de l’organisation.
 
L’administrateur sélectionne les sources de contenu de formation (par exemple, LinkedIn Learning ou SharePoint) qui seront disponibles dans l’application. L’administrateur configure alors ces sources pour veiller à ce que le contenu soit disponible à des fins de recherche et de découverte et puisse être consulté par les employés qui utilisent l’application.

### <a name="assign-the-knowledge-admin-role-optional"></a>Attribuer le rôle d’administrateur de connaissances [facultatif]

Ces étapes doivent être effectuées par l’administrateur pour le centre d’administration 365 Microsoft.

1.  Dans le volet de navigation de gauche du centre d’administration 365 de Microsoft, accédez à **rôles**.

2.  Dans la page **rôles** , sous l’onglet **Azure ad** , sélectionnez **administrateur de connaissances**.
 
3.  Dans la page **administration de connaissances** , dans la section **administrateurs attribués** , sélectionnez **Ajouter**, puis ajoutez la personne que vous choisissez pour le rôle.

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a>Configurer les paramètres des sources de contenu d’apprentissage pour l’application

Ces étapes doivent être effectuées par l’administrateur 365 Microsoft ou l’administrateur de connaissances.

1.  Dans le volet de navigation de gauche du centre d’administration 365 Microsoft, accédez à **paramètres** de l'  >  **organisation**.

2.  Dans la page **paramètres** , sous l’onglet **services & compléments** , sélectionnez application d' **apprentissage**.

   ![Page Paramètres dans le centre d’administration Microsoft 365 avec l’application d’apprentissage répertoriée](media/learning-app-365-settings-page.png)

3.  Dans le volet de l' **application formations** , sélectionnez les sources de contenu d’apprentissage que vous voulez configurer pour l’organisation, puis sélectionnez **Enregistrer**.

   ![Panneau d’application d’apprentissage dans le centre d’administration Microsoft 365 affichant les options de sources de contenu](media/learning-app-365-settings-learning-app-panel.png)

Parmi toutes les sources d’apprentissage qui existent, d’autres sont activées par défaut. Elles incluent les éléments suivants :

- Formations LinkedIn (contenu gratuit)
- Microsoft Apprenez
- Formation Microsoft 365

> [!NOTE]
> Si votre organisation dispose d’un abonnement de type LinkedIn Learning standard ou professionnel, le référentiel de contenu sera déverrouillé pour les employés de votre organisation. Seuls les employés qui disposent d’une autorisation pourront utiliser l’ensemble du référentiel de contenu.

D’autres sources doivent être activées ou configurées manuellement. Les sources d’apprentissage qui ne sont pas de Microsoft sont séparément sous licence de votre organisation et de la tierce partie. Vous devez vérifier que vous vous êtes inscrit (e) pour l’apprentissage pour vous et vos utilisateurs.

Pour activer ou désactiver une source de contenu d’apprentissage, activez la case à cocher en regard de la source. Si une source est activée, une coche s’affiche.

## <a name="configure-sharepoint-as-a-learning-content-source"></a>Configurer SharePoint en tant que source de contenu d’apprentissage

Vous configurez SharePoint en tant que source de contenu d’apprentissage pour l’application formations Teams (préversion privée) dans le centre d’administration 365 Microsoft.

### <a name="overview"></a>Vue d’ensemble

L’administrateur de connaissances fournit une URL de site pour permettre au service d’apprentissage de créer un référentiel de contenu d’apprentissage centralisé vide sous la forme d’une liste SharePoint structurée. Cette liste peut être utilisée par l’Organisation pour lier des liens vers des dossiers SharePoint interentreprises contenant du contenu d’apprentissage. Les administrateurs sont chargés de recueillir et de traiter une liste d’URL pour les dossiers. Ces dossiers doivent inclure uniquement du contenu qui peut être mis à disposition de l’application formations Teams (préversion privée).

### <a name="permissions"></a>Autorisations

Les URL de dossiers peuvent être collectées à partir de n’importe quel site SharePoint de l’organisation. Tout contenu figurant dans ces dossiers pourra être utilisé dans les résultats de la recherche, mais seuls les contenus pour lesquels l’employé individuel dispose d’autorisations peuvent être utilisés.
 
### <a name="learning-service"></a>Service d’apprentissage

Le service d’apprentissage utilise les URL de dossier fournies pour obtenir les métadonnées de tout le contenu stocké dans ces dossiers. Les employés peuvent rechercher et utiliser le contenu d’une entreprise dans l’application dans les 24 heures suivant la fourniture de l’URL du dossier dans le référentiel centralisé. La suppression de contenu du référentiel n’est pas prise en charge à ce stade. Le contenu en surface ne peut pas être supprimé en fournissant une nouvelle URL de site SharePoint dans le centre d’administration 365 Microsoft.

### <a name="configure-sharepoint-as-a-source"></a>Configurer SharePoint en tant que source

Ces étapes doivent être effectuées par l’administrateur Microsoft 365 ou l’administrateur de connaissances.

1.  Dans le volet de navigation de gauche du centre d’administration 365 de Microsoft, accédez à **paramètres**.
 
2.  Dans la page **paramètres** , sous l’onglet **services & compléments** , sélectionnez application d' **apprentissage**.

   ![Page Paramètres dans le centre d’administration Microsoft 365 avec l’application d’apprentissage répertoriée](media/learning-app-365-settings-page.png)

3.  Dans le volet de l' **application formations** , indiquez l’URL du site du site SharePoint sur lequel vous souhaitez que l’application crée un référentiel centralisé.

   ![Panneau de l’application formations dans le centre d’administration Microsoft 365 affichant l’option SharePoint sélectionnée](media/learning-app-365-panel-sharepoint-selected.png)

4.  Une liste SharePoint est créée automatiquement dans le site SharePoint de l’organisation fournie. Dans le volet de navigation de gauche du site SharePoint, sélectionnez formation du contenu de l' **application éducation**. 

   ![Navigation gauche dans SharePoint montrant la section du référentiel de contenu de l’application d’apprentissage](media/learning-app-content-repository-nav.png)

 
5. Dans la page du référentiel de contenu de l' **application d’apprentissage** , remplissez la liste SharePoint avec des URL vers les dossiers de contenu de formation.

   1.   Pour afficher le volet **nouveau** , sélectionnez **nouveau** . 

   ![Page du référentiel de contenu de l’application d’apprentissage dans SharePoint présentant la nouvelle option](media/learning-app-content-repository-new.png)
 
   2.   Dans le volet **nouvel élément** , dans le champ **titre** , ajoutez un nom de répertoire de votre choix. Dans le champ **URL du dossier** , ajoutez l’URL du dossier contenu d’apprentissage. Sélectionnez **Enregistrer**.

   ![Panneau nouvel élément dans SharePoint affichant les champs d’URL de titre et de dossier](media/learning-app-new-item-panel.png)

   3. La page du référentiel de contenu de l’application d’apprentissage est mise à jour avec le nouveau contenu d’apprentissage.

   ![Page du référentiel de contenu de l’application d’apprentissage dans SharePoint affichant les informations mises à jour](media/learning-app-content-repository-populated.png)


 


