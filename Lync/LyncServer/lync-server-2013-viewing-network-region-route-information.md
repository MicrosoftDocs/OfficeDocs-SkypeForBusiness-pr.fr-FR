---
title: 'Lync Server 2013 : affichage des informations d’itinéraire de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f509735cf3a43e6539305fcad31db17cfd52a11
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Affichage des informations d’itinéraire de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Utilisez les procédures suivantes pour afficher les itinéraires de région réseau existants dans le panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell. Pour plus d’informations sur la création ou la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Pour afficher les informations d’itinéraire de région réseau dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher qu’un itinéraire de région à la fois.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations d’itinéraire de région réseau à l’aide des applets de commande Windows PowerShell

Les informations sur les itinéraires de région réseau peuvent être visualisées à l’aide de Windows PowerShell et de la cmdlet Get-CsNetworkInterRegionRoute. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-region-route-information"></a>Pour afficher les informations sur les itinéraires de région réseau

  - Pour afficher des informations sur tous les itinéraires de région réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkInterRegionRoute
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Suppression des itinéraires de région réseau existants dans Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

