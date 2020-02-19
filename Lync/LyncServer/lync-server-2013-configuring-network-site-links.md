---
title: 'Lync Server 2013 : configuration des liens de sites réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccd6a4efa271a5ca70a81eb6f375ffee4d1ae45d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configuration des liens de sites réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Dans une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies réseau intersite qui définissent les limitations de bande passante entre les sites qui sont directement liés. Quand des sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéo peuvent être définies pour lesdits sites. Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour configurer des stratégies de site réseau, mais vous ne pouvez le faire qu’à l’aide d’applets de commande de Lync Server Management Shell. Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé stratégie inter-site réseau) à partir de Lync Server Management Shell.

<div>

## <a name="to-create-a-network-site-link"></a>Pour créer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  À l’invite de commandes, tapez la commande suivante en spécifiant les valeurs valides pour votre configuration :
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Cet exemple crée un lien de site réseau nommé Reno\_Portland qui définit des limites de bande passante entre les sites réseau Reno et Portland. Les sites réseau et le profil de stratégie de bande passante doivent être existants avant d’exécuter cette commande.

Pour obtenir des descriptions détaillées des paramètres, voir [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell. Pour récupérer une liste des profils de stratégie de bande passante pouvant être appliqués au lien de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile**. Pour plus d’informations, reportez-vous à [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) dans la documentation Lync Server Management Shell.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Pour modifier un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier l’un ou l’autre des sites connectés, ou les deux, ainsi que le profil de stratégie de bande passante associé au lien. Voici un exemple de modification du profil de stratégie de bande passante d’un lien de\_site nommé Reno Portland :
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Pour obtenir des descriptions détaillées des paramètres, voir [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Pour supprimer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. L’exemple suivant supprime le lien de\_site de réseau Portland Reno :
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Pour obtenir des descriptions détaillées des paramètres, voir [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) dans la documentation de Lync Server Management Shell.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Applets de commande de contrôle d’admission des appels dans Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

