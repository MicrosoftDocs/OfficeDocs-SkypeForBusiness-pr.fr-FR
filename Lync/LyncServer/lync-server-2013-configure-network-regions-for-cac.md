---
title: 'Lync Server 2013 : configuration des régions réseau pour le contrôle d’admission des opérations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acafaca86af1943d2614349ff42f04fa87faddaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

<div>


> [!IMPORTANT]  
> Si vous avez déjà créé des régions réseau pour E9-1-1 ou une déviation du trafic multimédia, vous pouvez modifier les régions réseau existantes en ajoutant des paramètres spécifiques au contrôle d’admission des appels à l’aide de la cmdlet <STRONG>Set-applet csnetworkregion</STRONG> . Pour obtenir un exemple de la façon de modifier une région réseau, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync Server 2013</A>.



</div>

Les *régions réseau* sont les concentrateurs ou les dorsales réseau utilisés pour la configuration du contrôle d’admission des médias, E9-1-1 et la déviation du trafic multimédia. Utilisez la procédure suivante pour créer des régions réseau qui s’alignent sur les régions réseau dans l’exemple de topologie réseau pour le contrôle d’admission des opérations. Pour afficher l’exemple de topologie réseau, reportez-vous à l’exemple [suivant : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

L’exemple de topologie réseau pour le contrôle d’admission des États comprend trois régions : Amérique du Nord, EMEA et APAC. Chaque région dispose d’un site central spécifié. Pour la région Amérique du Nord, le site central désigné est nommé CHICAGO. La procédure suivante montre comment utiliser la cmdlet **New-applet csnetworkregion** pour créer la région Amérique du Nord.

<div>


> [!NOTE]  
> Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer une région réseau. Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server pour créer une région réseau, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Pour créer une région réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Pour chaque région que vous devez créer, exécutez la cmdlet **New-applet csnetworkregion** . Par exemple, pour créer la région Amérique du Nord, exécutez :
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Répétez l’étape 2 pour créer les régions réseau, EMEA et APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

