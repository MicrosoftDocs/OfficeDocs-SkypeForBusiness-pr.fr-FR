---
title: 'Lync Server 2013 : Annexe B : Gestion d’un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Annexe B : Gestion d’un Survivable Branch Appliance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

Cette rubrique décrit les procédures de gestion d’une unité de branchement survivant. Pour plus d’informations, sur le remplacement d’une unité de branchement Survivable et sur la modification de la liste frontale de Lync Server 2013 à laquelle l’unité de branchement Survivable est associée.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Pour remplacer une unité de branchement survivant

1.  Arrêtez tous les services Lync Server 2013 sur l’appareil de branche Survivable. (Voir la documentation du fabricant de l’appareil de branchement Survivable.)

2.  Recommande Supprimez l’unité de branchement Survivable du domaine.

3.  Supprimez l’objet de l’unité de l’appareil de branchement Survivable dans les services de domaine Active Directory (AD FS) en procédant comme suit:
    
      - Connectez-vous à un serveur membre en tant que membre du groupe administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.
    
      - Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant, puis cliquez sur **supprimer**.

4.  Ajoutez à nouveau l’objet de l’appareil de branchement Survivable. (Voir [Ajouter une unité de branchement survivant à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Attendez que la réplication Active Directory intervient.

6.  Ouvrez Lync Server Management Shell, puis tapez **Enable-CSTopology**.

7.  Connectez la nouvelle appliance de succursale survivant au réseau, puis suivez les étapes décrites dans l’article [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [déploiement d’une unité ou d’un serveur Survivables avec Lync Server 2013- tâche de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Pour renommer une unité de branchement survivant

1.  Déplacer des utilisateurs vers le site central. Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server 2013 sur l’appareil de branche Survivable. (Voir la documentation du fabricant de l’appareil de branchement Survivable.)

3.  Supprimez l’appareil de branchement survivant de la topologie en procédant comme suit:
    
      - Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.
    
      - Dans l’arborescence de la console, développez **sites**de succursales, cliquez sur l’unité de branchement Survivable, puis cliquez sur **supprimer** dans le volet action.

4.  Supprimez l’unité de branchement Survivable du domaine.

5.  Supprimez l’objet de l’unité de branchement Survivable dans Active Directory en procédant comme suit:
    
      - Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.
    
      - Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant, puis cliquez sur **supprimer**.

6.  Restaurez les commutateurs par défaut de l’appareil de branchement survivant. (Voir la documentation du fabricant de l’appareil de branchement Survivable.)

7.  Suivez les étapes décrites dans l’article [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [déploiement d’une unité ou d’un serveur de succursales survivant avec Lync Server 2013-Task site](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Déplacez les utilisateurs vers l’appareil de succursales survivant renommé. Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Pour modifier le pool frontal de Lync Server auquel est associé l’unité de branchement Survivable

1.  Déplacez les utilisateurs de l’unité de branchement Survivable vers le pool frontal de Lync Server sur le site central. Pour plus d’informations, voir [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server sur l’unité de branchement Survivable. (Pour plus d’informations, consultez la documentation du fabricant de l’appareil pour succursales survivant).

3.  Mettez à jour le pool frontal du serveur Lync pour lequel est associé l’unité de branchement survivant, en procédant comme suit:
    
      - Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.
    
      - Développez **sites**de succursales.
    
      - Cliquez avec le bouton droit sur l’objet de l’appareil de branchement survivant à modifier, puis cliquez sur **modifier les propriétés** .
    
      - Sous résilience, sélectionnez le nouveau pool frontal pour lequel vous souhaitez associer l’unité de branchement survivant, puis cliquez sur **suivant**.
    
      - Dans l’arborescence de la console, cliquez avec le bouton droit sur la nouvelle branche Survivable, cliquez sur **Topology**, puis sur **publier**.

4.  Redémarrez tous les services Lync Server sur l’unité de branchement Survivable.

5.  Testez l’appareil de branchement Survivable. Pour plus d’informations, reportez-vous à [la section utilisateurs domestiques d’une unité ou d’un serveur de succursales survivables dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Déplacez les utilisateurs du pool frontal de Lync Server vers le site central vers l’unité de branchement Survivable.

</div>

</div>

<span> </span>

</div>

</div>

</div>

