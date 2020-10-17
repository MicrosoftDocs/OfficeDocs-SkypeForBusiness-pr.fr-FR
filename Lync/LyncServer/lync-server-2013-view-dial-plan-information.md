---
title: 'Lync Server 2013 : afficher les informations sur le plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e60533af230f613be89cad16379b851549801
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506431"
---
# <a name="view-dial-plan-information-in-lync-server-2013"></a>Afficher les informations de plan de numérotation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour afficher les informations d’un plan de numérotation existant, effectuez la procédure suivante. Si vous souhaitez créer un nouveau plan de numérotation, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a>Pour afficher des informations sur un plan de numérotation à partir du panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, double-cliquez sur le nom du plan de numérotation.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher les informations que d’un seul plan de numération à la fois.

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a>Pour afficher les plans de numérotation à l’aide des applets de commande Windows PowerShell

  - Les plans de numérotation peuvent être affichés à l’aide de l’interface de ligne de commande Windows PowerShell et de la cmdlet **Get-CsDialPlan** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Pour afficher des informations sur tous vos plans de numérotation, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :
    
        Get-CsDialPlan
    
    Cette commande renvoie des informations semblables à celles-ci :
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

