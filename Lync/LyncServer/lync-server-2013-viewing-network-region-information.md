---
title: 'Lync Server 2013 : affichage des informations de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d59e8182c0ebe904d61dd18e9cd3653f58a6fb4a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>Affichage des informations de région réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser le panneau de configuration Lync Server pour afficher les régions réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins via Internet peuvent être empruntés pour les connexions audio et vidéo. Utilisez cette rubrique pour afficher des régions réseau existantes. Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [Creating or Modifying Network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Pour afficher des informations sur une région réseau à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez afficher.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher qu’une région à la fois.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de région réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les informations de région réseau à l’aide de Windows PowerShell et de la cmdlet **Get-applet csnetworkregion** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-network-region-information"></a>Pour afficher les informations de région réseau

  - Pour afficher des informations sur toutes vos régions réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkRegion
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de régions réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Suppression des régions réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

