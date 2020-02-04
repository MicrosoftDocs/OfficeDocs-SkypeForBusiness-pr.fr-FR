---
title: 'Lync Server 2013 : Configuration des enregistrements hôte DNS'
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
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configuration des enregistrements hôte DNS pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Pour configurer les enregistrements d’un hôte DNS

1.  Sur le serveur DNS (Domain Name System), cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 sera installé.

3.  Cliquez sur **nouvel hôte (A ou AAAA)**.

4.  Cliquez sur **nom**, tapez le nom d’hôte de la liste (le nom de domaine est censé partir de la zone dans laquelle l’enregistrement est défini et qu’il n’est pas nécessaire d’entrer dans le cadre de l’enregistrement a).

5.  Cliquez sur **IP Address (adresse IP**), puis tapez l’adresse IP virtuelle (VIP) de l’équilibrage de charge pour le pool frontal.
    
    <div>
    

    > [!IMPORTANT]  
    > Dans les déploiements qui utilisent un pool de réalisateurs, les enregistrements d’hôte (A) pour les URL simples doivent pointer vers l’adresse VIP du directeur de charge du directeur.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Si vous déployez uniquement un serveur ou un directeur Enterprise Edition qui est connecté à la topologie sans équilibrage de charge, ou si vous déployez un serveur Standard Edition Server, tapez l’adresse IP du serveur Enterprise Edition Server, Standard Edition Server ou Director. Un équilibrage de charge est requis si vous déployez plusieurs serveurs ou Director Enterprise Edition dans un pool. Les équilibreurs de charge ne sont pas utilisés avec les serveurs Standard Edition.

    
    </div>

6.  Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.

7.  Pour créer un enregistrement A supplémentaires, répétez les étapes 4 et 5.

8.  Lorsque vous avez terminé de créer tous les enregistrements A dont vous avez besoin, cliquez sur **terminé**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

