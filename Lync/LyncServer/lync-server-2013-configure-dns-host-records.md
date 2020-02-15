---
title: 'Lync Server 2013 : configuration des enregistrements d’hôte DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ae1e2502ec1618f007ba76255ae6d01ebb66f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configuration des enregistrements d’hôte DNS pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Pour configurer des enregistrement d’hôte DNS (A)

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **Nouvel hôte (A ou AAAA)**.

4.  Cliquez sur **Nom**, tapez le nom d’hôte du pool (le nom de domaine est présumé à partir de la zone dans laquelle est défini l’enregistrement, il est inutile de l’entrer comme partie de l’enregistrement A).

5.  Cliquez sur **adresse IP**, tapez l’adresse IP virtuelle de l’équilibreur de charge pour le pool frontal.
    
    <div>
    

    > [!IMPORTANT]  
    > Dans les déploiements qui utilisent un pool directeur, les enregistrements hôtes (A) pour les URL simples doivent pointer sur l’adresse IP virtuelle du programme d’équilibrage de la charge du directeur.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si vous déployez un seul serveur Enterprise Edition Server connecté à la topologie sans programme d’équilibrage de la charge, ou si vous déployez un serveur Standard Edition, tapez l’adresse IP du serveur Enterprise Edition Server, Standard Edition Server ou du directeur. L’utilisation d’un programme d’équilibrage de la charge est nécessaire si vous déployez plusieurs serveurs Enterprise Edition Server ou directeur dans un pool. Les programmes d’équilibrage de la charge ne sont pas utilisés avec les serveurs Standard Edition.

    
    </div>

6.  Cliquez sur **Ajouter un hôte**, puis sur **OK**.

7.  Pour créer un enregistrement A supplémentaire, répétez les étapes 4 et 5.

8.  Lorsque vous avez terminé de créer tous les enregistrements A dont vous avez besoin, cliquez sur **Terminer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

