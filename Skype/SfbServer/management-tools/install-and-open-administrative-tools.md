---
title: Installer et ouvrir les outils d’administration
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique décrit comment installer et ouvrir les outils d’administration que vous avez besoin pour déployer et gérer Skype pour les entreprises.
ms.openlocfilehash: 260d84f071558ff54511b8650868db3ebb56abcb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899476"
---
# <a name="install-and-open-administrative-tools"></a>Installer et ouvrir les outils d’administration

Cette rubrique décrit comment installer les outils d’administration que vous avez besoin pour déployer et gérer Skype pour Business Server. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Skype pour Business Server. En outre, vous pouvez installer les outils d’administration sur d’autres ordinateurs, tels que les consoles d’administration dédiés. Il est fortement recommandé que vous installez les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou de la forêt en tant que la Skype pour le déploiement de serveur d’entreprise que vous créez, pour vous assurer que la préparation des Services de domaine Active Directory étapes sont déjà terminées, qui permet d’utiliser les outils d’administration sur cet ordinateur ultérieurement pour publier votre topologie. Vérifiez également que passer en revue la configuration requise avant d’installer ou utiliser le Skype pour les outils d’administration Business Server. Consultez la configuration requise dans [Skype pour Business Server 2019](../../SfBServer2019/plan/system-requirements.md) ou [Skype pour Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si votre organisation requiert que vous recherchez Internet Information Services (IIS) et tous les Services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’installation pour la Skype pour les fichiers Business Server dans la boîte de dialogue du programme d’installation. Si vous installez les fichiers d’installation sur ce chemin d’accès, notamment OCSCore.msi, le reste de la Skype pour les fichiers Business Server sera déployé à ce lecteur également. 

## <a name="to-install-the-administrative-tools"></a>Pour installer les outils d’administration

1. Ouvrez une session en tant qu’administrateur local (configuration minimale requise) sur l’ordinateur où vous souhaitez installer les outils d’administration. Si vous êtes connecté comme un utilisateur standard de Windows et de contrôle de compte d’utilisateur (UAC) sont activés, vous serez invité l’administrateur local ou un domaine équivalent nom d’utilisateur et mot de passe.
2. Recherchez le support d’installation sur votre ordinateur, puis double-cliquez sur \Setup\amd64\Setup.exe.
3. Si vous êtes invité à installer Microsoft Visual C++ distribuable, cliquez sur **Oui**.
4. Dans la page Emplacement d’installation, cliquez sur **OK**. Modifier ce chemin d’accès vers un autre emplacement ou lecteur si vous devez disposer des fichiers vers un autre emplacement.

    > [!Important]
    > Si votre organisation requiert que vous recherchez Internet Information Services (IIS) et tous les Services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’installation pour la Skype pour les fichiers Business Server dans la boîte de dialogue du programme d’installation. Si vous installez les fichiers d’installation sur ce chemin d’accès, notamment OCSCore.msi, le reste de la Skype pour les fichiers Business Server sera déployé trop à ce lecteur. 

5. Dans la page Contrat de licence utilisateur final, passez en revue les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est requise avant de continuer.
6. Dans la page Assistant déploiement, cliquez sur **Installer les outils administrateur**. 
7. Lorsque l’installation est terminée, cliquez sur **Quitter**.

Utilisez les procédures suivantes pour ouvrir les outils d’administration et déployer, configurer ou dépanner votre Skype pour la topologie du serveur d’entreprise.

- [Assistant Déploiement](#deployment-wizard)
- [Générateur de topologie](#topology-builder) 
- [Skype pour le panneau de configuration serveur Business](#skype-for-business-server-control-panel)
- [Skype Entreprise Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistant Déploiement

Utilisez la procédure suivante pour démarrer l’Assistant Déploiement localement pour ajouter ou supprimer des fichiers de composants.

**Pour démarrer le Skype pour l’Assistant de déploiement Business Server**

1. Ouvrez une session l’ordinateur où le Skype pour l’Assistant de déploiement Business Server est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
2. Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour l’Assistant de déploiement Business Server**.


## <a name="topology-builder"></a>Générateur de topologie 

Utilisez la procédure suivante pour ouvrir le Générateur de topologie pour définir les serveurs que vous souhaitez déployer dans votre Skype pour la topologie du serveur d’entreprise.

**Pour ouvrir le Skype pour le Générateur de topologie de serveur Business à concevoir la topologie**

1. Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est un membre du groupe utilisateurs local, mais pour lire, publier ou activer une topologie qui est requis pour installer Skype pour Business Server sur un serveur, vous devez utiliser un compte qui est membre du groupe Admins du domaine et th groupe RTCUniversalServerAdmins de e et qui dispose d’autorisations Contrôle total (autrement dit, lire, écrire et modifier) sur le partage de fichiers que vous allez utiliser pour le magasin de fichiers d’archivage afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requises ( DACL), ou d’un compte disposant de droits utilisateur équivalents.
 
2. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour le Générateur de topologie Business Server**.

## <a name="skype-for-business-server-control-panel"></a>Skype pour le panneau de configuration serveur Business 

Utilisez une des procédures suivantes pour ouvrir le Skype pour Business Server Control Panel gérer la configuration des serveurs, les utilisateurs, clients et périphériques dans votre environnement.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur qui est affecté au rôle CsAdministrator pour effectuer une tâche dans le Skype pour le panneau de configuration serveur Business. Vous pouvez utiliser d’autres rôles pour vous connecter à la Skype pour Business Server Control Panel effectuer des tâches d’administration spécifiques, dépendantes de la tâche, que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour administrer l’archivage dans le Skype pour le panneau de configuration serveur Business. Pour plus d’informations sur les rôles, consultez [planification de contrôle d’accès basé sur un rôle](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, voir la documentation de la tâche. 

**Pour ouvrir le Skype pour le panneau de configuration serveur Business à partir de n’importe quel ordinateur à l’intérieur du pare-feu de votre organisation**

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsAdministrator ou autres qui dispose des droits d’utilisateur appropriés et des autorisations pour la tâche à effectuer, ouvrez une session n’importe quel ordinateur dans votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.

    > [!IMPORTANT]
    > Si vous avez configuré une administration simple uniform resource locator (URL), vous pouvez accéder à la Skype pour le panneau de configuration serveur Business à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur dans le pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, voir [planification des URL simples](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) et [modifier ou configurer des URL simples](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration configurés pour votre organisation.

**Pour ouvrir le Skype pour le panneau de configuration serveur Business sur un ordinateur exécutant Skype pour Business Server**

1. À partir d’un compte d’utilisateur qui est membre du rôle CsAdministrator ou autres qui dispose des droits d’utilisateur appropriés et des autorisations pour la tâche à effectuer, ouvrez une session sur un ordinateur sur lequel vous avez installé Skype pour Business Server ou, au minimum , le Skype pour les outils d’administration Business Server. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran minimale de 1024 x 768.
2. Démarrez Skype pour le panneau de configuration serveur Business : cliquez sur **Démarrer**, sur **Tous les programmes**, pointez sur **Outils d’administration**, pointez sur **Skype pour Business Server**, puis cliquez sur **Skype pour le panneau de configuration serveur Business**.

## <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell 

Utilisez la procédure suivante pour ouvrir le Skype pour Business Server Management Shell administrer des serveurs, les utilisateurs, clients et périphériques dans votre environnement à l’aide de la ligne de commande.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur qui est affecté au rôle CsAdministrator pour effectuer une tâche dans le Skype pour Business Server Management Shell. Vous pouvez vous connecter à l’aide d’autres rôles pour effectuer des tâches d’administration spécifiques, en fonction de la tâche, que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour exécuter les applets de commande relatives à l’administration d’archivage. Pour plus d’informations sur les rôles, consultez [planification de contrôle d’accès basé sur un rôle](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles que vous pouvez utiliser pour exécuter une applet de commande spécifique, voir la documentation de l’applet de commande.<br/><br/>Vous pouvez également exécuter certaines applets de commande en utilisant un compte d’utilisateur dans le groupe RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, selon l’applet de commande. 

**Pour ouvrir Skype pour Business Server Management Shell**

Si vous ouvrez une fenêtre Windows PowerShell, plutôt que la Skype pour Business Server Management Shell, par défaut, vous ne pouvez pas exécuter le Skype pour les applets de commande Business Server. Pour exécuter le Skype pour les applets de commande Business Server à partir de Windows PowerShell, tapez ce qui suit à l’invite de commandes Windows PowerShell :

`Import-Module Lync`

Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.
