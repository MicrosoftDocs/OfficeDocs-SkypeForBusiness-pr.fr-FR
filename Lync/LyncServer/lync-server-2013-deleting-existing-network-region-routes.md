---
title: 'Lync Server 2013: suppression des itinéraires de région réseau existants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Supprimer des itinéraires de région réseau existants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions. Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre. Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer les itinéraires de région réseau. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau. Utilisez cette rubrique pour supprimer des itinéraires de la région de réseau existants. Pour plus d’informations sur la création et la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Pour supprimer un itinéraire de la région du réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.

4.  Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires par région à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée. Pour sélectionner tous les itinéraires de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>édition</STRONG> .

    
    </div>

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurer un itinéraire de région réseau](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))  


[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

