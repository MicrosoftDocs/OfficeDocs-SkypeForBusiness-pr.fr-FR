---
title: 'Lync Server 2013 : Vérification de l’affectation des régions aux plans de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Vérifier que le plan de numérotation Lync Server 2013 a des régions affectées

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2010-11-02_

Les plans de numérotation qui sont utilisés pour les conférences rendez-vous doivent disposer d’une **région de conférence** rendez-vous pour associer les numéros d’accès aux conférences rendez-vous au plan de numérotation approprié. Lorsque vous créez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Lorsque vous créez le numéro d’accès à une conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.

Dans la mesure où il est important de spécifier une région pour tous les plans de numérotation, nous vous conseillons d’utiliser cette procédure pour vérifier que tous les plans de numérotation disposent de régions. Cette étape est facultative.

Utilisez l’applet de connexion **Get-CsDialPlan** pour vérifier si la région est définie pour toutes les offres de numérotation de conférence rendez-vous. Si ce n’est pas le cas, vous pouvez utiliser l’applet de commande **Set-CsDialPlan** pour configurer la région. Vous pouvez également utiliser le panneau de configuration de Lync Server pour mettre à jour la région dans les plans de numérotation existants. Pour plus d’informations sur l’utilisation du panneau de configuration de Lync Server, voir [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Pour vérifier que la région est correctement configurée dans les plans de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez la commande suivante dans l’invite de commandes :
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Par exemple :
    
        Get-CsDialPlan
    
    Dans cet exemple, tous les plans de numérotation configurés pour votre organisation sont renvoyés.

4.  Vérifiez les plans de numérotation renvoyés pour identifier ceux ne comportant pas la région de conférence rendez-vous. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Pour définir la propriété de région d’un plan de numérotation

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour tous les plans de numérotation ne comportant pas de région de conférence rendez-vous, exécutez :
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Exemple :
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    Dans cet exemple, le plan de numérotation dont l’identité est Redmond est modifié afin de définir la propriété DialinConferencingRegion sur « US West Coast ». Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

