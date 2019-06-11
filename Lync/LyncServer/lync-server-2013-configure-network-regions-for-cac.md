---
title: 'Lync Server 2013: configurer des régions réseau pour CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurer des régions réseau pour CAC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Si vous avez déjà créé des régions réseau pour le contournement de E9-1-1 ou du support multimédia, vous pouvez modifier les régions réseau existantes en ajoutant des paramètres spécifiques au contrôle d’admission des appels à l’aide de l’applet <STRONG>de commande Set-CsNetworkRegion</STRONG> . Pour obtenir un exemple illustrant comment modifier une région réseau, reportez-vous à la rubrique <A href="lync-server-2013-create-or-modify-a-network-region.md">créer ou modifier une région réseau dans Lync Server 2013</A>.



</div>

Les *régions réseau* sont les concentrateurs réseau ou les dorsales qui sont utilisés pour la configuration du CAC, de E9-1-1 et du contournement multimédia. Utilisez la procédure suivante pour créer des régions réseau qui s’alignent sur des régions réseau dans l’exemple de topologie réseau pour CAC. Pour afficher l’exemple de topologie du réseau, reportez-vous à la rubrique [exemple: rassemblement des exigences relatives au contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

L’exemple de topologie réseau pour CAC comporte trois régions: Amérique du Nord, EMEA et APAC. Chaque région possède un site central spécifié. Pour la région Amérique du Nord, le site central désigné est appelé CHICAGO. La procédure suivante vous montre comment utiliser l’applet de commande **New-CsNetworkRegion** pour créer la région Amérique du Nord.

<div>


> [!NOTE]  
> Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer une région réseau. Pour plus d’informations sur l’utilisation du panneau de configuration de Lync Server pour créer une région réseau, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">créer ou modifier une région réseau dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Pour créer une région de réseau pour le contrôle d’admission des appels

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour chaque région que vous devez créer, exécutez l’applet de requête **New-CsNetworkRegion** . Par exemple, pour créer la région Amérique du Nord, exécutez:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Répétez l’étape 2 pour créer les zones du réseau (EMEA et APAC).

</div>

</div>

<span> </span>

</div>

</div>

</div>

