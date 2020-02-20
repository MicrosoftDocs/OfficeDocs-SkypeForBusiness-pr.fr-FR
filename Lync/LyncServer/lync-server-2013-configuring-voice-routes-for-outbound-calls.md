---
title: 'Lync Server 2013 : configuration des itinéraires des communications vocales pour les appels sortants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c53a8358345130aa95fff4e29b5facf901cbea79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Un itinéraire de communications vocales Lync Server 2013 associe les numéros de téléphone de destination à une ou plusieurs passerelles de réseau téléphonique commuté (PSTN) ou à des jonctions SIP, ainsi qu’un ou plusieurs enregistrements d’utilisation PSTN.

**Pour afficher les itinéraires des communications vocales à l’aide du panneau de configuration Lync Server**

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Cliquez sur **Routage des communications vocales**.

3.  Cliquez sur **Itinéraire**.

4.  Double-cliquez sur un itinéraire de communications vocales pour afficher les autres propriétés de la liste des itinéraires de communications vocales ou sélectionnez l’itinéraire, puis cliquez sur **Modifier**. Cliquez ensuite sur **Afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher les informations détaillées que d’un seul itinéraire à la fois.

    
    </div>

**Pour afficher les itinéraires des communications vocales à l’aide de Windows PowerShell**

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**. Les itinéraires des communications vocales peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande **Get-CsVoiceRoute** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.
    
    Pour afficher des informations sur tous vos itinéraires vocaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsVoiceRoute
    
    Cette action a pour effet de renvoyer des informations similaires à ce qui suit :
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Pour plus d’informations, reportez-vous à <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion du routage des communications vocales dans Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

