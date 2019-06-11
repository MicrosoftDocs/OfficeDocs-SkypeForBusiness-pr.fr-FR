---
title: 'Lync Server 2013: affichage des informations de sous-réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Affichage des informations de sous-réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la création et la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>Pour afficher un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.

4.  Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez afficher.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

    
    </div>

5.  Dans le menu **édition** , cliquez sur **afficher les détails.**

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de sous-réseau en utilisant des applets de cmdlet Windows PowerShell

Les informations de sous-réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkSubnet. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-network-subnet-information"></a>Pour afficher les informations de sous-réseau

  - Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsNetworkSubnet
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer ou modifier des sous-réseaux réseau dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Supprimer des sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

