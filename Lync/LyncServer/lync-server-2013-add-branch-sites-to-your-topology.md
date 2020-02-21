---
title: 'Lync Server 2013 : ajout de sites de succursale à votre topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Ajouter des sites de succursale à votre topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Les sites de succursale représentent des filiales physiques qui sont connectées à vos bureaux principaux via une liaison réseau étendu. Pour ajouter un site de succursale à votre topologie Lync, exécutez la procédure suivante sur le site central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Pour ajouter des sites de succursale à votre topologie

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.

3.  Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.

4.  (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.

5.  Cliquez sur **Suivant**.

6.  (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
      - Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.
    
      - Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.

7.  Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, assurez-vous que la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Assistant à la fermeture de cet Assistant** est activée, cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.

8.  Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.

**Étape suivante :**

Pour les serveurs Survivable Branch Appliances ou serveurs Survivable Branch [Server : Define a Survivable Branch Appliance or Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Pour une connectivité PSTN non résiliente : [définition d’une passerelle PSTN pour un site de succursale dans Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

