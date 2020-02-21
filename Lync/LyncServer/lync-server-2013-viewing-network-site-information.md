---
title: 'Lync Server 2013 : affichage des informations relatives au site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf9f10ed66fec57516f14cf17a71692fc360da7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a>Affichage des informations de site réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez afficher les informations relatives à un site réseau dans le panneau de configuration Lync Server 2013 ou dans Lync Server Management Shell. Pour plus d’informations sur la création ou la modification de sites réseau, reportez-vous à la rubrique [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>Pour afficher les informations sur les sites réseau dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez afficher.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher les informations que d’un site à la fois.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de site réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les informations de site réseau à l’aide de Windows PowerShell et de la cmdlet Get-applet csnetworksite. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-site-information"></a>Pour afficher des informations sur les sites réseau

  - Pour afficher des informations sur tous les sites réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkSite
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)  
[Suppression d’un site réseau existant dans Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

