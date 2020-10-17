---
title: 'Lync Server 2013 : transfert de groupes Response Group vers un nouveau pool'
description: 'Lync Server 2013 : transfert de groupes Response Group vers un nouveau pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b696963a28abbcd258f53fae12c3e281efa6ae4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541981"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Transfert de groupes Response Group vers un nouveau pool dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server 2013 introduit une nouvelle prise en charge des cmdlets pour le transfert de groupes Response Group d’un pool vers un autre, même si le nom de domaine complet (FQDN) est différent.

Suivez les étapes de la procédure ci-après pour déplacer des groupes Response Group d’un pool frontal vers un autre.

<div>


> [!NOTE]  
> Dans un environnement de coexistence, vous pouvez déplacer des groupes Response Group uniquement entre des &nbsp; Pools frontaux Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Pour déplacer les groupes Response Group avec un nom de domaine complet différent

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exportez les groupes Response Group dans le pool source. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Pour supprimer les groupes Response Group du pool source durant l’exportation, incluez le paramètre –RemoveExportedConfiguration. Par exemple :
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importez les groupes Response Group vers le pool de destination et affectez ce dernier comme nouveau propriétaire. Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Si vous souhaitez également copier les paramètres de niveau application de Response Group depuis le pool source vers le pool de destination, incluez le paramètre – ReplaceExistingRgsSettings. Vous ne pouvez définir qu’un seul ensemble de paramètres de niveau d’application par pool. Si vous copiez les paramètres de niveau d’application du pool source vers le pool de destination, les paramètres du pool source remplacent ceux du pool de destination. Si vous ne copiez pas les paramètres de niveau d’application du pool source, les paramètres existants du pool de destination s’appliquent aux groupes Response Group importés.
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Les paramètres de niveau d’application comprennent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de la reprise d’appel parqué des agents ainsi que la configuration du contexte de l’appel. Pour afficher ces paramètres de configuration, exécutez l’applet de commande <STRONG>Get-CsRgsConfiguration</STRONG>. Pour plus d’informations sur cette applet de commande, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-applet csrgsconfiguration</A>.

    
    </div>

4.  Vérifiez que l’importation est réussie en affichant la configuration des groupes Response Group importés. Pour ce faire, procédez comme suit :
    
      - Vérifiez que tous les flux de travail ont été importés. Sur la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que toutes les files d’attente ont été importées. Sur la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que tous les groupes d’agents ont été importés. Sur la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que toutes les heures ouvrées ont été importées. Sur la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Vérifiez que tous les groupes de congés ont été importés. Sur la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Vérifiez que l’importation est réussie en appelant un des groupes Response Group et en vérifiant que l’appel est correctement traité.

6.  Demandez aux agents membres des groupes d’agents formels de s’inscrire à leurs groupes d’agents dans le pool de destination.

7.  Si vous n’avez pas précédemment supprimé les groupes Response Group du pool source, supprimez-les. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

