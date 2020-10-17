---
title: Vérifier les informations de la topologie
description: Vérifier les informations de topologie.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555490"
---
# <a name="verify-topology-information"></a>Vérifier les informations de la topologie

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

La première étape de la vérification de la fusion réussie consiste à afficher les informations de topologie Office Communications Server 2007 R2 que vous avez fusionnées avec Lync Server 2013. Dans le générateur de topologies, le nœud **BackCompatSite** affiche le nom de domaine complet (FQDN) de chaque pool et serveur Office Communications Server 2007 R2 que vous avez fusionnés.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Pour afficher BackCompatSite dans le Générateur de topologies

1.  Dans votre environnement Office Communications Server 2007 R2, ouvrez l’outil d’administration Office Communications Server 2007 R2 et notez les noms de domaine complets des pools et serveurs hérités.

2.  Dans votre environnement Lync Server 2013, ouvrez le générateur de topologies, puis développez le nœud **BackCompatSite** .

3.  Vérifiez que les noms de domaine complets des pools et serveurs que vous fusionnez sont affichés.
    
    <div>
    

    > [!NOTE]  
    > Aucune information n’est affichée dans <STRONG>BackCompatSite</STRONG> pour les rôles serveur colocalisés sur un serveur frontal ou un serveur Standard Edition. Seuls les rôles serveur requis pour l’interopérabilité entre Office Communications Server 2007 R2 et Lync Server 2013 sont affichés.

    
    </div>

![Boîte de dialogue BackCompatSite du générateur de topologies](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Boîte de dialogue BackCompatSite du générateur de topologies")

Vous pouvez également utiliser le panneau de configuration Lync Server 2013 pour afficher votre topologie fusionnée. Dans le panneau de configuration Lync Server 2013, vous pouvez voir le nom de domaine complet du serveur, le nom de domaine complet du pool et le nom du site pour votre topologie fusionnée. Les serveurs fusionnés porte le nom **Site****BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Pour afficher la topologie fusionnée dans le panneau de configuration Lync Server 2013

1.  Ouvrez le panneau de configuration Lync Server 2013.

2.  Cliquez sur **Topologie**.

3.  Sous l’onglet **Statut**, vérifiez que les serveurs et pools que vous avez fusionnés apparaissent en recherchant **BackCompatSite** dans la colonne **Site**.

![Panneau de configuration Lync Server affichant la topologie fusionnée](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panneau de configuration Lync Server affichant la topologie fusionnée")

Pour afficher plus d’informations sur un pool fusionné, utilisez l’applet de commande **Get-CsPool**. Outre les informations disponibles dans le panneau de configuration du générateur de topologies et de Lync Server 2013, cette applet de commande affiche les services exécutés sur le pool Lync Server 2013.

<div>


> [!NOTE]  
> Lorsque vous publiez la topologie après avoir exécuté l’Assistant fusion dans le générateur de topologies, les annuaires de conférence sont fusionnés avec Lync Server 2013. Les annuaires des conférences peuvent être vérifiés en exécutant l’applet de commande <STRONG>Get-CsConferenceDirectory</STRONG>.



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Pour afficher les services sur un pool fusionné

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Par exemple :
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Pour vérifier les annuaires des conférences fusionnés

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez le code suivant :
    
        Get-CsConferenceDirectory

3.  Vérifiez que tous les annuaires des conférences du pool ou du serveur que vous fusionnez figurent désormais dans Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

