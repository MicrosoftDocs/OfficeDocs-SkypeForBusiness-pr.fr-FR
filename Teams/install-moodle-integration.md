---
title: Installer l’intégration de Moodle à Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Découvrez comment installer et configurer l’application Moodle open source Learning Management System (LMS) pour Microsoft Teams.
keywords: Plug-in d’intégration d’application Moodle Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789539"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installation de l’intégration de Moodle à Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), le système de gestion de l’apprentissage (LMS) le plus populaire et open source au monde, est désormais intégré à Microsoft Teams ! Cette intégration permet aux enseignants et aux étudiants de collaborer autour des cours Moodle, de poser des questions sur leurs notes et devoirs et de rester informés avec les notifications , directement dans Teams !

Pour aider les administrateurs informatiques à configurer facilement cette intégration, nous avons mis à jour notre plug-in Moodle open source avec les fonctionnalités suivantes :

* Inscription automatique de votre serveur Moodle auprès d’Azure AD.
* Déploiement en un clic de votre bot Moodle Assistant sur Azure.
* Provisionnement automatique des équipes et synchronisation automatique des inscriptions d’équipe pour tous ou sélection des cours Moodle.
* Installation automatique de l’onglet Moodle et du bot Moodle Assistant dans chaque équipe synchronisée. (Bientôt disponible)
* Publication en un clic de l’application Moodle dans votre App Store Teams privé. (Bientôt disponible)

Pour en savoir plus sur les fonctionnalités fournies par cette intégration, consultez [Installation de l’intégration moodle à Microsoft Teams](/microsoftteams/platform/resources/moodleinstructions).

## <a name="prerequisites"></a>Conditions préalables

Pour installer et configurer cette application, vous avez besoin des éléments suivants :

1. Informations d’identification de l’administrateur Moodle
2. Informations d’identification de l’administrateur Azure AD
3. Un abonnement Azure dans lequel vous pouvez créer des ressources

## <a name="step-1-install-the-moodle-plugin"></a>Étape 1 : Installer le plug-in Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L’intégration moodle dans Microsoft Teams est optimisée par le open source [jeu de plug-in Moodle](https://github.com/Microsoft/o365-moodle). Pour installer le plug-in dans votre serveur Moodle :

1. Tout d’abord, téléchargez le [jeu de plug-in Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) et enregistrez-le sur votre ordinateur local. Vous devez utiliser la version 3.5 ou ultérieure.
    * L’installation du plug-in local_o365 installe également les [plug-ins auth_oidc](https://moodle.org/plugins/auth_oidc) et [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) .
1. Connectez-vous à votre serveur Moodle en tant qu’administrateur, puis sélectionnez **Administration du site** dans le volet de navigation gauche.
1. Sélectionnez l’onglet **Plug-ins** , puis cliquez sur **Installer les plug-ins**.
1. Dans la section **Installer le plug-in à partir du fichier ZIP** , cliquez sur le bouton **Choisir un fichier** .
1. Sélectionnez l’option **Charger un fichier** dans le volet de navigation gauche, recherchez le fichier que vous avez téléchargé ci-dessus, puis cliquez sur **Charger ce fichier**.
1. Sélectionnez à nouveau l’option **Administration du site** dans le volet de navigation gauche pour revenir à votre tableau de bord d’administration. Faites défiler jusqu’aux **plug-ins locaux**, puis cliquez sur le lien **d’intégration Microsoft Office 365**. Laissez cette page de configuration ouverte dans un onglet de navigateur distinct, car vous l’utiliserez tout au long du reste de ce processus.

Vous trouverez plus d’informations sur l’installation des plug-ins Moodle dans la [documentation Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Remarque importante :** Laissez votre page de configuration de plug-in Microsoft 365 ou Office 365 Moodle ouverte dans un onglet de navigateur distinct, car vous revenez à cet ensemble de pages tout au long de ce processus.

*Vous n’avez pas encore de site Moodle ?* Vous pouvez consulter notre [référentiel](https://github.com/azure/moodle) Moodle sur Azure, où vous pouvez déployer rapidement une instance Moodle sur Azure et la personnaliser en fonction de vos besoins.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Étape 2 : Configurer la connexion entre le plug-in Microsoft 365 ou Office 365 et Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Ensuite, vous devez inscrire Moodle en tant qu’application dans Azure Active Directory. Nous avons fourni un script PowerShell pour vous aider à effectuer ce processus. Le script PowerShell provisionne une nouvelle application Azure AD pour votre organisation Microsoft 365 ou Office 365, qui sera utilisée par le plug-in Moodle. Le script provisionne l’application pour votre locataire Microsoft 365 ou Office 365, configure toutes les URL de réponse et autorisations requises pour l’application approvisionnée et retourne l’ID d’application et la clé. Vous pouvez utiliser l’ID d’application et la clé générés dans votre page d’installation du plug-in Moodle pour configurer votre serveur Moodle avec Azure AD. Si vous souhaitez voir les étapes manuelles détaillées que le script PowerShell automatise, vous pouvez les trouver dans la [documentation complète du plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Onglet Moodle pour le flux d’informations Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustration de l’onglet Moodle pour le flux d’informations Microsoft Teams" />

1. Dans la page du plug-in Microsoft 365 ou Office 365 Integration, sélectionnez l’onglet **Configuration**.
1. Cliquez sur le bouton **Télécharger le script PowerShell** et enregistrez-le sur votre ordinateur local.
1. Vous devez préparer le script PowerShell à partir du fichier ZIP. Pour ce faire :
    * Téléchargez et extrayez le `Moodle-AzureAD-Powershell.zip` fichier.
    * Ouvrez le dossier extrait.
    * Cliquez avec le bouton droit sur le `Moodle-AzureAD-Script.ps1` fichier et sélectionnez **Propriétés**.
    * Sous l’onglet **Général** de l’Fenêtre Propriétés, cochez la `Unblock` case en regard de l’attribut **Sécurité** en bas.
    * Cliquez sur **OK**.
    * Copiez le chemin d’accès au répertoire du dossier extrait.
1. Ensuite, vous allez exécuter PowerShell en tant qu’administrateur :
    * Cliquez sur Démarrer.
    * Tapez PowerShell.
    * Cliquez avec le bouton droit sur Windows PowerShell.
    * Cliquez sur « Exécuter en tant qu’administrateur ».
1. Accédez au répertoire décompressé en tapant `cd ...\...\Moodle-AzureAD-Powershell` où `...\...` se trouve le chemin d’accès au répertoire.
1. Exécutez le script PowerShell en :
    * Entrez `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Entrez `.\Moodle-AzureAD-Script.ps1`.
    * Connectez-vous à votre compte d’administrateur Microsoft 365 ou Office 365 dans la fenêtre contextuelle.
    * Entrez le nom de l’application Azure AD (par exemple, Plug-in Moodle/Moodle).
    * Entrez l’URL de votre serveur Moodle.
    * Copiez **l’ID d’application** et la **clé d’application** générés par le script et enregistrez-les.
1. Ensuite, vous devez ajouter l’ID et la clé au plug-in Moodle. Revenez à la page d’administration du plug-in (administration de site > plug-ins > Intégration de Microsoft 365).
1. Sous l’onglet **Installation** , ajoutez **l’ID d’application** et la **clé d’application** que vous avez copiés précédemment, puis cliquez sur **Enregistrer les modifications**.
1. Une fois la page actualisée, vous devez maintenant voir une nouvelle section **Choisir la méthode de connexion**. Cochez la case par **défaut** , puis cliquez à nouveau sur **Enregistrer les modifications** .
1. Une fois la page actualisée, vous verrez une autre nouvelle section **Administration consentement & des informations supplémentaires**.
    * Cliquez sur le lien **Fournir Administration consentement**, entrez vos informations d’identification Microsoft 365 ou Office 365 Administrateur général, puis **acceptez** d’accorder les autorisations.
    * En regard du champ **Locataire Azure AD** , cliquez sur le bouton **Détecter** .
    * En regard de **l’URL OneDrive Entreprise** cliquez sur le bouton **Détecter**.
    * Une fois les champs renseignés, cliquez à nouveau sur le bouton **Enregistrer les modifications** .
1. Cliquez sur le bouton **Mettre à jour** pour vérifier l’installation, puis **enregistrez les modifications**.
1. Ensuite, vous devez synchroniser les utilisateurs entre votre serveur Moodle et Azure Active Directory. Selon votre environnement, vous pouvez sélectionner différentes options au cours de cette étape. Notez que la configuration que vous définissez ici s’exécute avec chaque cron Moodle exécuté (généralement une fois par jour) pour que tout reste synchronisé. Pour commencer :
    * Basculer vers **l’onglet Paramètres de synchronisation**
    * Dans la section **Synchroniser les utilisateurs avec Azure AD** , cochez les cases qui s’appliquent à votre environnement. En règle générale, vous sélectionnez au moins :
        * Créer des comptes dans Moodle pour les utilisateurs dans Azure AD
        * Mettre à jour tous les comptes dans Moodle pour les utilisateurs dans Azure AD
    * Dans la section **Restriction de création** d’utilisateurs, vous pouvez configurer un filtre pour limiter les utilisateurs Azure AD qui seront synchronisés avec Moodle.
    * La section **Mappage des champs** utilisateur vous permet de personnaliser le mappage des champs Profil utilisateur Azure AD vers Moodle.
    * Dans la section **Synchronisation Teams** , vous pouvez choisir de créer automatiquement des groupes (par exemple, Teams) pour une partie ou la totalité de vos cours Moodle existants.
1. Pour valider les travaux cron (et les exécuter manuellement si vous le souhaitez pour la première exécution), cliquez sur le lien de **la page gestion des tâches planifiées** dans la section **Synchroniser les utilisateurs avec Azure AD** . Vous accédez alors à la page **Tâches planifiées** .
    * Faites défiler vers le bas et recherchez les **utilisateurs de synchronisation du travail avec le travail Azure AD** , puis cliquez sur **Exécuter maintenant**.
    * Si vous avez choisi de créer des groupes basés sur des cours existants, vous pouvez également exécuter les **groupes d’utilisateurs Create dans Office 365** travail.
1. Revenez à la page d’administration du plug-in (Administration du site > plug-ins > Intégration de Microsoft 365) et sélectionnez la page **Paramètres Teams** . Vous devez configurer certains paramètres de sécurité pour activer l’intégration de l’application Teams.
    * Pour activer OpenID Connect, cliquez sur le lien **Gérer l’authentification** , puis cliquez sur l’icône d’œil sur la ligne **OpenId Connect** si elle est grisée.
    * Ensuite, vous devez activer l’incorporation d’images. Cliquez sur le lien **Sécurité HTTP** , puis cochez la case en regard de **Autoriser l’incorporation d’images**.
    * L’étape suivante consiste à activer les services web qui activeront les fonctionnalités de l’API Moodle. Cliquez sur le lien **Fonctionnalités avancées** , puis vérifiez que la case à cocher en regard **d’Activer les services web** est cochée.
    * Enfin, vous devez activer les services externes pour Microsoft 365 ou Office 365. Cliquez ensuite sur le lien **Services externes** :
        * Cliquez sur **Modifier** sur la ligne **Moodle Office 365 Webservices**.
        * Cochez la case en regard de **Activé**, puis cliquez sur **Enregistrer les modifications**
    * Ensuite, vous devez modifier vos autorisations utilisateur authentifiées pour leur permettre de créer des jetons de service web. Cliquez sur le **lien « Utilisateur authentifié » du rôle d’édition** . Faites défiler vers le bas et **recherchez la fonctionnalité Créer un jeton de service web** et cochez la case **Autoriser** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Étape 3 : Déployer le bot Assistant Moodle sur Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Le bot assistant Moodle gratuit pour Microsoft Teams aide les enseignants et les étudiants à répondre à des questions sur leurs cours, devoirs, notes et autres informations dans Moodle. Le bot envoie également des notifications Moodle aux étudiants et aux enseignants directement dans Teams. Ce bot est un projet open source géré par Microsoft et [disponible sur GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> Dans cette section, vous allez déployer des ressources sur votre abonnement Azure, et toutes les ressources seront configurées à l’aide du niveau **gratuit** . Selon l’utilisation de votre bot, vous devrez peut-être mettre à l’échelle ces ressources.
> Si vous souhaitez simplement utiliser l’onglet Moodle sans le bot, passez à [l’étape 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flux d’informations sur le bot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustration du flux d’informations du bot Moodle pour Microsoft Teams" />


Pour installer le bot, vous devez d’abord l’inscrire sur la [plateforme d’identités Microsoft](https://identity.microsoft.com/Landing). Cela permet à votre bot de s’authentifier auprès de vos points de terminaison Microsoft. Pour inscrire votre bot :

1. Revenez à la page d’administration du plug-in (Administration du site > plug-ins > Intégration de Microsoft 365) et sélectionnez l’onglet **Paramètres Teams** .
1. Cliquez sur le lien **Portail d’inscription d’applications Microsoft** et connectez-vous avec votre ID Microsoft.
1. Entrez un nom pour votre application (par exemple, MoodleBot) et cliquez sur le bouton **Créer** .
1. Copiez **l’ID d’application** et collez-le dans le champ **Bot Application ID** de la page **Paramètres de l’équipe** .
1. Cliquez sur le bouton **Générer un nouveau mot de passe** . Copiez le mot de passe généré et collez-le dans le champ **Mot de passe de l’application** bot sur la page **Paramètres de l’équipe** .
1. Faites défiler jusqu’au bas du formulaire, puis cliquez sur **Enregistrer les modifications**.

Maintenant que vous avez généré votre ID d’application et votre mot de passe, il est temps de déployer votre bot sur Azure. Cliquez sur le bouton **Déployer sur Azure** et remplissez le formulaire avec les informations nécessaires (l’ID d’application bot, le mot de passe de l’application bot et le secret Moodle figurent sur la page **Paramètres de l’équipe** , et les informations Azure se trouvent sur la page **d’installation** ). Une fois le formulaire rempli, cochez la case pour accepter les conditions générales, puis cliquez sur le bouton **Acheter** (toutes les ressources Azure sont déployées sur le niveau gratuit).

Une fois le déploiement des ressources terminé sur Azure, vous devez configurer le plug-in Moodle avec son point de terminaison de messagerie. Tout d’abord, vous devez obtenir le point de terminaison à partir de votre bot dans Azure. Pour ce faire :

1. Si ce n’est pas déjà fait, connectez-vous au [Portail Azure](https://portal.azure.com).
2. Dans le volet gauche, sélectionnez **Groupes de ressources**.
3. Dans la liste, sélectionnez le groupe de ressources que vous venez d’utiliser (ou que vous venez de créer) lors du déploiement de votre bot.
4. Sélectionnez la ressource **WebApp Bot** dans la liste des ressources du groupe.
5. Copiez le point **de terminaison de messagerie** à partir de la section **Vue d’ensemble** .
6. Dans Moodle, ouvrez la page **Paramètres de l’équipe** de votre plug-in Moodle.
7. Dans le champ **Bot Endpoint** , collez l’URL que vous venez de copier et remplacez les *messages* word par *webhook*. L’URL doit maintenant ressembler à `https://botname.azurewebsites.net/api/webhook`
8. Cliquez sur **Enregistrer les modifications**
9. Une fois vos modifications enregistrées, revenez à l’onglet **Paramètres de l’équipe** , cliquez sur le bouton **Télécharger le fichier manifeste** et enregistrez le package de manifeste sur votre ordinateur (vous l’utiliserez dans la section suivante).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Étape 4 : Déployer votre application Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Maintenant que votre bot est déployé sur Azure et configuré pour communiquer avec votre serveur Moodle, il est temps de déployer votre application Microsoft Teams. Pour ce faire, vous allez charger le fichier manifeste que vous avez téléchargé à partir de la page Paramètres de l’équipe du plug-in Moodle à l’étape précédente.

Avant de pouvoir installer l’application, vous devez vous assurer que les applications externes et le chargement indépendant des applications sont activés. Pour ce faire, vous pouvez suivre [ces étapes](./admin-settings.md). Une fois que vous avez vérifié que les applications externes sont activées, vous pouvez suivre les étapes ci-dessous pour déployer votre application.

1. Ouvrez Microsoft Teams.
2. Cliquez sur l’icône **Store** en bas à gauche de la barre de navigation.
3. Cliquez sur le lien **Charger une application personnalisée** dans la liste des options. *Note:* Si vous êtes connecté en tant qu’administrateur général, vous avez la possibilité de charger l’application dans l’App Store de votre organisation. Sinon, vous ne pourrez charger l’application que pour Teams dont vous faites partie (« chargement indépendant »).
4. Sélectionnez le `manifest.zip` package que vous avez téléchargé précédemment, puis cliquez sur **Enregistrer**. Si vous n’avez pas encore téléchargé le package de manifeste, vous pouvez le faire à partir de l’onglet **Paramètres de l’équipe** de la page de configuration du plug-in dans Moodle.

Maintenant que vous avez installé l’application, vous pouvez ajouter l’onglet à n’importe quel canal auquel vous avez accès. Pour ce faire, accédez au canal, cliquez sur le **+** symbole et sélectionnez votre application dans la liste. Suivez les invites pour terminer l’ajout de votre onglet de cours Moodle à un canal.

Voilà! Vous et votre équipe pouvez maintenant commencer à travailler avec vos cours Moodle directement à partir de Microsoft Teams.

Pour partager des demandes de fonctionnalités ou des commentaires avec nous, visitez notre [portail de commentaires](https://feedbackportal.microsoft.com).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
