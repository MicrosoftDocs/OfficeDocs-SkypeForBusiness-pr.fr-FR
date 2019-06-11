---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Connexion d’une Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Chaque appareil de branchement survivant (SBA) est associé à une réserve frontale qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal a été déplacé vers Lync Server 2013, le SBA doit être désassocié du pool frontal 2010 de Lync Server lors de la mise à niveau du pool, une fois que le pool a été migré vers Lync Server 2013, il est possible de le réassocier à l’adresse du pool frontal mis à niveau. Cela implique la suppression de l’SBA de la topologie Lync Server 2010 héritée dans le générateur de topologie, puis l’ajout de l’SBA à la topologie de Lync Server 2013. Les utilisateurs hébergés sur l’ancien serveur Lync Server 2010 SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie. Dès lors que l’SBA est ajouté à la topologie Lync Server 2013, les utilisateurs peuvent ensuite être repassés à l’adresse SBA. Ces étapes sont décrites ci-dessous:

1.  Déplacer les utilisateurs de succursales hébergés sur l’ancien réseau Lync Server 2010 vers un autre pool frontal.

2.  Supprimez SBA de la topologie de Lync Server 2010 héritée pour déconnecter le pool frontal existant en tant qu’Bureau d’enregistrement de sauvegarde.

3.  Ajoutez SBA à la topologie Lync Server 2013 et configurez ce nouveau pool frontal comme bureau d’enregistrement de sauvegarde.

4.  Déplacez les utilisateurs de la succursale vers le nouveau Lync Server 2013 SBA.

**Ajouter le site de succursale Lync Server 2010 SBA à votre topologie**

1.  Ouvrez le **Générateur de topologie**.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **sites**de succursales, puis cliquez sur **nouveau site de succursale**.

3.  Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez le nom du site de la succursale.

4.  Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.

5.  Cliquez sur **Suivant**.

6.  Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes:
    
    1.  Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.
    
    2.  Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.
    
    3.  Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.

7.  Cliquez sur **suivant**, puis effectuez l’une des opérations suivantes:
    
    1.  Si vous utilisez une application de succursale ou un serveur Lync 2010 sur ce site, veillez à désactiver l’option **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** . Cliquez sur **Terminer**.

8.  Pour associer l’ancien serveur Lync Server 2010 SBA au pool frontal 2013 Server, procédez comme suit:
    
    1.  Développez le site de succursale qui a été créé.
    
    2.  Cliquez avec le bouton droit sur **Lync Server 2010** , puis cliquez sur **nouveau**.
    
    3.  Cliquez sur l' **application branchement Survivable...**

9.  Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [définir une unité ou un serveur de succursales survivant dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Une unité de branchement de Lync Server 2010 Survivable ne peut être associée qu’à un magasin de contrôle d' 2010 serveur Lync.

    
    </div>

10. Si vous n’utilisez pas d’appareil ou serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** , puis cliquez sur **Terminer**.

11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.

</div>

<span> </span>

</div>

</div>

</div>

