---
title: Installation de l’intégration de Moodle à Microsoft teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Découvrez comment installer et configurer l’application intégration de Moodle pour Microsoft teams
keywords: Plug-in d’intégration d’application Moodle teams
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c6e2d8cfb4e3932d4559a5c5c7b618189da7e57
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37572057"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installation de l’intégration de Moodle à Microsoft teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), le système de gestion de l’apprentissage (LMS), le plus populaires et open source (LMS), est désormais intégré à Microsoft Teams. Cette intégration permet aux enseignants et aux enseignants de collaborer sur les cours de Moodle, de poser des questions sur leurs notes et leurs devoirs et de rester informé grâce aux notifications--directement dans Teams.

Pour aider les administrateurs informatiques à configurer facilement cette intégration, nous avons mis à jour le plug-in Moodle d’Office 365 Open-source avec les fonctionnalités suivantes :

* Inscription automatique de votre serveur Moodle à l’aide d’Azure AD.
* Déploiement en un clic de votre bot de l’Assistant Moodle sur Azure.
* Attribution automatique d’équipes et synchronisation automatique des inscriptions d’équipe pour tous ou sélectionner les cours Moodle.
* Installation automatique de l’onglet Moodle et du robot Moodle Assistant dans chaque équipe synchronisée. (Bientôt disponible)
* Publication en un clic de l’application Moodle dans votre magasin d’applications Microsoft Teams. (Bientôt disponible)

Pour en savoir plus sur les fonctionnalités fournies par cette intégration, cliquez [ici](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle).

## <a name="prerequisites"></a>Conditions requises

Pour installer et configurer cette application, vous avez besoin des éléments suivants :

1. Informations d’identification d’administrateur moodle
2. Informations d’identification de l’administrateur Azure AD
3. Un abonnement Azure vous pouvez créer de nouvelles ressources dans

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Étape 1 : installer le plug-in Office 365 moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L’intégration de Moodle dans Microsoft teams est optimisée par le [plug-in Office 365](https://github.com/Microsoft/o365-moodle)Open source Set. Pour installer le plug-in sur votre serveur Moodle :

1. Tout d’abord, téléchargez le [jeu de plug-ins Office 365](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) , puis enregistrez-le sur votre ordinateur local. Vous devez utiliser la version 3,5 ou une version ultérieure.
    * L’installation du plug-in local_o365 installera également les plug-ins [auth_oidc](https://moodle.org/plugins/auth_oidc) et [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) .
1. Connectez-vous à votre serveur Moodle en tant qu’administrateur, puis sélectionnez **administration du site** dans le volet de navigation gauche.
1. Sélectionnez l’onglet **plug-ins** , puis cliquez sur installer les plug- **ins**.
1. Dans la section **installer le plug-in** , cliquez sur le bouton **choisir un fichier** .
1. Dans la barre de navigation gauche, sélectionnez les options **Télécharger un fichier** , recherchez le fichier que vous avez téléchargé, puis cliquez sur **Télécharger ce fichier**.
1. Sélectionnez de nouveau l’option **administration du site** dans le volet de navigation de gauche pour revenir à votre tableau de bord d’administration. Faites défiler vers le bas jusqu’à **plug-ins locaux** et cliquez sur le lien **intégration de Microsoft Office 365** . Conservez cette page de configuration ouverte dans un onglet de navigateur distinct, tel que vous pouvez l’utiliser dans le reste de ce processus.

Vous trouverez davantage d’informations sur l’installation des plug-ins Moodle dans la [documentation Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Remarque importante :** Conservez votre page de configuration du plug-in Office 365 Moodle ouverte sous un onglet de navigateur distinct, tel que vous devrez revenir à cet ensemble de pages tout au long de ce processus.

*Vous ne disposez pas déjà d’un site Moodle ?* Vous voudrez peut-être consulter notre Moodle sur Azure [référentiel Samples](https://github.com/azure/moodle) , où vous pouvez rapidement déployer une instance Moodle sur Azure et la personnaliser selon vos besoins.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Étape 2 : configurer la connexion entre le plug-in Office 365 et Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Ensuite, vous devez enregistrer Moodle en tant qu’application dans votre Azure Active Directory. Nous avons fourni un script PowerShell pour vous aider à effectuer ce processus. Le script PowerShell met en application une nouvelle application Azure AD pour votre client Office 365, qui sera utilisée par le plug-in Office 365 moodle. Le script met en service l’application pour votre client O365, configurez toutes les URL et autorisations de réponse requises pour l’application approvisionnée et renvoyez l’AppID et la clé. Vous pouvez utiliser l’AppID et la clé générés dans votre page de configuration du plug-in O365 Moodle pour configurer votre serveur Moodle avec Azure AD. Si vous souhaitez consulter les étapes manuelles détaillées du script PowerShell, vous pouvez les trouver dans la documentation complète du plug- [in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Onglet Moodle pour le flux d’informations sur Microsoft teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustration de l’onglet Moodle pour le flux d’informations sur Microsoft teams" />

1. À partir de la page du plug-in intégration de Microsoft Office 365 slect l’onglet **configuration** .
1. Cliquez sur le bouton **Télécharger le script PowerShell** et enregistrez-le sur votre ordinateur local.
1. Vous devez préparer le script PowerShell à partir du fichier ZIP. Pour ce faire :
    * Téléchargez et extrayez le `Moodle-AzureAD-Powershell.zip` fichier.
    * Ouvrez le dossier extrait.
    * Cliquez avec le bouton droit `Moodle-AzureAD-Script.ps1` sur le fichier, puis sélectionnez **Propriétés**.
    * Dans la **** boîte de dialogue Propriétés, sous l’onglet général `Unblock` , activez la case à cocher en regard de l’attribut **sécurité** en bas.
    * Cliquez sur **OK**.
    * Copiez le chemin d’accès du répertoire du dossier extrait.
1. Ensuite, vous allez exécuter PowerShell en tant qu’administrateur :
    * Cliquez sur Démarrer.
    * Tapez PowerShell.
    * Cliquez avec le bouton droit sur Windows PowerShell.
    * Cliquez sur « Exécuter en tant qu’administrateur ».
1. Naviguez jusqu’à l’annuaire décompressé `cd ...\...\Moodle-AzureAD-Powershell` en `...\...` entrant où correspond au chemin d’accès au répertoire.
1. Exécutez le script PowerShell en procédant comme suit :
    * Entrée `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Entrée `.\Moodle-AzureAD-Script.ps1`.
    * Connectez-vous à votre compte d’administrateur O365 dans la fenêtre contextuelle.
    * Entrez le nom de l’application Azure AD (par exemple, Plug-in Moodle/Moodle).
    * Entrez l’URL de votre serveur moodle.
    * Copiez l’ID de l' **application** et la clé de l' **application** générés par le script, puis enregistrez-les.
1. Ensuite, vous devez ajouter l’ID et la clé au plugin Office 365 moodle. Revenez à la page d’administration du plug-in (administration du site > plug-ins > l’intégration de Microsoft Office 365).
1. Dans l’onglet **configuration** , ajoutez l' **ID** de l’application et la clé de l' **application** copiés précédemment, puis cliquez sur **enregistrer les modifications**.
1. Dès que la page est actualisée, vous devez maintenant voir une nouvelle section **choisir une méthode de connexion**. Cliquez sur la case à cocher **par défaut** , puis cliquez de nouveau sur **enregistrer les modifications** .
1. Après la réactualisation de la page, vous verrez une autre autorisation d’administrateur de section **& des informations supplémentaires**.
    * Cliquez sur le lien **proposer un accord d’administration** , entrez vos informations d’identification d’administrateur général 365 Office3, puis cliquez sur **accepter** pour accorder les autorisations.
    * En regard du champ **client Azure ad** , cliquez sur le bouton **détecter** .
    * En regard de l' **URL OneDrive entreprise** , cliquez sur le bouton **détecter** .
    * Une fois les champs remplis, cliquez de nouveau sur le bouton **enregistrer les modifications** .
1. Cliquez sur le bouton **mettre à jour** pour confirmer l’installation, puis sur **enregistrer les modifications**.
1. Ensuite, vous devez synchroniser les utilisateurs entre votre serveur Moodle et Azure Active Directory. En fonction de votre environnement, vous pouvez sélectionner différentes options au cours de cette étape. Notez que la configuration que vous définissez ici s’exécute avec chaque Moodle de cron (généralement une fois par jour) pour que tous les éléments soient synchronisés. Pour commencer, procédez comme suit :
    * Basculer vers l' **onglet Paramètres de synchronisation**
    * Dans la section **synchroniser des utilisateurs avec Azure ad** , sélectionnez les cases à cocher qui s’appliquent à votre environnement. En règle générale, vous devez sélectionner au moins :
        * Créer des comptes dans Moodle pour les utilisateurs d’Azure AD
        * Mise à jour de tous les comptes dans Moodle pour les utilisateurs d’Azure AD
    * Dans la section **restriction de création d’utilisateurs** , vous pouvez configurer un filtre pour limiter les utilisateurs d’Azure ad qui seront synchronisés avec moodle.
    * La section **mappage de champs d’utilisateurs** vous permet de personnaliser le mappage de champs de profil utilisateur d’Azure ad moodle.
    * Dans la section **synchronisation d’équipes** , vous pouvez choisir de créer automatiquement des groupes (Teams) pour tout ou partie de vos cours Moodle existants.
1. Pour valider les tâches cron (et les exécuter manuellement si vous le souhaitez pour la première fois), cliquez sur le lien **page de gestion des tâches planifiées** dans la section **synchroniser des utilisateurs avec Azure ad** . Vous serez redirigé vers la page **tâches planifiées** .
    * Faites défiler vers le bas et recherchez le travail **synchroniser des utilisateurs avec Azure ad** , puis cliquez sur **Exécuter maintenant**.
    * Si vous avez choisi de créer des groupes en fonction de cours existants, vous pouvez également exécuter la tâche **créer des groupes d’utilisateurs dans Office 365** .
1. Revenez à la page d’administration du plug-in (administration du site > plug-ins > intégration de Microsoft Office 365) et sélectionnez la page des paramètres de l' **équipe** . Vous devez configurer des paramètres de sécurité pour activer l’intégration des applications Teams.
    * Pour activer la connexion à OpenID, cliquez sur le lien **gérer l’authentification** , puis cliquez sur l’icône d’œil dans la ligne de **connexion OpenID** s’il est grisé.
    * Ensuite, vous devez activer l’incorporation de trames. Cliquez sur le lien **sécurité http** , puis activez la case à cocher en regard de **autoriser l’incorporation de trames**.
    * L’étape suivante consiste à activer les services Web qui activeront les fonctionnalités de l’API moodle. Cliquez sur le lien **fonctionnalités avancées** , puis assurez-vous que la case à cocher en regard de **activer les services Web** est activée.
    * Pour finir, vous devez activer les services externes pour Office 365. Cliquez sur le lien **services externes** :
        * Cliquez sur **modifier** dans la ligne **Moodle Office 365 WebServices** .
        * Activez la case à cocher en regard de **activé**, puis cliquez sur **enregistrer les modifications** .
    * Ensuite, vous devez modifier vos autorisations d’utilisateur authentifié pour leur permettre de créer des jetons de service Web. Cliquez sur le lien modification de l' **utilisateur authentifié du rôle** . Faites défiler vers le bas et recherchez la fonctionnalité **créer un jeton de service Web** , puis activez la case à cocher **autoriser** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Étape 3 : déployer le robot de l’Assistant Moodle sur Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Le robot Moodle assistant gratuit pour Microsoft teams permet aux enseignants et aux étudiants de répondre à des questions sur leurs cours, leurs devoirs, leurs notes et d’autres informations dans Moodle. Le bot envoie également des notifications Moodle aux étudiants et aux enseignants directement dans Teams. Ce robot est un projet open source géré par Microsoft et est [disponible sur GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> Dans cette section, vous allez déployer des ressources sur votre abonnement Azure, et toutes les ressources seront configurées à l’aide du niveau **gratuit** . En fonction de l’utilisation de votre bot, il est possible que vous deviez mettre à l’échelle ces ressources.
> Si vous voulez simplement utiliser l’onglet Moodle sans le bot, passez à l' [étape 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flux d’information sur bot moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustration de Moodle bot pour le flux d’informations sur Microsoft teams" />


Pour installer le robot, vous devez d’abord l’enregistrer sur la [plateforme d’identité Microsoft](https://identity.microsoft.com/Landing). Cela permet à votre bot de s’authentifier auprès de vos points de terminaison Microsoft. Pour inscrire votre bot :

1. Revenez à la page d’administration du plug-in (administration du site > plug-ins > l’intégration de Microsoft Office 365), puis sélectionnez l’onglet Paramètres de l' **équipe** .
1. Cliquez sur le lien **Microsoft Application Registration Portal** et connectez-vous avec votre identifiant Microsoft.
1. Entrez un nom pour votre application (par exemple, MoodleBot) et cliquez sur le bouton **créer** .
1. Copiez l’ID de l' **application** et collez-la dans le champ **ID d’application bot** de la page Paramètres de l' **équipe** .
1. Cliquez sur le bouton **générer un nouveau mot de passe** . Copiez le mot de passe généré et collez-le dans le champ **mot de passe de l’application bot** sur la page Paramètres de l' **équipe** .
1. Faites défiler jusqu’au bas du formulaire, puis cliquez sur **enregistrer les modifications**.

À présent que vous avez généré votre ID d’application et votre mot de passe, il est temps de déployer votre bot sur Azure. Cliquez sur le bouton **déployer dans Azure** et remplissez le formulaire avec les informations nécessaires (l’ID de l’application bot, le mot de passe de l’application bot et le secret Moodle figurent dans la page Paramètres de l' **équipe** , et les informations Azure se trouvent dans la page de **configuration** ). Lorsque vous avez rempli le formulaire, cliquez sur la case à cocher pour accepter les termes et conditions, puis cliquez sur le bouton **achat** (toutes les ressources Azure sont déployées sur le niveau libre).

Une fois le déploiement des ressources vers Azure terminé, vous devez configurer le plug-in Office 365 Moodle avec le point de terminaison de la messagerie. Tout d’abord, vous devez obtenir le point de terminaison de votre bot dans Azure. Pour cela, procédez comme suit :

1. Si ce n’est pas déjà fait, connectez-vous au [portail Azure](https://portal.azure.com).
2. Dans le volet gauche, sélectionnez **groupes de ressources**.
3. Dans la liste, sélectionnez le groupe de ressources que vous venez d’utiliser (ou créé) lors du déploiement de votre bot.
4. Sélectionnez la ressource **webapp bot** dans la liste des ressources du groupe.
5. Copiez le **point de terminaison de messagerie** à partir de la section **vue d’ensemble** .
6. Dans Moodle, ouvrez la page Paramètres de l' **équipe** de votre Plugin Office 365 moodle.
7. Dans le champ **point de terminaison de robot** , collez l’URL que vous venez de copier et remplacez les *messages* Word par *webhook*. L’URL doit maintenant ressembler à`https://botname.azurewebsites.net/api/webhook`
8. Cliquez sur **enregistrer les modifications** .
9. Une fois vos modifications enregistrées, revenez à l’onglet Paramètres de l' **équipe** , cliquez sur le bouton **Télécharger le fichier manifeste** et enregistrez le package du manifeste sur votre ordinateur (vous l’utiliserez dans la section suivante).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Étape 4 : déployer votre application Microsoft teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

À présent que votre bot est déployé sur Azure et configuré pour parler sur votre serveur Moodle, il est temps de déployer votre application Microsoft Teams. Pour cela, vous devez charger le fichier manifeste que vous avez téléchargé à partir de la page des paramètres d’équipe du plug-in Office 365 Moodle de l’étape précédente.

Avant de procéder à l’installation de l’application, vous devez vous assurer que les applications externes et chargement indépendant d’applications sont activées. Pour ce faire, vous pouvez suivre [ces étapes](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings). Une fois que vous avez vérifié que les applications externes sont activées, vous pouvez suivre les étapes ci-dessous pour déployer votre application.

1. Ouvrez Microsoft Teams.
2. Cliquez sur l’icône **Store** dans le coin inférieur gauche de la barre de navigation.
3. Cliquez sur le lien **Télécharger une application personnalisée** dans la liste des options. *Remarque :* Si vous êtes connecté en tant qu’administrateur global, vous avez la possibilité de télécharger l’application dans le magasin d’applications de votre organisation, sans quoi vous ne pourrez télécharger l’application que pour les équipes dont vous faites partie (« chargement indépendant »).
4. Sélectionnez le `manifest.zip` package que vous avez téléchargé précédemment, puis cliquez sur **Enregistrer**. Si vous n’avez pas encore téléchargé le package de manifeste, vous pouvez le faire à partir de l’onglet Paramètres de l' **équipe** de la page Configuration du plug-in moodle.

Maintenant que vous avez installé l’application, vous pouvez ajouter l’onglet à n’importe quel canal auquel vous avez accès. Pour ce faire, accédez au canal, cliquez sur **+** le symbole et sélectionnez votre application dans la liste. Suivez les invites pour finaliser l’ajout de votre onglet de cours Moodle à un canal.

Voilà! Vous et votre équipe pouvez désormais commencer à utiliser vos cours Moodle directement à partir de Microsoft Teams.

Pour partager des demandes de fonctionnalité ou des commentaires avec nous, veuillez consulter notre [page vocale](https://microsoftteams.uservoice.com/forums/916759-moodle)de l’utilisateur.