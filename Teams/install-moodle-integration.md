---
title: Installer l’intégration Moodle avec Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 05/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Découvrez comment installer et configurer l’application d’intégration Moodle pour Microsoft Teams.
keywords: Plug-in d’équipes Moodle application intégration
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto: Microsoft Teams
ms.openlocfilehash: 92259a9ef01232aaeca67089b5d654fe302f1224
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2019
ms.locfileid: "34055363"
---
# <a name="install-moodle-integration-with-microsoft-teams"></a>Installer l’intégration Moodle avec Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), la source plus populaires et ouvrir Gestion système (LMS) dans le monde, est désormais intégré à Microsoft Teams ! Cette intégration permet aux formateurs et enseignants collaborent autour de cours Moodle, posent des questions sur leurs affectations et les notes et mis à jour avec les notifications--tous au sein des équipes de rester !

Pour aider les administrateurs informatiques facilement configurer cette intégration, nous avons mis à jour notre open source du plug-in Office 365 Moodle les fonctionnalités suivantes :

- Enregistrement automatique de votre serveur Moodle avec Azure AD
- Déploiement d’un seul clic de votre robot Moodle Assistant pour Azure
- Mise en service automatique des équipes et la synchronisation automatique d’inscriptions de l’équipe pour tous les ou sélectionnez Moodle cours
- Installation automatique de l’onglet Moodle et le composant WebBot Moodle Assistant dans chaque équipe synchronisé (bientôt disponible)
- Publication d’un clic de l’application Moodle dans votre magasin d’applications privé équipes (bientôt disponible)

## <a name="prerequisites"></a>Conditions requises

Pour installer et configurer cette application, que vous devez :

- Informations d’identification administrateur Moodle
- Informations d’identification administrateur AD Azure
- Un abonnement Azure que vous pouvez créer de nouvelles ressources dans

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Étape 1 : Installer le plug-in Office 365 Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L’intégration Moodle dans Microsoft Teams a été générée par la [plug-in Office 365 Moodle](https://github.com/Microsoft/o365-moodle)ouvrir la source. Pour installer le plug-in sur votre serveur Moodle :

1. Télécharger le [plug-in Office 365 définie](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) et enregistrez-le sur votre ordinateur local. Vous devez utiliser la version 3.5 ou ultérieure.
2. Se connecter à votre serveur Moodle en tant qu’administrateur, puis sélectionnez **administration du Site** dans le volet de navigation de gauche.
3. Sélectionnez l’onglet **plug-ins** , puis cliquez sur **installer le plug-ins**.
4. Dans la section **installer le plug-in à partir du fichier ZIP** , cliquez sur le bouton **Choisir un fichier** .
5. Sélectionnez les options de **télécharger un fichier** à partir du volet de navigation de gauche, recherchez le fichier que vous avez téléchargé et cliquez sur **Télécharger le fichier**.
6. Sélectionnez l’option de **l’administration de sites** à partir du volet de navigation de gauche à nouveau pour revenir à votre tableau de bord d’administration. Faites défiler jusqu'à la **plug-ins Local** , cliquez sur le lien de **L’intégration de Microsoft Office 365** . Laissez cette page de configuration ouvert dans un onglet de navigation distincte : vous utiliserez tout au long de ce processus.

Vous trouverez plus d’informations sur l’installation du plug-ins Moodle dans la [documentation Moodle](https://docs.moodle.org/34/en/Installing_plugins).

> [!IMPORTANT]
> Conserver votre page de configuration du plug-in Office 365 Moodle ouvert dans un onglet de navigation distincte : vous allez renvoyer à cet ensemble de pages de ce processus.

Vous n’avez pas déjà un site Moodle ? Vous pouvez souhaiter extraire notre Moodle sur Azure [emprunteuses](https://github.com/azure/moodle) où vous pouvez rapidement déployer une instance de Moodle sur Azure et personnalisez-le à vos besoins.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Étape 2 : Configurer la connexion entre le plug-in Office 365 et Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Ensuite, vous devez inscrire Moodle en tant qu’application dans Azure Active Directory (AD Azure). Nous avons fourni un script PowerShell pour vous aider à effectuer cette procédure. Le script PowerShell met en service un nouveau Azure application AD pour votre client Office 365, qui sera utilisé par le plug-in Office 365 Moodle. Le script sera mise en service de l’application pour votre client O365, configurer tous les l’URL de réponse requis et autorisations de l’application mis en service et renvoyer l’AppID et la clé. Vous pouvez utiliser l’AppID et la clé générée dans votre page le programme d’installation du plug-in Moodle O365 pour configurer votre serveur Moodle avec Azure AD. Si vous souhaitez voir les étapes manuelles détaillées sur l’automatisation de script PowerShell, vous trouverez les dans la [documentation pour le plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)complète.

1. Dans la page du plug-in de l’intégration de Microsoft Office 365, sélectionnez l’onglet **configuration** .
2. Cliquez sur le bouton **Télécharger un PowerShell Script** , puis enregistrez le script sur votre ordinateur local.
3. Vous devez préparer le script PowerShell à partir du fichier ZIP. Pour ce faire :
    1. Téléchargez et extrayez le fichier Moodle-AzureAD-Powershell.zip.
    2. Ouvrez le dossier d’extraction.
    3. Cliquez sur le fichier Moodle-AzureAD-Script.ps1, puis sélectionnez **Propriétés**.
    4. Sous l’onglet **Général** de la fenêtre Propriétés, cochez la case **Débloquer** en regard de l’attribut de **sécurité** en bas.
    5. Cliquez sur **OK**.
    6. Copiez le chemin d’accès du répertoire du dossier extrait.
4. Ensuite, vous allez exécuter PowerShell en tant qu’administrateur :
    1. Cliquez sur Démarrer.
    2. Type **PowerShell**.
    3. Avec le bouton droit de **Windows PowerShell**.
    4. Cliquez sur **Exécuter en tant qu’administrateur**.
5. Accédez au répertoire décompressé en tapant `cd ...\...\Moodle-AzureAD-Powershell` où `...\...` est le chemin d’accès au répertoire.
6. Exécutez le script PowerShell :
    1. Entrez `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    2. Entrez `.\Moodle-AzureAD-Script.ps1`.
    3. Connectez-vous à votre compte d’administrateur O365 dans la fenêtre contextuelle.
    4. Entrez le nom de l’application Azure AD (par exemple, le **plug-in Moodle/Moodle**).
    5. Entrez l’URL de votre serveur Moodle.
    6. Copiez **l’ID d’Application** et la **Clé d’Application** générée par le script et les enregistrer.
7. Ensuite, vous devez ajouter l’ID et la clé pour le plug-in Office 365 Moodle. Revenir à la page d’administration du plug-in (**administration du Site** > **plug-ins** > **L’intégration de Microsoft Office 365**).
8. Sous l’onglet **installation** , ajoutez **l’ID d’Application** et de la **Clé de l’Application** que vous avez copié précédemment, puis cliquez sur **Enregistrer les modifications**.
9. Une fois la page est actualisée, vous devez voir une nouvelle section appelée la **méthode de connexion choisir**. Cliquez sur la case à cocher **par défaut**, puis cliquez sur **Enregistrer les modifications**.
10. Une fois la page est actualisée, vous verrez une nouvelle section appelée **Admin consentement & des informations supplémentaires**.
    1. Cliquez sur le lien **Fournir d’administration consentement** , entrez vos informations d’identification d’administrateur Global de 365 Office3, puis cliquez sur **Accepter** pour accorder les autorisations.
    2. En regard du champ **Azure AD client** , cliquez sur le bouton **détecter** .
    3. En regard **OneDrive entreprise URL**, cliquez sur le bouton **détecter** .
    4. Une fois que les champs remplir, cliquez sur le bouton **Enregistrer les modifications** .
11. Cliquez sur le bouton de **mise à jour** pour vérifier l’installation, puis cliquez sur **Enregistrer les modifications**.
12. Ensuite, vous devez synchroniser les utilisateurs entre votre serveur Moodle et le Azure AD. Selon votre environnement, vous pouvez sélectionner des options différentes au cours de cette étape. Notez que la configuration que vous définissez ici s’exécutera avec chaque cron Moodle exécuter (généralement une fois par jour) pour tout synchroniser. Pour commencer :
    1. Basculez vers l' **onglet Paramètres de la synchronisation**.
    2. Dans la section **synchroniser les utilisateurs avec Azure AD** , activez les cases à cocher qui s’appliquent à votre environnement. En général, sélectionnez au moins :
        - **Créer des comptes dans Moodle pour les utilisateurs dans Azure AD**
        - **Mettre à jour tous les comptes de Moodle pour les utilisateurs dans Azure AD**
    3. Dans la section **Restriction de création d’utilisateur** , vous pouvez configurer un filtre pour limiter les utilisateurs Azure AD qui seront synchronisés avec Moodle.
    4. La section **Mappage de champ utilisateur** vous autorisera à personnaliser Azure AD pour le mappage du champ Moodle profil d’utilisateur.
    5. Dans la section **Synchronisation des équipes** , vous pouvez choisir de créer automatiquement des groupes (autrement dit, les équipes) pour tout ou partie des cours Moodle existants.
13. Pour valider les travaux cron (et les exécuter manuellement si vous le souhaitez, pour la première exécution), cliquez sur le lien de la **page de gestion des tâches planifiées** dans la section **synchroniser les utilisateurs avec Azure AD** . Cela vous dirige vers la page **Tâches planifiées** .
    1. Faites défiler vers le bas et recherchez le travail de **synchronisation des utilisateurs avec Azure AD** de travail et cliquez sur **Exécuter maintenant**.
    2. Si vous avez choisi de créer des groupes en fonction des cours existants, vous pouvez également exécuter la tâche **créer les groupes d’utilisateurs dans Office 365** .
14. Revenir à la page d’administration du plug-in (**administration du Site** > **plug-ins** > **L’intégration de Microsoft Office 365**), puis sélectionnez la page **Paramètres d’équipes** . Vous devez configurer certains paramètres de sécurité pour activer l’intégration de l’application équipes.
    1. Pour activer la OpenID se connecter, cliquez sur le lien **Gérer l’authentification** , cliquez sur l’icône de œil sur la ligne **OpenId se connecter** si elle est estompé.
    2. Pour activer l’incorporation de cadre, cliquez sur le lien de **Sécurité HTTP** , puis activez la case à cocher en regard de **l’incorporation de cadre autoriser**.
    3. Activer les services web (qui activera les fonctionnalités de l’API Moodle). Cliquez sur le lien de **Fonctionnalités avancées** , puis assurez-vous que la case à cocher en regard **d’activer des services web** est sélectionnée.
    4. Activer les services externes pour Office 365. Cliquez sur le lien **des services externes** , puis :
        1. Sur la ligne **Moodle Office 365 Webservices** , cliquez sur **Modifier** .
        2. Activez la case à cocher **activé**, puis cliquez sur **Enregistrer les modifications**
    5. Enfin, vous devez modifier vos autorisations utilisateur authentifié pour permettre aux utilisateurs de créer des jetons de service web. Cliquez sur le lien de **l’utilisateur authentifié de rôle modification** . Faites défiler vers le bas et recherchez la possibilité de **créer un jeton de service web** et activez la case à cocher **Autoriser** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Étape 3 : Déployer le composant WebBot Moodle Assistant dans Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Le robot Assistant Moodle gratuite pour Microsoft Teams aide enseignants et étudiants à répondre aux questions sur leurs cours, affectations, notes et d’autres informations dans Moodle. Le composant WebBot envoie également Moodle notifications aux étudiants et enseignants droit au sein des équipes. Cet outil est un projet open source mis à jour par Microsoft et est [disponible sur les référentiels](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
. Dans cette section vous allez déployer les ressources à votre abonnement Azure et toutes les ressources vont être configurés à l’aide de la couche libre. En fonction de l’utilisation de votre robot, vous devrez peut-être mettre ces ressources à l’échelle. Si vous souhaitez simplement utiliser l’onglet Moodle sans le composant WebBot, passez à [l’étape 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flux d’informations Moodle bot

Pour installer le composant WebBot, vous devez l’enregistrer sur la [Plateforme d’identité Microsoft](https://identity.microsoft.com/Landing). Cela permet à votre robot pour s’authentifier auprès de vos points de terminaison de Microsoft. Pour enregistrer votre robot :

1. Revenir à la page d’administration du plug-in (**administration du Site** > **plug-ins** > **L’intégration de Microsoft Office 365**), puis sélectionnez l’onglet **Paramètres des équipes** .
2. Cliquez sur le lien du **Portail de l’inscription d’Application Microsoft** et la connexion avec votre ID. Microsoft
3. Entrez un nom pour l’application (par exemple, MoodleBot), cliquez sur le bouton **créer** .
4. Copiez l' **ID de l’Application** et collez-le dans le champ **ID d’Application du robot** , dans la page **Paramètres de l’équipe** .
5. Cliquez sur le bouton **Générer un nouveau mot de passe** . Copiez le mot de passe généré et collez-le dans le champ **Mot de passe Bot Application** dans la page **Paramètres de l’équipe** .
6. Faites défiler vers le bas du formulaire, cliquez sur **Enregistrer les modifications**.

Maintenant que vous avez généré votre ID d’application et le mot de passe, il est temps de déployer votre robot sur Azure. Cliquez sur le bouton **déployer vers Azure** et remplissez le formulaire avec les informations nécessaires (l’ID de robot et le mot de passe sont dans la page **Paramètres de l’équipe** , et les informations Azure sont dans la page **installation** ). Une fois le formulaire rempli, cliquez sur la case à cocher pour accepter les termes du contrat, puis cliquez sur le bouton **achat** (toutes les ressources Azure sont déployés dans la couche libre).

Une fois que les ressources sont terminées déployer sur Azure, vous devez configurer le plug-in Office 365 Moodle avec son point de terminaison de messagerie. Tout d’abord, vous devez obtenir le point de terminaison à partir de votre robot dans Azure. Pour ce faire :

1. Si vous n’êtes pas déjà connecté, connectez-vous au [portail Azure](https://portal.azure.com).
2. Dans le volet gauche, sélectionnez les **groupes de ressources**.
3. Dans la liste, sélectionnez le groupe de ressources vous venez utilisé (ou créé) lors du déploiement de votre robot.
4. Sélectionnez la ressource **WebApp robot** de la liste des ressources dans le groupe.
5. Copiez **Point de terminaison de la messagerie** à partir de la section **vue d’ensemble** .
6. Dans Moodle, ouvrez la page **Paramètres de l’équipe** de votre plug-in Office 365 Moodle.
7. Dans le champ de **Point de terminaison de robot** , collez l’URL que vous venez de copier et modifier les *messages* de word à *webhook*. L’URL doit maintenant ressembler à ceci : `https://botname.azurewebsites.net/api/webhook`.
8. Cliquez sur **Enregistrer les modifications**.
9. Une fois vos modifications sont enregistrées, retournez dans l’onglet **Paramètres de l’équipe** , cliquez sur le bouton **Télécharger le fichier manifest** et enregistrer le package manifest sur votre ordinateur (vous devez l’utiliser dans l’étape suivante).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Étape 4 : Déploiement de votre application les équipes Microsoft

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Maintenant que vous avez déployé votre robot dans Azure et configuré pour communiquer avec votre serveur Moodle, il est temps de déployer votre application Teams Microsoft. Pour ce faire, vous devez charger le fichier manifeste que vous avez téléchargé à partir de la page de **Paramètres de l’équipe** du plug-in Office 365 Moodle à l’étape précédente.

Avant de pouvoir installer l’application, vous devez vous assurer que les applications externes et chargement de version test des applications est activée. Pour ce faire, procédez comme [suit](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings). Une fois que vous avez vérifié que les applications externes sont activées, suivez les étapes ci-dessous pour déployer votre application.

1. Ouvrez les équipes Microsoft.
2. Cliquez sur l’icône de la **banque** dans le coin inférieur gauche de la barre de navigation.
3. Cliquez sur le lien **télécharger une application personnalisée** à partir de la liste d’options. 
   > [!NOTE]
   > Si vous êtes connecté en tant qu’administrateur global, vous aurez la possibilité de téléchargement de l’application dans le magasin d’applications de votre organisation ; dans le cas contraire vous seulement pourrez charger l’application pour les équipes, vous êtes un composant de (*chargement de version test*).
4. Sélectionnez le package de manifest.zip que vous avez téléchargé précédemment, puis cliquez sur **Enregistrer**. Si vous n’avez pas encore téléchargé le package de manifeste, vous pouvez le faire à partir de l’onglet **Paramètres de l’équipe** de la page de configuration du plug-in dans Moodle.

Maintenant que vous disposez de l’application installée, vous pouvez ajouter l’onglet à n’importe quelle chaîne que vous avez accès à. Pour ce faire, accédez à la chaîne, cliquez sur le **+** symbole, puis sélectionnez votre application dans la liste. Suivez les invites pour terminer l’ajout de l’onglet de cours Moodle à un canal.

Voilà ! Vous et votre équipe, maintenant commencer à travailler avec vos cours Moodle directement à partir de Microsoft Teams.

Pour partager toutes les demandes de fonctionnalité nous ou fournissez des commentaires, visitez notre [page vocale de l’utilisateur](https://microsoftteams.uservoice.com/forums/916759-moodle).