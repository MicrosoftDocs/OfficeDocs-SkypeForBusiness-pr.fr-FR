---
title: 'Lync Server 2013 : ouvrir les outils d’administration Lync Server'
description: 'Lync Server 2013 : Ouvrez les outils d’administration Lync Server.'
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
ms.openlocfilehash: 01cf0dc0c17686e2b1c7bee17bdc383ab6247909
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544760"
---
# <a name="open-lync-server-2013-administrative-tools"></a>Ouvrir les outils d’administration de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

Vous pouvez utiliser les procédures de cette rubrique pour ouvrir outils d’administration afin de déployer, configurer ou dépanner votre topologie Lync Server 2013.

  - Assistant Déploiement

  - Générateur de topologies

  - Panneau de configuration Lync Server

  - Lync Server Management Shell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Assistant Déploiement

Utilisez la procédure suivante pour démarrer l’Assistant Déploiement localement afin d’ajouter ou de supprimer des fichiers de composants Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Pour démarrer l’Assistant Déploiement de Lync Server 2013

1.  Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Lync Server est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Générateur de topologies

Utilisez la procédure suivante pour ouvrir le générateur de topologie afin de définir les serveurs que vous souhaitez déployer dans votre topologie Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Pour ouvrir le générateur de topologies Lync Server 2013 afin de concevoir la topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs local, mais pour lire, publier ou activer une topologie, qui est nécessaire pour installer Lync Server 2013 sur un serveur, vous devez utiliser un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins, et disposant des autorisations contrôle total (c’est-à-dire , lisez, écrivez et modifiez) sur le partage de fichiers que vous allez utiliser pour le magasin de fichiers d’archivage afin que le générateur de topologies puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise ou un compte doté de droits d’utilisateur équivalents.

    
    </div>

2.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Panneau de configuration Lync Server 2013

Utilisez l’une des procédures suivantes pour ouvrir le panneau de configuration Lync Server 2013 afin de gérer la configuration des serveurs, des utilisateurs, des clients et des périphériques dans votre environnement.

<div>


> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans le panneau de configuration Lync Server 2013. Vous pouvez utiliser d’autres rôles pour vous connecter au panneau de configuration Lync Server 2013 afin d’effectuer des tâches d’administration spécifiques, en fonction de la tâche que vous devez effectuer. Par exemple, vous pouvez utiliser CSArchivingAdministrator pour administrer l’archivage dans le panneau de configuration Lync Server 2013. Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur les rôles que vous pouvez utiliser pour effectuer une tâche spécifique, reportez-vous à la documentation de la tâche.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Pour ouvrir le panneau de configuration Lync Server 2013 à partir de n’importe quel ordinateur au sein du pare-feu de votre organisation

1.  À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle disposant des droits et des autorisations d’utilisateur appropriés pour la tâche à effectuer, ouvrez une session sur un ordinateur de votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous avez configuré une URL (Uniform Resource Locator) d’administration simple, vous pouvez accéder au panneau de configuration Lync Server 2013 à partir d’un navigateur Internet en cours d’exécution sur n’importe quel ordinateur au sein du pare-feu de votre organisation. Pour plus d’informations sur la configuration de l’URL simple d’administration, voir <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync server 2013</A> dans la documentation de planification et <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

2.  Ouvrez une fenêtre du navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Pour ouvrir le panneau de configuration Lync Server 2013 sur un ordinateur exécutant Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du rôle CsAdministrator ou d’un autre rôle disposant des droits et des autorisations d’utilisateur appropriés pour la tâche à effectuer, ouvrez une session sur un ordinateur sur lequel vous avez installé Lync Server 2013 ou, au minimum, les outils d’administration de Lync Server 2013. Pour configurer les paramètres, l’ordinateur doit avoir une résolution d’écran minimale de 1024 x 768.

2.  Démarrez le panneau de configuration Lync Server 2013 : cliquez sur **Démarrer**, sur **tous les programmes**, pointez sur **Outils d’administration**, sur **Microsoft Lync Server 2013**, puis cliquez sur **panneau de configuration Lync Server 2013**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

Utilisez la procédure suivante pour ouvrir Lync Server 2013 Management Shell afin d’administrer les serveurs, les utilisateurs, les clients et les appareils dans votre environnement à l’aide de la ligne de commande.

<div>


> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans Lync Server 2013 Management Shell. Vous pouvez aussi vous servir d’autres rôles pour réaliser des tâches d’administration précises en fonction de l’opération que vous devez mener. Par exemple, le rôle CSArchivingAdministrator peut vous servir à exécuter des applets de commande inhérentes à l’administration de l’archivage. Pour plus d’informations sur les rôles, voir <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur les rôles qu’il est possible d’utiliser pour l’exécution d’une applet de commande spécifique, voir la documentation consacrée à celle-ci.<BR>Vous pouvez également exécuter certaines applets de commande à l’aide d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, selon l’applet de commande.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Pour ouvrir Lync Server 2013 Management Shell

  - Si vous ouvrez une fenêtre Windows PowerShell plutôt que Lync Server 2013 Management Shell, par défaut, vous ne pouvez pas exécuter les applets de commande Lync Server 2013. Pour exécuter les applets de commande Lync Server 2013 à partir de Windows PowerShell, tapez ce qui suit à l’invite de commandes Windows PowerShell :
    
    `Import-Module Lync`

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Installer les outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Outils d’administration Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

