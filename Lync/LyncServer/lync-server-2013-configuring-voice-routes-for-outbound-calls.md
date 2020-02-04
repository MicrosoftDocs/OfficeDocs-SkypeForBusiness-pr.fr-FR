---
title: 'Lync Server 2013 : Configuration des itinéraires de communications vocales pour les appels sortants'
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
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Un itinéraire vocal de Lync Server 2013 associe des numéros de téléphone de destination à une ou plusieurs passerelles de réseau téléphonique commuté (PSTN) ou des Trunks SIP et un ou plusieurs enregistrements d’utilisation PSTN.

**Pour afficher les itinéraires vocaux à l’aide du panneau de configuration de Lync Server**

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Cliquez sur **gamme vocale**.

3.  Cliquez sur **Itinéraire**.

4.  Double-cliquez sur un itinéraire vocal pour afficher d’autres propriétés dans la liste des itinéraires vocaux, ou sélectionnez l’itinéraire, puis cliquez sur **modifier**. Cliquez ensuite sur **afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez uniquement afficher des informations détaillées sur un itinéraire à la fois.

    
    </div>

**Pour afficher les itinéraires vocaux à l’aide de Windows PowerShell**

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**. Les itinéraires vocaux peuvent être affichés à l’aide de Windows PowerShell et de l’applet **de passe Get-CsVoiceRoute** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».
    
    Pour afficher des informations sur l’ensemble de vos itinéraires vocaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsVoiceRoute
    
    Vous obtiendrez des indications semblables à ceci :
    
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
> Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-voice-routes.md">itinéraires vocaux dans Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

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

