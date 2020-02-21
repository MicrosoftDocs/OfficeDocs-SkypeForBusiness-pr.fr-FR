---
title: 'Lync Server 2013 : affichage des informations de sous-réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c61c6c9c27fb6ba642a8996588dc2e4a3c3c42d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Affichage des informations de sous-réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la création ou la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>Pour afficher un sous-réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez afficher.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de sous-réseau à l’aide des applets de commande Windows PowerShell

Les informations de sous-réseau peuvent être visualisées à l’aide de Windows PowerShell et de la cmdlet Get-CsNetworkSubnet. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-subnet-information"></a>Pour afficher les informations de sous-réseau

  - Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkSubnet
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

