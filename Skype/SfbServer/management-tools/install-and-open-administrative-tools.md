---
title: Installer et ouvrir les outils d’administration
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cette rubrique décrit comment installer et ouvrir les outils d’administration dont vous avez besoin pour déployer et gérer Skype Entreprise.
ms.openlocfilehash: a40a1617490f22c37ec2a8173118dcb289ec8ff8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743430"
---
# <a name="install-and-open-administrative-tools"></a>Installer et ouvrir les outils d’administration

Cette rubrique décrit comment installer les outils d’administration dont vous avez besoin pour déployer et gérer Skype Entreprise Server. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Skype Entreprise Server. Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées. Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement Skype Entreprise Server que vous créez, pour vous assurer que les étapes de préparation des services de domaine Active Directory sont déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur ultérieurement pour publier votre topologie. Veillez également à passer en revue les conditions requises avant d’installer ou d’utiliser les outils Skype Entreprise Server’administration. Consultez la documentation de la [Skype Entreprise Server 2019](../../SfBServer2019/plan/system-requirements.md) [ou Skype Entreprise Server 2015.](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)
 
> [!Important]
> Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Skype Entreprise Server dans la boîte de dialogue Installation. Si vous installez les fichiers d’installation sur ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Skype Entreprise Server seront également déployés sur ce lecteur. 

## <a name="to-install-the-administrative-tools"></a>Pour installer les outils d’administration

1. Connectez-vous en tant qu’administrateur local (minimum requis) à l’ordinateur sur lequel vous souhaitez installer les outils d’administration. Si vous êtes connecté en tant qu’utilisateur standard dans Windows et que le contrôle de compte d’utilisateur (UAC) est activé, vous êtes invité à utiliser l’administrateur local ou un nom d’utilisateur et un mot de passe équivalents au domaine.
2. Accédez au support d’installation sur votre ordinateur, puis double-cliquez sur \Setup\amd64\Setup.exe.
3. Si vous êtes invité à installer le Microsoft Visual C++ distribuable, cliquez sur **Oui**.
4. Dans la page Emplacement de l’installation, cliquez sur **OK.** Remplacez ce chemin par le chemin d’accès à un autre emplacement ou lecteur si vous souhaitez que les fichiers soient installés à un autre endroit.

    > [!Important]
    > Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Skype Entreprise Server dans la boîte de dialogue Installation. Si vous installez les fichiers d’installation sur ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Skype Entreprise Server seront également déployés sur ce lecteur. 

5. Dans la page Contrat de Licence Utilisateur Final, vérifiez les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est obligatoire pour continuer.
6. Dans la page Assistant Déploiement, cliquez sur **Installer les outils d’administration.** 
7. Lorsque l’installation est terminée cliquez sur **Quitter**.

Utilisez les procédures suivantes pour ouvrir les outils d’administration afin de déployer, configurer ou dépanner votre topologie Skype Entreprise Server de gestion.

- [Assistant Déploiement](#deployment-wizard)
- [Générateur de topologies](#topology-builder) 
- [Panneau de configuration Skype Entreprise Server](#skype-for-business-server-control-panel)
- [Skype Entreprise Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistant Déploiement

Utilisez la procédure suivante pour démarrer localement l’Assistant Déploiement afin d’ajouter ou de supprimer des fichiers de composants.

**Pour démarrer l’Assistant Skype Entreprise Server déploiement**

1. Log on the computer where the Skype Entreprise Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.
2. Cliquez **sur Démarrer,** sur Tous les **programmes,** **sur Skype Entreprise Server,** puis sur Skype Entreprise Server **Déploiement.**


## <a name="topology-builder"></a>Générateur de topologies 

Utilisez la procédure suivante pour ouvrir le Générateur de topologie afin de définir les serveurs que vous souhaitez déployer dans Skype Entreprise Server topologie.

**Pour ouvrir le générateur Skype Entreprise Server topologie pour concevoir la topologie**

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour lire, publier ou activer une topologie requise pour installer Skype Entreprise Server sur un serveur, vous devez utiliser un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.  et qui dispose d’autorisations de contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous allez utiliser pour le magasin de fichiers d’archivage afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DAC) requise ou un compte avec des droits d’utilisateur équivalents.
 
2. Démarrez le Générateur de topologies : **cliquez** sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **générateur de topologies.**

## <a name="skype-for-business-server-control-panel"></a>Panneau de configuration Skype Entreprise Server 

Utilisez l’une des procédures suivantes pour ouvrir le Panneau de configuration Skype Entreprise Server pour gérer la configuration des serveurs, des utilisateurs, des clients et des appareils dans votre environnement.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans le Panneau de Skype Entreprise Server de contrôle. Vous pouvez utiliser d’autres rôles pour vous connecter au Panneau de Skype Entreprise Server pour effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour administrer l’archivage dans Skype Entreprise Server panneau de Skype Entreprise Server. Pour plus d’informations sur les rôles, voir [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, voir la documentation de la tâche. 

**Pour ouvrir le Panneau de Skype Entreprise Server à partir de n’importe quel ordinateur à l’intérieur du pare-feu de votre organisation**

1. À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle qui dispose des droits et autorisations d’utilisateur appropriés pour la tâche à effectuer, connectez-vous à n’importe quel ordinateur de votre déploiement interne avec une résolution d’écran minimale de 1 024 x 768.

    > [!IMPORTANT]
    > Si vous avez configuré une URL (Uniform Resource Locator) d’administration simple, vous pouvez accéder au Panneau de configuration Skype Entreprise Server à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur du pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, voir [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) and [Edit or configure simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. Ouvrez une fenêtre du navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

**Pour ouvrir le Panneau de Skype Entreprise Server sur un ordinateur exécutant Skype Entreprise Server**

1. À partir d’un compte d’utilisateur membre du rôle CsAdministrator ou d’un autre rôle qui dispose des droits et autorisations d’utilisateur appropriés pour la tâche à effectuer, connectez-vous à un ordinateur sur lequel vous avez installé Skype Entreprise Server ou, au minimum, aux outils d’administration Skype Entreprise Server. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran minimale de 1 024 x 768.
2. Démarrez Skype Entreprise Server panneau de Skype Entreprise Server : cliquez sur **Démarrer,** sur Tous les **programmes,** pointez sur Outils d’administration, pointez sur **Skype Entreprise Server,** puis cliquez sur Skype Entreprise Server Panneau de **Skype Entreprise Server.**

## <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell 

Utilisez la procédure suivante pour ouvrir l’environnement Skype Entreprise Server Management Shell pour administrer les serveurs, les utilisateurs, les clients et les périphériques de votre environnement à l’aide de la ligne de commande.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans Skype Entreprise Server Management Shell. Vous pouvez aussi vous servir d’autres rôles pour réaliser des tâches d’administration précises en fonction de l’opération que vous devez mener. Par exemple, le rôle CSArchivingAdministrator peut vous servir à exécuter des applets de commande inhérentes à l’administration de l’archivage. Pour plus d’informations sur les rôles, voir [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Pour plus d’informations sur les rôles qu’il est possible d’utiliser pour l’exécution d’une applet de commande spécifique, voir la documentation consacrée à celle-ci.<br/><br/>Vous pouvez également exécuter certaines applets de commande à l’aide d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, selon l’applet de commande. 

**Pour ouvrir Skype Entreprise Server Management Shell**

Si vous ouvrez une fenêtre Windows PowerShell plutôt que l’Skype Entreprise Server Management Shell, vous ne pouvez pas exécuter les cmdlets Skype Entreprise Server par défaut. Pour exécuter les cmdlets Skype Entreprise Server’Windows PowerShell, tapez ce qui suit à l’invite Windows PowerShell commande suivante :

`Import-Module Lync`

Démarrez l’Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**