---
title: 'Lync Server 2013 : annexe B : gestion d’un Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27975119b9e54b96ba7472ce1e60d64a51671c5c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>Annexe B : gestion d’un Survivable Branch Appliance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Cette rubrique décrit les procédures de gestion d’un Survivable Branch appliance. En particulier, le remplacement et le changement de nom d’un Survivable Branch appliance, ainsi que la modification du pool frontal Lync Server 2013 auquel le Survivable Branch Appliance est associé.

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>Pour remplacer un Survivable Branch Appliance

1.  Arrêtez tous les services Lync Server 2013 sur le Survivable Branch appliance. (Voir la documentation du fournisseur du Survivable Branch Appliance.)

2.  Recommandation Supprimez le Survivable Branch Appliance du domaine.

3.  Supprimez l’objet d’ordinateur Survivable Branch Appliance dans les services de domaine Active Directory, en procédant comme suit :
    
      - Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer**, sur **Outils d'administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch appliance, puis cliquez sur **supprimer**.

4.  Ajoutez à nouveau l’objet ordinateur Survivable Branch appliance. (Voir [Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Attendez que la réplication Active Directory ait lieu.

6.  Ouvrez Lync Server Management Shell et tapez **Enable-CSTopology**.

7.  Connectez le nouveau Survivable Branch Appliance au réseau, puis suivez les étapes décrites dans [Deploying a Survivable Branch Appliance or Server with Lync server 2013-central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>Pour renommer un Survivable Branch Appliance

1.  Déplacez les utilisateurs vers le site central. Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server 2013 sur le Survivable Branch appliance. (Voir la documentation du fournisseur du Survivable Branch Appliance.)

3.  Supprimez le Survivable Branch appliance de la topologie, en procédant comme suit :
    
      - Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.
    
      - Dans l’arborescence de la console, développez **sites de succursale**, cliquez sur le Survivable Branch appliance, puis cliquez sur **supprimer** dans le volet Actions.

4.  Supprimez le Survivable Branch Appliance du domaine.

5.  Supprimez l’objet d’ordinateur Survivable Branch Appliance dans Active Directory en procédant comme suit :
    
      - Ouvrez une session sur un contrôleur de domaine, en tant que membre du groupe Administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch appliance, puis cliquez sur **supprimer**.

6.  Restaurez le Survivable Branch Appliance aux paramètres d’usine. (Voir la documentation du fournisseur du Survivable Branch Appliance.)

7.  Suivez les étapes décrites dans [Deploying a Survivable Branch Appliance or Server with Lync server 2013-central site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Deploy a Survivable Branch Appliance or Server with Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Déplacez les utilisateurs vers le Survivable Branch Appliance renommé. Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>Pour changer le pool de serveurs frontaux Lync Server auquel le Survivable Branch Appliance est associé

1.  Déplacez les utilisateurs du Survivable Branch Appliance vers le pool frontal Lync Server au niveau du site central. Pour plus d’informations, consultez la rubrique [déplacer des utilisateurs vers un autre pool dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server sur le Survivable Branch appliance. (Consultez la documentation du fournisseur Survivable Branch Appliance Vendor).

3.  Mettez à jour le pool frontal Lync Server auquel le Survivable Branch Appliance est associé, en procédant comme suit :
    
      - Cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.
    
      - Développez **Sites de succursales**.
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch appliance à modifier, puis cliquez sur **modifier les propriétés** .
    
      - Sous résistance, sélectionnez le nouveau pool frontal auquel le Survivable Branch appliance doit être associé, puis cliquez sur **suivant**.
    
      - Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch appliance, cliquez sur **topologie**, puis cliquez sur **publier**.

4.  Redémarrez tous les services Lync Server sur le Survivable Branch appliance.

5.  Testez le Survivable Branch appliance. Pour plus d’informations, consultez [la rubrique utilisateurs familiaux sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Déplacez les utilisateurs du pool frontal Lync Server du site central vers le Survivable Branch appliance.

</div>

</div>

<span> </span>

</div>

</div>

</div>

