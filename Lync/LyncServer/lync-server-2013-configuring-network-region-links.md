---
title: 'Lync Server 2013: configuration de liens de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895c85a80d3e5a7fadee3dccad25f9d89f04028a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Configuration de liens de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique. Le panneau de configuration de Lync Server vous permet de définir un lien entre deux zones du réseau et de définir les limites de bande passante pour les connexions audio et vidéo entre ces régions. Pour plus d’informations sur la suppression d’un lien de région réseau existant, reportez-vous à [la rubrique Suppression de liens de région réseau dans Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Pour créer un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.

4.  Dans la page de **liaison région** , cliquez sur **nouveau**.

5.  Dans le **lien nouvelle zone**, tapez une valeur dans le champ **nom** .
    
    <div>
    

    > [!NOTE]  
    > Cette valeur doit être unique dans le cadre de votre déploiement 2013 de Lync Server.

    
    </div>

6.  Dans la liste déroulante ** \#région réseau 1** , sélectionnez l’une des deux régions à lier.

7.  Dans la liste déroulante ** \#région de réseau 2** , sélectionnez la autre zone à lier. Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.

8.  Facultatif Si vous voulez appliquer des limitations de bande passante aux appels audio et vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Pour modifier un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.

4.  Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans le **lien modifier la région**, vous pouvez modifier les régions liées ou le profil de la stratégie de bande passante pour ce lien.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer des liens de région réseau dans Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
