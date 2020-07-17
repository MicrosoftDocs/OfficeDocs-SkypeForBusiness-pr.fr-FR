---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Connexion d’une Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Lync Server 2013, le SBA doit être désassocié à partir du pool frontal Lync Server 2010, tandis que le pool est mis à niveau, une fois le pool migré vers Lync Server 2013, le SBA peut être réassocié au pool frontal mis à niveau. Cela implique de supprimer le SBA de la topologie Lync Server 2010 héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Lync Server 2013. Les utilisateurs hébergés sur l’ancien Lync Server 2010 SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Lync Server 2013, ces utilisateurs peuvent ensuite être déplacés vers le SBA. Voici un récapitulatif de ces étapes :

1.  Déplacez les utilisateurs de succursale hébergés sur l’ancien SBA Lync Server 2010 vers un autre pool frontal.

2.  Supprimez SBA de la topologie Lync Server 2010 héritée pour déconnecter le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.

3.  Ajoutez SBA à la topologie Lync Server 2013 et configurez ce nouveau pool frontal comme serveur d’inscriptions de sauvegarde.

4.  Déplacez les utilisateurs de succursale vers le nouveau Lync Server 2013 SBA.

**Ajouter le site de succursale SBA Lync Server 2010 à votre topologie**

1.  Ouvrez le **Générateur de topologie**.

2.  Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis entrez le nom du site de succursale.

4.  (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.

5.  Cliquez sur **Suivant**.

6.  (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :
    
    1.  Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
    2.  Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.
    
    3.  Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.

7.  Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :
    
    1.  Si vous utilisez un SBA ou un serveur Lync 2010 sur ce site, assurez-vous d’avoir désactivé la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**. Cliquez sur **Terminer**.

8.  Pour associer l’ancien serveur Lync Server 2010 SBA au pool frontal Lync Server 2013, procédez comme suit :
    
    1.  Développez le site de succursale créé.
    
    2.  Cliquez avec le bouton droit sur **Lync Server 2010** puis cliquez sur **Nouveau**.
    
    3.  Cliquez sur **Survivable Branch Appliance…**

9.  Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Une appliance Survivable Branch Lync Server 2010 ne peut être associée qu’à un magasin de surveillance Lync Server 2010.

    
    </div>

10. Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.

11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.

</div>

<span> </span>

</div>

</div>

</div>

