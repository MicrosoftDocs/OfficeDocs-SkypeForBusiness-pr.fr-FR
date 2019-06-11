---
title: Vérifier les informations de topologie
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Vérifier les informations de topologie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-26_

La première étape de vérification réussie du publipostage consiste à afficher les informations sur la topologie Office Communications Server 2007 R2 que vous avez fusionnées avec Lync Server 2013. Dans le générateur de topologie, le nœud **BackCompatSite** affiche le nom de domaine complet (FQDN) de chaque pool et serveur Office Communications Server 2007 R2.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Pour afficher BackCompatSite dans le générateur de topologie

1.  Dans votre environnement Office Communications Server 2007 R2, ouvrez l’outil d’administration Office Communications Server 2007 R2 et notez les noms de domaine complets des pools et serveurs hérités.

2.  Dans votre environnement Lync Server 2013, ouvrez le générateur de topologie et développez le nœud **BackCompatSite** .

3.  Vérifiez que les noms de domaine complets des pools et des serveurs que vous fusionnez sont affichés.
    
    <div>
    

    > [!NOTE]  
    > Aucune information n’apparaît dans <STRONG>BackCompatSite</STRONG> pour les rôles serveur colocalisés sur un serveur frontal ou un serveur Standard Edition Server. Seuls les rôles de serveur requis pour l’interopérabilité entre Office Communications Server 2007 R2 et Lync Server 2013 sont affichés.

    
    </div>

![Boîte de dialogue BackCompatSite de générateur de topologie] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Boîte de dialogue BackCompatSite de générateur de topologie")

Vous pouvez également utiliser le panneau de configuration de Lync Server 2013 pour afficher votre topologie fusionnée. Dans Lync Server 2013 panneau de configuration, vous pouvez voir chaque nom de domaine complet (FQDN) de serveur, nom de domaine complet (FQDN) du pool et nom de site pour votre topologie fusionnée. Les serveurs fusionnés portent le nom de **site** **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Pour afficher la topologie fusionnée dans Lync Server 2013 panneau de configuration

1.  Ouvrez le panneau de configuration de Lync Server 2013.

2.  Cliquez sur **Topology**.

3.  Dans l’onglet **statut** , assurez-vous que les serveurs et les pools fusionnés apparaissent en recherchant **BackCompatSite** dans la colonne **site** .

![Panneau de configuration de Lync Server avec topologie fusionnée] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panneau de configuration de Lync Server avec topologie fusionnée")

Pour afficher des détails supplémentaires sur un pool fusionné, utilisez l’applet de passe **Get-CsPool** . Outre les informations disponibles dans le générateur de topologie et le panneau de configuration de Lync Server 2013, cette applet de commande affiche les services qui s’exécutent sur le pool Lync Server 2013.

<div>


> [!NOTE]  
> Lorsque vous publiez la topologie après avoir exécuté l’Assistant fusion dans le générateur de topologie, les annuaires de conférences sont fusionnés avec Lync Server 2013. Les annuaires de conférences peuvent être vérifiés en exécutant l’applet de passe <STRONG>Get-CsConferenceDirectory</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Pour afficher les services d’un pool fusionné

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Par exemple :
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Pour vérifier la fusion des répertoires de conférences

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsConferenceDirectory

3.  Vérifiez que tous les répertoires de conférences du pool ou du serveur que vous fusionnez se trouvent désormais dans Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

