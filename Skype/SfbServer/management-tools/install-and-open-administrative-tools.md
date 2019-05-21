---
title: Installer et ouvrir les outils d’administration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique décrit comment installer et ouvrir les outils d’administration dont vous avez besoin pour déployer et gérer Skype entreprise.
ms.openlocfilehash: 612ea46fe8870944fa4b460b034bb9a7386a88bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274400"
---
# <a name="install-and-open-administrative-tools"></a>Installer et ouvrir les outils d’administration

Cette rubrique explique comment installer les outils d’administration dont vous avez besoin pour déployer et gérer Skype entreprise Server. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Skype entreprise Server. Par ailleurs, vous pouvez installer les outils d’administration sur d’autres ordinateurs, par exemple des consoles d’administration dédiées. Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou forêt que le déploiement de Skype entreprise Server que vous créez, afin de vous assurer que les étapes de préparation des services de domaine Active Directory sont déjà terminées. qui vous permet d’utiliser les outils d’administration de cet ordinateur ultérieurement pour publier votre topologie. Assurez-vous également de passer en revue les exigences nécessaires avant d’installer ou d’utiliser les outils d’administration de Skype entreprise Server. Reportez-vous à la documentation de configuration requise dans [Skype entreprise server 2019](../../SfBServer2019/plan/system-requirements.md) ou [skype entreprise Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Skype entreprise Server dans la boîte de dialogue d’installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Skype entreprise Server sera déployé sur ce lecteur également. 

## <a name="to-install-the-administrative-tools"></a>Pour installer les outils d’administration

1. Ouvrez une session en tant qu’administrateur local (configuration minimale) pour l’ordinateur sur lequel vous voulez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard dans Windows et que le contrôle de compte d’utilisateur (UAC) est activé, vous êtes invité à entrer un nom d’utilisateur et un mot de passe d’administrateur local.
2. Recherchez le support d’installation sur votre ordinateur, puis double-cliquez sur \Setup\amd64\Setup.exe.
3. Si vous êtes invité à installer Microsoft Visual C++ distribuable, cliquez sur **Oui**.
4. Dans la page Emplacement d’installation, cliquez sur **OK**. Changez de chemin d’accès à un autre emplacement ou lecteur si vous avez besoin d’installer les fichiers à un autre emplacement.

    > [!Important]
    > Si votre organisation nécessite que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Skype entreprise Server dans la boîte de dialogue d’installation. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, le reste des fichiers Skype entreprise Server sera également déployé sur ce lecteur. 

5. Sur la page contrat de licence utilisateur final, passez en revue les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est nécessaire pour pouvoir continuer.
6. Dans la page de l’Assistant Déploiement, cliquez sur **installer les outils d’administration**. 
7. Lorsque l’installation est terminée, cliquez sur **quitter**.

Pour ouvrir les outils d’administration et résoudre les problèmes liés à la topologie de Skype entreprise Server, procédez comme suit.

- [Assistant Déploiement](#deployment-wizard)
- [Générateur de topologie](#topology-builder) 
- [Panneau de configuration Skype entreprise Server](#skype-for-business-server-control-panel)
- [Skype Entreprise Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistant Déploiement

Utilisez la procédure suivante pour démarrer l’Assistant déploiement en local afin d’ajouter ou de supprimer des fichiers de composants.

**Pour démarrer l’Assistant Déploiement de Skype entreprise Server**

1. Ouvrez une session sur l’ordinateur sur lequel est installé l’Assistant Déploiement de Skype entreprise Server en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
2. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Assistant Déploiement de Skype entreprise Server**.


## <a name="topology-builder"></a>Générateur de topologie 

Utilisez la procédure suivante pour ouvrir le générateur de topologie et définir les serveurs que vous voulez déployer dans votre topologie de Skype entreprise Server.

**Pour ouvrir le générateur de topologie Skype entreprise Server et concevoir la topologie**

1. Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour lire, publier ou activer une topologie, qui est requise pour l’installation de Skype entreprise Server sur un serveur, vous devez utiliser un compte membre du groupe administrateurs de domaine et Th le groupe e RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous allez utiliser pour le stockage des fichiers d’archivage, afin que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requise ( DACL) ou un compte disposant de droits d’utilisateur équivalents.
 
2. Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.

## <a name="skype-for-business-server-control-panel"></a>Panneau de configuration Skype entreprise Server 

Utilisez l’une des procédures suivantes pour ouvrir le panneau de configuration Skype entreprise Server pour gérer la configuration des serveurs, utilisateurs, clients et appareils de votre environnement.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans le panneau de configuration Skype entreprise Server. Vous pouvez utiliser d’autres rôles pour vous connecter au panneau de configuration Skype entreprise Server et effectuer des tâches d’administration spécifiques en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour gérer l’archivage dans le panneau de configuration Skype entreprise Server. Pour plus d’informations sur les rôles, voir [planifier le contrôle d’accès basé sur un rôle](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, voir la documentation relative à la tâche. 

**Pour ouvrir le panneau de configuration Skype entreprise Server depuis n’importe quel ordinateur dans le pare-feu de votre organisation**

1. À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à n’importe quel ordinateur dans votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.

    > [!IMPORTANT]
    > Si vous avez configuré une adresse URL (Uniform Resource Locator) d’administration, vous pouvez accéder au panneau de configuration Skype entreprise Server à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur au sein du pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, voir [planification de simples URL](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) et [modification ou configuration d’URL simples](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

**Pour ouvrir le panneau de configuration Skype entreprise Server sur un ordinateur exécutant Skype entreprise Server**

1. À partir d’un compte d’utilisateur membre du rôle CsAdministrator ou d’un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à un ordinateur sur lequel vous avez installé Skype entreprise Server ou, au minimum , les outils d’administration de Skype entreprise Server. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran d’au moins 1024 x 768.
2. Démarrer le panneau de configuration Skype entreprise Server: cliquez sur **Démarrer**, **tous les programmes**, pointez sur **Outils d’administration**, pointez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Control Panel**.

## <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell 

Utilisez la procédure suivante pour ouvrir Skype entreprise Server Management Shell et administrer des serveurs, des utilisateurs, des clients et des appareils dans votre environnement à l’aide de la ligne de commande.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans Skype entreprise Server Management Shell. Vous pouvez vous connecter à l’aide d’autres rôles pour effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour exécuter des cmdlets liées à l’administration de l’archivage. Pour plus d’informations sur les rôles, voir [planifier le contrôle d’accès basé sur un rôle](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles que vous pouvez utiliser pour exécuter une applet de connexion spécifique, voir la documentation relative à l’applet de connexion.<br/><br/>Vous pouvez également exécuter certaines cmdlets en utilisant un compte d’utilisateur dans les groupes RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, en fonction de l’applet de la cmdlet. 

**Pour ouvrir Skype entreprise Server Management Shell**

Par défaut, si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, vous ne pouvez pas exécuter les applets de cmdlet Skype entreprise Server. Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, tapez les informations suivantes à l’invite de commandes Windows PowerShell:

`Import-Module Lync`

Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.
