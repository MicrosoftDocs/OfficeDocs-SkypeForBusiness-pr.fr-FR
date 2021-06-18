---
title: Intégration de Moodle à Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Découvrez comment installer et configurer l’application Moodle open-source Learning Management System (LMS) pour Microsoft Teams.
keywords: Plug-in d’intégration de l’application Teams Moodle
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60fabc107ba684afdf32c4eeeb0351f12dec883e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120635"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installation de l’intégration de Moodle à Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle,](https://moodle.org/)le système de gestion des formations open source le plus populaire au monde, est désormais intégré à Microsoft Teams ! Cette intégration permet aux enseignants et aux enseignants de collaborer autour de cours Moodle, de poser des questions sur leurs notes et devoirs et de rester à jour avec des notifications, directement dans Teams !

Pour aider les administrateurs informatiques à configurer facilement cette intégration, nous avons mis à jour notre plug-in Moodle open source avec les fonctionnalités suivantes :

* Enregistrement automatique de votre serveur Moodle auprès d’Azure AD.
* Déploiement en un clic de votre bot Assistant Moodle dans Azure.
* Mise en service automatique des équipes et synchronisation automatique des inscriptions aux équipes pour toutes les formations Moodle ou sélectionnez-les.
* Installation automatique de l’onglet Moodle et du robot Assistant Moodle dans chaque équipe synchronisée. (bientôt disponible)
* Publication en un clic de l’application Moodle dans votre magasin d’applications Teams privé. (bientôt disponible)

Pour en savoir plus sur les fonctionnalités que fournit cette intégration, voir Installation de l’intégration [Moodle à Microsoft Teams.](/microsoftteams/platform/resources/moodleinstructions)

## <a name="prerequisites"></a>Conditions préalables

Pour installer et configurer cette application, vous devez :

1. Informations d’identification de l’administrateur Moodle
2. Informations d’identification de l’administrateur Azure AD
3. Un abonnement Azure dans

## <a name="step-1-install-the-moodle-plugin"></a>Étape 1 : installer le plug-in Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L’intégration de Moodle dans Microsoft Teams est optimisée par le plug-in open source [Moodle.](https://github.com/Microsoft/o365-moodle) Pour installer le plug-in sur votre serveur Moodle :

1. Tout d’abord, [téléchargez le plug-in Moodle et](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) enregistrez-le sur votre ordinateur local. Vous devez utiliser la version 3.5 ou une version plus récente.
    * L’installation du local_o365 plug-in installera également les [plug-ins auth_oidc](https://moodle.org/plugins/auth_oidc) et [boost_o365Teams’équipe.](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. Connectez-vous à votre serveur Moodle en tant qu’administrateur, puis sélectionnez Administration du **site** dans le panneau de navigation gauche.
1. Sélectionnez **l’onglet Plug-ins,** puis cliquez sur **Installer les plug-ins.**
1. Sous le **plug-in d’installation de** la section Fichier ZIP, cliquez sur **le bouton Choisir un** fichier.
1. Sélectionnez **l’option Charger un fichier** dans le navigation gauche, recherchez le fichier que vous avez téléchargé ci-dessus, puis cliquez sur Télécharger ce **fichier.**
1. Sélectionnez de **nouveau l’option Administration** du site dans le panneau de navigation gauche pour revenir à votre tableau de bord d’administration. Faites défiler vers le bas **jusqu’aux plug-ins** locaux, puis cliquez sur Microsoft Office lien Intégration **365.** Gardez cette page de configuration ouverte dans un onglet de navigateur distinct, tel que vous l’utiliserez tout au long du processus.

Pour plus d’informations sur l’installation des plug-ins Moodle, voir la [documentation de Moodle.](https://docs.moodle.org/34/en/Installing_plugins)

**Remarque importante :** Gardez votre page de configuration du plug-in Microsoft 365 ou Office 365 Moodle ouverte dans un onglet de navigateur distinct, car vous revenirez à cet ensemble de pages tout au long de ce processus.

*Vous n’avez pas encore de site Moodle ?* Vous voudrez peut-être consulter notre moodle sur lepo [Azure](https://github.com/azure/moodle) où vous pouvez rapidement déployer une instance Moodle sur Azure et la personnaliser selon vos besoins.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Étape 2 : configurer la connexion entre le plug-in Microsoft 365 ou Office 365 et Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Vous devez ensuite inscrire Moodle en tant qu’application dans votre Azure Active Directory. Nous avons fourni un script PowerShell pour vous aider à effectuer ce processus. Le script PowerShell permet de dispositions une nouvelle application Azure AD pour votre organisation Microsoft 365 ou Office 365, qui sera utilisée par le plug-in Moodle. Le script configurera l’application pour votre client Microsoft 365 ou Office 365, configurera toutes les URL et autorisations de réponse requises pour l’application mise en service et retournera l’AppID et la clé. Vous pouvez utiliser l’AppID et la clé générées dans votre page de configuration du plug-in Moodle pour configurer votre serveur Moodle avec Azure AD. Si vous souhaitez consulter les étapes manuelles détaillées automatisables par le script PowerShell, vous pouvez les trouver dans la documentation complète du [plug-in.](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Onglet Moodle pour le flux d’informations de Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustration de l’onglet Moodle pour le flux d’informations de Microsoft Teams" />

1. Dans la page du plug-in Microsoft 365 ou Intégration d’Office 365, sélectionnez **l’onglet** Configuration.
1. Cliquez sur **le bouton Télécharger un script PowerShell** et enregistrez-le sur votre ordinateur local.
1. Vous devez préparer le script PowerShell à partir du fichier ZIP. Pour ce faire :
    * Téléchargez et extrayz le `Moodle-AzureAD-Powershell.zip` fichier.
    * Ouvrez le dossier extrait.
    * Cliquez avec le bouton droit sur `Moodle-AzureAD-Script.ps1` le fichier, puis sélectionnez **Propriétés.**
    * Sous **l’onglet** Général de la fenêtre Propriétés, cochez la case en regard de `Unblock` l’attribut Sécurité en bas. 
    * Cliquez sur **OK**.
    * Copiez le chemin d’accès du répertoire du dossier extrait.
1. Ensuite, vous exécuterez PowerShell en tant qu’administrateur :
    * Cliquez sur Démarrer.
    * Tapez PowerShell.
    * Cliquez avec le bouton droit sur Windows PowerShell.
    * Cliquez sur « Exécuter en tant qu’administrateur ».
1. Accédez au répertoire décompressé en tapant l’endroit où se trouve le `cd ...\...\Moodle-AzureAD-Powershell` `...\...` chemin d’accès à l’annuaire.
1. Exécutez le script PowerShell par :
    * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`Entrée.
    * `.\Moodle-AzureAD-Script.ps1`Entrée.
    * Connectez-vous à votre compte d’administrateur Microsoft 365 ou Office 365 dans la fenêtre pop-up.
    * Entrez le nom de l’application Azure AD (par exemple. Plug-in Moodle/Moodle).
    * Entrez l’URL de votre serveur Moodle.
    * Copiez **l’ID d’application** et la **clé d’application** générés par le script et enregistrez-les.
1. Vous devrez ensuite ajouter l’ID et la clé au plug-in Moodle. Revenir à la page d’administration du plug-in (> l’administration du site > l’intégration de Microsoft 365).
1. Sous **l’onglet** Configuration, ajoutez **l’ID d’application** et la clé d’application que vous avez copiées précédemment, puis cliquez **sur Enregistrer les modifications.** 
1. Une fois la page actualisée, vous devriez à présent voir une nouvelle section **Choisir la méthode de connexion.** Cliquez sur la case à cocher par **défaut,** puis cliquez **à nouveau sur** Enregistrer les modifications.
1. Une fois la page actualisée, vous verrez un autre consentement de l’administrateur de nouvelle section **& informations supplémentaires.**
    * Cliquez sur **le lien Accord** de l’administrateur, entrez vos informations d’identification  d’administrateur général Microsoft 365 ou Office 365, puis acceptez pour accorder les autorisations.
    * En regard du **champ Client Azure AD,** cliquez sur **le bouton** Détecter.
    * En **vis-à-vis de l’URL OneDrive** Entreprise, cliquez sur **le bouton** Détecter.
    * Une fois les champs remplis, cliquez à nouveau sur **le bouton** Enregistrer les modifications.
1. Cliquez sur le **bouton Mettre** à jour pour vérifier l’installation, puis **enregistrez les modifications.**
1. Vous devrez ensuite synchroniser les utilisateurs entre votre serveur Moodle et Azure Active Directory. En fonction de votre environnement, vous pouvez sélectionner différentes options au cours de cette étape. Notez que la configuration que vous définissez ici s’exécute avec chaque run Moodle cron (généralement une fois par jour) pour que tout reste synchronisé. Pour commencer :
    * Passer à **l’onglet Paramètres de synchronisation**
    * Dans la section **Synchroniser les utilisateurs avec Azure AD,** cochez les case qui s’appliquent à votre environnement. En règle générale, vous devez sélectionner au moins :
        * Créer des comptes dans Moodle pour les utilisateurs dans Azure AD
        * Mettre à jour tous les comptes dans Moodle pour les utilisateurs dans Azure AD
    * Dans la section Restriction de création d’utilisateurs, vous pouvez configurer un filtre pour limiter les utilisateurs Azure AD qui seront synchronisés avec Moodle. 
    * La section **Mappage des** champs utilisateur vous permet de personnaliser le mappage de champ Profil utilisateur Azure AD to Moodle.
    * Dans la section **Synchronisation de Teams,** vous pouvez choisir de créer automatiquement des groupes (c’est-à-dire, Teams) pour une partie ou l’ensemble de vos cours Moodle existants.
1. Pour valider les tâches de cron (et les exécuter manuellement si vous le souhaitez pour la première exécuter), cliquez sur le lien de **la page** de gestion des tâches prévues dans la section Synchroniser les utilisateurs avec **Azure AD.** Vous êtes alors sur la page **Tâches prévues.**
    * Faites défiler vers le bas et recherchez le travail Synchroniser les utilisateurs avec le travail **Azure AD,** puis cliquez **sur Exécuter maintenant.**
    * Si vous choisissez de créer des groupes sur la base de cours existants, vous pouvez également exécuter les groupes d’utilisateurs dans la **tâche Office 365.**
1. Revenir à la page d’administration du plug-in (> l’administration du site > l’intégration de Microsoft 365) et sélectionnez la page **Paramètres teams.** Vous devrez configurer certains paramètres de sécurité pour activer l’intégration de l’application Teams.
    * Pour activer OpenID Connect, cliquez sur le lien Gérer l’authentification, puis cliquez sur l’icône d’œil sur la ligne **OpenId Connect** si elle est grisée. 
    * Vous devez ensuite activer l’incorporation d’images. Cliquez sur **le lien de sécurité HTTP,** puis cochez la case en regard d’Autoriser **l’incorporation d’images.**
    * L’étape suivante consiste à activer les services web qui activeront les fonctionnalités de l’API Moodle. Cliquez sur **le lien Fonctionnalités** avancées, puis vérifiez que la case à cocher en regard d’Activer les **services web** est activée.
    * Enfin, vous devez activer les services externes pour Microsoft 365 ou Office 365. Cliquez sur le **lien Services externes,** puis sur :
        * Cliquez **sur** Modifier dans la **ligne Service web Moodle Office 365.**
        * Activez la case à cocher **en regard de Activé,** puis cliquez **sur Enregistrer les modifications**
    * Vous devrez ensuite modifier vos autorisations d’utilisateur authentifiées pour leur permettre de créer des jetons de service web. Cliquez sur **le lien Du rôle d’édition « Utilisateur authentifié** ». Faites défiler vers le bas, recherchez **la fonctionnalité Créer un jeton de service web** et cochez la **case** Autoriser.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Étape 3 : déployer le bot Assistant Moodle sur Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Le bot Assistant Moodle gratuit pour Microsoft Teams permet aux enseignants et aux étudiants de répondre à des questions sur leurs cours, devoirs, notes et autres informations dans Moodle. Le bot envoie également des notifications Moodle aux étudiants et aux enseignants directement dans Teams. Ce robot est un projet open source mis à jour par Microsoft [et disponible sur GitHub.](https://github.com/microsoft/Moodle-Teams-Bot)

> [!NOTE]
> Dans cette section, vous allez déployer les ressources dans votre abonnement Azure et toutes les ressources seront configurées au **niveau** gratuit. Selon l’utilisation de votre robot, vous devrez peut-être mettre ces ressources à l’échelle.
> Si vous voulez simplement utiliser l’onglet Moodle sans le bot, passez à [l’étape 4.](#step-4-deploy-your-microsoft-teams-app)

### <a name="moodle-bot-information-flow"></a>Flux d’informations du robot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustration du bot Moodle pour le flux d’informations de Microsoft Teams" />


Pour installer le robot, vous devez d’abord l’enregistrer sur la plateforme [identité Microsoft.](https://identity.microsoft.com/Landing) Cela permet à votre bot de s’authentifier avec vos points de terminaison Microsoft. Pour inscrire votre robot :

1. Revenir à la page d’administration du plug-in (> l’administration du site > l’intégration de Microsoft 365) et sélectionnez l’onglet **Paramètres de Teams.**
1. Cliquez sur le **lien portail d’inscription** des applications Microsoft et connectez-vous avec votre ID Microsoft.
1. Entrez un nom pour votre application (Eg. MoodleBot) et cliquez sur **le bouton** Créer.
1. Copiez **l’ID d’application** et collez-le dans le champ **ID d’application** du robot dans la page **Paramètres de l’équipe.**
1. Cliquez sur le **bouton Générer un nouveau mot de** passe. Copiez le mot de passe généré et collez-le dans le champ Mot de passe **d’application bot** dans la page **Paramètres de l’équipe.**
1. Faites défiler vers le bas du formulaire et cliquez **sur Enregistrer les modifications.**

À présent que vous avez généré vos ID et mot de passe d’application, il est temps de déployer votre robot sur Azure. Cliquez sur le bouton Déployer sur **Azure** et remplissez le formulaire avec les informations nécessaires (l’ID d’application bot, le mot de passe d’application bot et le « Moodle Secret » se trouve sur la page **Paramètres** de l’équipe et les informations Azure se trouve sur la **page** Configuration). Une fois le formulaire rempli, cliquez sur la case à cocher  pour accepter les conditions générales, puis cliquez sur le bouton Acheter (toutes les ressources Azure sont déployées au niveau gratuit).

Une fois le déploiement des ressources terminé dans Azure, vous devez configurer le plug-in Moodle avec son point de terminaison de messagerie. Tout d’abord, vous devez obtenir le point de terminaison auprès de votre robot dans Azure. Pour ce faire :

1. Si ce n’est pas déjà fait, connectez-vous au [portail Azure.](https://portal.azure.com)
2. Dans le volet gauche, **sélectionnez Groupes de ressources.**
3. Dans la liste, sélectionnez le groupe de ressources que vous avez utilisé (ou créé) lors du déploiement de votre bot.
4. Sélectionnez la **ressource WebApp Bot** dans la liste des ressources du groupe.
5. Copiez le **point de terminaison de la messagerie** à partir de la section Vue **d’ensemble.**
6. Dans Moodle, ouvrez la page **Paramètres de l’équipe** de votre plug-in Moodle.
7. Dans le **champ Point de terminaison du robot,** collez l’URL que vous viennent de copier et modifiez les *messages* en *web.* L’URL doit maintenant ressembler à `https://botname.azurewebsites.net/api/webhook`
8. Cliquez sur **Enregistrer les modifications**
9. Une fois vos modifications **enregistrées,** revenir à  l’onglet Paramètres de l’équipe, cliquer sur le bouton Télécharger le fichier manifeste et enregistrer le package manifeste sur votre ordinateur (vous l’utiliserez dans la section suivante).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Étape 4 : déployer votre application Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

À présent que votre bot est déployé dans Azure et configuré pour parler à votre serveur Moodle, il est temps de déployer votre application Microsoft Teams. Pour ce faire, vous devez charger le fichier manifeste que vous avez téléchargé à partir de la page Paramètres de l’équipe du plug-in Moodle à l’étape précédente.

Avant de pouvoir installer l’application, vous devez vous assurer que les applications externes et le chargement d’applications sont activés. Pour ce faire, vous pouvez suivre [ces étapes.](./admin-settings.md) Une fois que vous avez garanti que les applications externes sont activées, vous pouvez suivre les étapes ci-dessous pour déployer votre application.

1. Ouvrez Microsoft Teams.
2. Cliquez sur **l’icône** Store dans le bas gauche de la barre de navigation.
3. Cliquez sur **le lien Télécharger une application personnalisée** dans la liste des options. *Remarque :* Si vous êtes connecté en tant qu’administration globale, vous aurez la possibilité de télécharger l’application dans le magasin d’applications de votre organisation, sinon vous ne pourrez charger que l’application teams dont vous faites partie (le « chargement sideloading »).
4. Sélectionnez `manifest.zip` le package que vous avez précédemment téléchargé, puis cliquez sur **Enregistrer.** Si vous n’avez pas encore téléchargé le package manifeste, vous pouvez le faire à partir de l’onglet **Paramètres** de l’équipe de la page de configuration du plug-in dans Moodle.

À présent que l’application est installée, vous pouvez ajouter l’onglet à n’importe quel canal que vous avez accès. Pour ce faire, accédez au canal, cliquez sur le **+** symbole et sélectionnez votre application dans la liste. Suivez les invites pour finaliser l’ajout de votre onglet de cours Moodle à un canal.

Voilà! Vous et votre équipe pouvez maintenant commencer à utiliser vos cours Moodle directement à partir de Microsoft Teams.

Pour partager avec nous des demandes de fonctionnalité ou des commentaires, visitez notre [page User Voice.](https://microsoftteams.uservoice.com/forums/916759-moodle)