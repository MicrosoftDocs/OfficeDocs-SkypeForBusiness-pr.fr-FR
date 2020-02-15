---
title: Installer et ouvrir les outils d’administration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cette rubrique explique comment installer et ouvrir les outils d’administration dont vous avez besoin pour déployer et gérer Skype entreprise.
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031068"
---
# <a name="install-and-open-administrative-tools"></a>Installer et ouvrir les outils d’administration

Cette rubrique décrit la procédure d’installation des outils d’administration nécessaires au déploiement et à la gestion de Skype entreprise Server. Les outils d’administration sont installés par défaut sur chaque serveur exécutant Skype entreprise Server. Vous pouvez également les installer sur d’autres ordinateurs, notamment des consoles d’administration dédiées. Nous vous recommandons vivement d’installer les outils d’administration sur un ordinateur qui se trouve dans le même domaine ou la même forêt que le déploiement de Skype entreprise Server que vous créez, afin de vous assurer que les étapes de préparation des services de domaine Active Directory sont déjà terminées, ce qui vous permet d’utiliser les outils d’administration sur cet ordinateur ultérieurement pour publier votre topologie. Veillez également à vérifier les conditions requises avant d’installer ou d’utiliser les outils d’administration de Skype entreprise Server. Voir la documentation sur les conditions requises dans [Skype entreprise server 2019](../../SfBServer2019/plan/system-requirements.md) ou [skype entreprise Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers de Skype entreprise Server dans la boîte de dialogue de configuration. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers du serveur Skype entreprise seront également déployés sur ce lecteur. 

## <a name="to-install-the-administrative-tools"></a>Pour installer les outils d’administration

1. Connectez-vous en tant qu’administrateur local (minimum requis) à l’ordinateur sur lequel vous souhaitez installer les outils d’administration. Si vous avez ouvert une session en tant qu’utilisateur standard dans Windows et que le contrôle de compte d’utilisateur (UAC) est activé, vous serez invité à indiquer l’administrateur local ou un nom d’utilisateur et un mot de passe équivalents.
2. Accédez au support d’installation sur votre ordinateur, puis double-cliquez sur \Setup\amd64\Setup.exe.
3. Si vous êtes invité à installer Microsoft Visual C++ Redistributable, cliquez sur **Oui**.
4. Sur la page emplacement d’installation, cliquez sur **OK**. Remplacez ce chemin par le chemin d’accès à un autre emplacement ou lecteur si vous souhaitez que les fichiers soient installés à un autre endroit.

    > [!Important]
    > Si votre organisation exige que vous localisiez Internet Information Services (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers de Skype entreprise Server dans la boîte de dialogue de configuration. Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers du serveur Skype entreprise seront également déployés sur ce lecteur. 

5. Dans la page Contrat de Licence Utilisateur Final, vérifiez les termes du contrat de licence, cliquez sur **J’accepte**, puis cliquez sur **OK**. Cette étape est obligatoire pour continuer.
6. Sur la page Assistant Déploiement, cliquez sur **installer les outils d’administration**. 
7. Lorsque l’installation est terminée cliquez sur **Quitter**.

Utilisez les procédures suivantes pour ouvrir les outils d’administration afin de déployer, configurer ou dépanner votre topologie Skype entreprise Server.

- [Assistant Déploiement](#deployment-wizard)
- [Générateur de topologies](#topology-builder) 
- [Panneau de configuration Skype Entreprise Server](#skype-for-business-server-control-panel)
- [Skype Entreprise Server Management Shell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistant Déploiement

Utilisez la procédure suivante pour démarrer l’Assistant Déploiement localement afin d’ajouter ou de supprimer des fichiers de composants.

**Pour démarrer l’Assistant Déploiement de Skype entreprise Server**

1. Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Skype entreprise Server est installé en tant que membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins.
2. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Assistant Déploiement de Skype entreprise Server**.


## <a name="topology-builder"></a>Générateur de topologies 

Utilisez la procédure suivante pour ouvrir le générateur de topologie afin de définir les serveurs que vous souhaitez déployer dans votre topologie Skype entreprise Server.

**Pour ouvrir le générateur de topologie Skype entreprise Server afin de concevoir la topologie**

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour lire, publier ou activer une topologie, qui est nécessaire pour installer Skype entreprise Server sur un serveur, vous devez utiliser un compte membre du groupe administrateurs du domaine et du groupe. le groupe e RTCUniversalServerAdmins, qui dispose des autorisations contrôle total (c’est-à-dire, lecture, écriture et modification) sur le partage de fichiers que vous allez utiliser pour le magasin de fichiers d’archivage, afin que le générateur de topologies puisse configurer la liste de contrôle d’accès discrétionnaire requise ( DACL) ou un compte doté de droits d’utilisateur équivalents.
 
2. Démarrez le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Générateur de topologie Skype entreprise Server**.

## <a name="skype-for-business-server-control-panel"></a>Panneau de configuration Skype Entreprise Server 

Utilisez l’une des procédures suivantes pour ouvrir le panneau de configuration de Skype entreprise Server afin de gérer la configuration des serveurs, des utilisateurs, des clients et des périphériques dans votre environnement.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans le panneau de configuration de Skype entreprise Server. Vous pouvez utiliser d’autres rôles pour vous connecter au panneau de configuration de Skype entreprise Server afin d’effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour administrer l’archivage dans le panneau de configuration de Skype entreprise Server. Pour plus d’informations sur les rôles, consultez la rubrique [Planning for Role-Based Access Control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, reportez-vous à la documentation de la tâche. 

**Pour ouvrir le panneau de configuration de Skype entreprise Server à partir de n’importe quel ordinateur à l’intérieur du pare-feu de votre organisation**

1. À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle disposant des droits et des autorisations d’utilisateur appropriés pour la tâche à effectuer, ouvrez une session sur un ordinateur de votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.

    > [!IMPORTANT]
    > Si vous avez configuré une URL (Uniform Resource Locator) d’administration simple, vous pouvez accéder au panneau de configuration de Skype entreprise Server à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur au sein du pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, consultez la rubrique [Planning for simple URLs](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) et [Edit or configure simple URLs](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx). 

2. Ouvrez une fenêtre du navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

**Pour ouvrir le panneau de configuration de Skype entreprise Server sur un ordinateur exécutant Skype entreprise Server**

1. À partir d’un compte d’utilisateur membre du rôle CsAdministrator ou d’un autre rôle disposant des droits et des autorisations d’utilisateur appropriés pour la tâche à effectuer, ouvrez une session sur un ordinateur sur lequel vous avez installé Skype entreprise Server ou, au minimum , les outils d’administration de Skype entreprise Server. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran minimale de 1024 x 768.
2. Démarrez le panneau de configuration de Skype entreprise Server : cliquez sur **Démarrer**, sur **tous les programmes**, pointez sur **Outils d’administration**, sur **Skype entreprise Server**, puis cliquez sur **panneau de configuration Skype entreprise Server**.

## <a name="skype-for-business-server-management-shell"></a>Skype Entreprise Server Management Shell 

Utilisez la procédure suivante pour ouvrir Skype entreprise Server Management Shell afin d’administrer les serveurs, les utilisateurs, les clients et les appareils dans votre environnement à l’aide de la ligne de commande.

> [!NOTE]
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans Skype entreprise Server Management Shell. Vous pouvez aussi vous servir d’autres rôles pour réaliser des tâches d’administration précises en fonction de l’opération que vous devez mener. Par exemple, le rôle CSArchivingAdministrator peut vous servir à exécuter des applets de commande inhérentes à l’administration de l’archivage. Pour plus d’informations sur les rôles, consultez la rubrique [Planning for Role-Based Access Control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Pour plus d’informations sur les rôles qu’il est possible d’utiliser pour l’exécution d’une applet de commande spécifique, voir la documentation consacrée à celle-ci.<br/><br/>Vous pouvez également exécuter certaines applets de commande à l’aide d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, selon l’applet de commande. 

**Pour ouvrir Skype entreprise Server Management Shell**

Si vous ouvrez une fenêtre Windows PowerShell plutôt que Skype entreprise Server Management Shell, par défaut, vous ne pouvez pas exécuter les applets de commande Skype entreprise Server. Pour exécuter les applets de commande Skype entreprise Server à partir de Windows PowerShell, tapez ce qui suit à l’invite de commandes Windows PowerShell :

`Import-Module Lync`

Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.
