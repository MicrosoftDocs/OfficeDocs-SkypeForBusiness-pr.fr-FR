---
title: 'Lync Server 2013 : Ajout des sites de succursale à votre topologie'
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
ms.openlocfilehash: 2df1871956b33b3781128e2b62af13bdd875d10b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>Ajout des sites de succursale à votre topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Les sites de succursales représentent des agences physiques qui sont connectées à vos bureaux principaux par le biais d’une liaison WAN. Pour ajouter un site de succursale à votre topologie Lync, procédez comme suit sur le site central.

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>Pour ajouter des sites de succursales à votre topologie

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, cliquez avec le bouton droit sur **sites de succursales**, puis cliquez sur **nouveau site de succursale**.

3.  Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez le nom du site de la succursale.

4.  Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.

5.  Cliquez sur **Suivant**.

6.  Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes :
    
      - Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.
    
      - Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.
    
      - Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.

7.  Cliquez sur **suivant**, puis effectuez l’une des opérations suivantes :
    
      - Si vous utilisez un appareil ou un serveur de succursales survivant sur ce site, assurez-vous que la case à cocher **ouvrir le nouvel Assistant survie à la fermeture de cet Assistant** est activée, cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir [définir une unité ou un serveur de succursales survivant dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
      - Si vous n’utilisez pas d’appareil ou serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** , puis cliquez sur **Terminer**.

8.  Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.

**Étape suivante :**

Pour les appareils ou serveurs de succursales Survivables : [définir une unité ou un serveur de succursale Survivable dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

Pour la connectivité PSTN non résiliente : [définissez une passerelle PSTN pour un site de succursale dans Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [configurez un Trunk avec une dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)ou [configurez un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

