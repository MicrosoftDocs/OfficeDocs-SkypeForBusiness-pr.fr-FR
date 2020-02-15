---
title: 'Lync Server 2013 : affichage des informations de lien de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7046f4f405bc3ece0170c4d598369828b47aa910
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Affichage des informations de lien de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez afficher les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le panneau de configuration Lync Server pour afficher un lien existant entre deux régions réseau. Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Pour afficher un lien de région réseau dans le panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez afficher.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur un lien de région à la fois.

    
    </div>

5.  Dans le menu **Edition**, sélectionnez **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de lien de région réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et de la cmdlet **Get-CsNetworkRegionLink** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-region-link-information"></a>Pour afficher les informations d’un lien de région réseau

  - Pour afficher des informations sur tous les liens de région réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkRegionLink
    
    Cette commande renvoie le type d’information suivant :
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des liens de sites réseau dans Lync Server 2013](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

