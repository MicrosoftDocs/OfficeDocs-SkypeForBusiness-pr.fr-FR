---
title: 'Lync Server 2013: afficher les informations de plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be912be5bd421310b1806165db7aac744f7ab23f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a>Afficher les informations de plan de numérotation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Pour afficher des informations pour un plan de numérotation existant, suivez les étapes de la procédure ci-dessous. Pour créer un nouveau plan de numérotation, reportez-vous à [la rubrique créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a>Pour afficher des informations sur un plan de numérotation via le panneau de configuration de Lync Server

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez afficher des informations pour un seul plan de numérotation à la fois.

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a>Pour afficher les plans de numérotation à l’aide des cmdlets Windows PowerShell

  - Les plans de numérotation peuvent être affichés à l’aide de l’interface de ligne de commande Windows PowerShell et de l’applet de commande **Get-CsDialPlan** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».
    
    Pour afficher des informations sur l’ensemble de vos plans de numérotation, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsDialPlan
    
    Cette commande renvoie des informations similaires à ce qui suit:
    
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


[Créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

