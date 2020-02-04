---
title: 'Lync Server 2013 : ouvrir les outils d’administration de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c1b2eec210b22bc45a27c9635507c7ad83553
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Ouvrez les outils d’administration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

Vous pouvez utiliser les procédures décrites dans cette rubrique pour ouvrir les outils d’administration pour déployer, configurer ou dépanner votre topologie Lync Server 2013.

  - Assistant Déploiement

  - Générateur de topologie

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Assistant Déploiement

Suivez la procédure ci-dessous pour démarrer l’Assistant déploiement en local afin d’ajouter ou de supprimer des fichiers de composants Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Pour démarrer l’Assistant Déploiement de Lync Server 2013

1.  Ouvrez une session sur l’ordinateur sur lequel est installé l’Assistant Déploiement de Lync Server en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement de Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Générateur de topologie

Utilisez la procédure suivante pour ouvrir le générateur de topologie et définir les serveurs que vous voulez déployer dans votre topologie Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Pour ouvrir le générateur de topologie Lync Server 2013 et concevoir la topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour lire, publier ou activer une topologie, qui est requise pour installer Lync Server 2013 sur un serveur, vous devez utiliser un compte membre du groupe administrateurs de domaine et du RTCUniv. ersalServerAdmins et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous allez utiliser pour le stockage des fichiers d’archivage, afin que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise. ou un compte disposant de droits d’utilisateur équivalents.

    
    </div>

2.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Panneau de configuration de Lync Server 2013

Utilisez l’une des procédures suivantes pour ouvrir le panneau de configuration de Lync Server 2013 pour gérer la configuration des serveurs, utilisateurs, clients et appareils de votre environnement.

<div>


> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans le panneau de configuration de Lync Server 2013. Vous pouvez utiliser d’autres rôles pour vous connecter à Lync Server 2013 panneau de configuration afin d’effectuer des tâches d’administration spécifiques en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour gérer l’archivage dans Lync Server 2013 Control Panel. Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planifier le contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, voir la documentation relative à la tâche.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Pour ouvrir le panneau de configuration Lync Server 2013 à partir de n’importe quel ordinateur dans le pare-feu de votre organisation

1.  À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à n’importe quel ordinateur dans votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous avez configuré une adresse URL (Uniform Resource Locator) d’administration, vous pouvez accéder au panneau de configuration de Lync Server 2013 à partir d’un navigateur Internet qui s’exécute sur n’importe quel ordinateur au sein du pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, voir <A href="lync-server-2013-planning-for-simple-urls.md">planification d’URL simples dans Lync server 2013</A> dans la documentation de planification et <A href="lync-server-2013-edit-or-configure-simple-urls.md">modifier ou configurer des URL simples dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Pour ouvrir le panneau de configuration de Lync Server 2013 sur un ordinateur exécutant Lync Server 2013

1.  À partir d’un compte d’utilisateur qui est membre du rôle CsAdministrator ou d’un autre rôle disposant de droits d’utilisateur et d’autorisations appropriés pour la tâche à exécuter, connectez-vous à un ordinateur sur lequel vous avez installé Lync Server 2013 ou, au minimum, Lync Server 2013 administration outils ive. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran d’au moins 1024 x 768.

2.  Démarrez le panneau de configuration de Lync Server 2013 : cliquez sur **Démarrer**, sur **tous les programmes**, pointez sur **Outils d’administration**, sur **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server 2013 Control Panel**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

Utilisez la procédure suivante pour ouvrir Lync Server 2013 Management Shell pour administrer des serveurs, des utilisateurs, des clients et des appareils dans votre environnement à l’aide de la ligne de commande.

<div>


> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer une tâche dans Lync Server 2013 Management Shell. Vous pouvez vous connecter à l’aide d’autres rôles pour effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour exécuter des cmdlets liées à l’administration de l’archivage. Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">planifier le contrôle d’accès basé sur les rôles dans Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur les rôles que vous pouvez utiliser pour exécuter une applet de connexion spécifique, voir la documentation relative à l’applet de connexion.<BR>Vous pouvez également exécuter certaines cmdlets en utilisant un compte d’utilisateur dans les groupes RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, en fonction de l’applet de la cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Pour ouvrir Lync Server 2013 Management Shell

  - Si vous ouvrez une fenêtre Windows PowerShell plutôt que Lync Server 2013 Management Shell, par défaut, vous ne pouvez pas exécuter les applets de cmdlet Lync Server 2013. Pour exécuter les applets de commande Lync Server 2013 à partir de Windows PowerShell, tapez la commande suivante à l’invite de commandes Windows PowerShell :
    
    `Import-Module Lync`

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

