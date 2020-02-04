---
title: 'Lync Server 2013 : configuration de liens de site réseau'
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
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configuration de liens de site réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Dans le cadre d’une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies entre site réseau qui définissent les limitations de bande passante entre les sites qui sont directement liés. Lorsque les sites réseau partagent un lien direct, les limites de bande passante pour les connexions audio et vidéo peuvent être définies entre ces deux sites. Dans le panneau de configuration de Lync Server, vous ne pouvez pas utiliser l’applet de commande de Lync Server Management Shell pour configurer les stratégies de site réseau. Vous pouvez créer, modifier et supprimer un lien de site réseau (également connu sous le nom de stratégie intersite réseau) de Lync Server Management Shell.

<div>

## <a name="to-create-a-network-site-link"></a>Pour créer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration :
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Cet exemple crée un lien de site réseau intitulé Reno\_Portland qui définit les limites de bande passante entre les sites réseau Reno et Portland. Les sites réseau et le profil de la stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.

Pour obtenir une description détaillée des paramètres, consultez la rubrique [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell. Pour récupérer la liste des profils de stratégie de bande passante qui peuvent être appliqués au lien site réseau, appelez l’applet **de passe Get-CsNetworkBandwidthPolicyProfile** . Pour plus d’informations, consultez la rubrique [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) dans la documentation Lync Server Management Shell.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Pour modifier un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de connexion **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné. Vous pouvez modifier l’un ou l’autre des sites connectés, et vous pouvez modifier le profil de la stratégie de bande passante associé au lien. Voici un exemple de modification du profil de la stratégie de bande passante d’un lien\_de site nommé Reno Portland :
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Pour obtenir une description détaillée des paramètres, consultez la rubrique [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Pour supprimer un lien de site réseau

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Utilisez l’applet de connexion **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau. Dans l’exemple suivant, le lien\_vers le site réseau de Portland de Reno est supprimé :
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Pour obtenir une description détaillée des paramètres, consultez la rubrique [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) dans la documentation Lync Server Management Shell.

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

