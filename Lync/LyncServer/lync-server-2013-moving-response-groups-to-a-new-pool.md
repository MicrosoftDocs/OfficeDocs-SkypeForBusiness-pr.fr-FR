---
title: 'Lync Server 2013 : déplacer des groupes de réponse vers un nouveau pool'
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
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Déplacer des groupes de réponse vers un nouveau pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server 2013 introduit une nouvelle cmdlet support pour le déplacement de groupes de réponse d’un pool vers un autre, même si le nom de domaine complet (FQDN) est différent.

Suivez les étapes décrites dans la procédure ci-dessous pour déplacer les groupes de réponse d’un pool frontal vers un autre à l’aide d’un nom de domaine complet différent.

<div>


> [!NOTE]  
> Dans un environnement de coexistence, vous pouvez déplacer des groupes de réponse uniquement entre&nbsp;les pools front end de Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Pour déplacer des groupes de réponses vers un pool avec un nom de domaine complet différent

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exportez les groupes de réponses dans le pool de sources. Dans la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Pour supprimer les groupes de réponse du pool de sources lors de l’exportation, incluez le paramètre – RemoveExportedConfiguration. Par exemple :
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importez les groupes de réponses dans le pool de destination et attribuez le pool de destination comme nouveau propriétaire. À partir de la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Si vous voulez également copier les paramètres au niveau de l’application du groupe de réponses du pool de sources vers le pool de destination, incluez le paramètre – ReplaceExistingRgsSettings. Vous pouvez définir un seul ensemble de paramètres de niveau application par pool. Si vous copiez les paramètres au niveau de l’application à partir du pool de sources vers le pool de destination, les paramètres du pool de sources remplacent ceux du pool de destination. Si vous ne copiez pas les paramètres au niveau de l’application à partir du pool de sources, les paramètres existants du pool de destination s’appliquent aux groupes de réponse importés.
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Les paramètres au niveau de l’application incluent la configuration par défaut de Music-Holding, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel. Pour afficher ces paramètres de configuration, exécutez l’applet <STRONG>de passe Get-CsRgsConfiguration</STRONG> . Pour plus d’informations sur cette cmdlet, voir <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Assurez-vous que l’importation réussie s’affiche avec la configuration de groupe de réponse importée en procédant comme suit :
    
      - Vérifiez que tous les flux de travail étaient importés. Dans la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que toutes les files d’attente ont été importées. Dans la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que tous les groupes d’agents ont été importés. Dans la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Vérifiez que toutes les heures d’activité ont été importées. Dans la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Vérifiez que tous les ensembles de jours fériés ont été importés. Dans la ligne de commande, tapez ce qui suit :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Vérifiez que l’importation est réussie en passant un appel à l’un des groupes de réponses et en vérifiant que l’appel est géré correctement.

6.  Demandez aux agents membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de destination.

7.  Si vous n’avez pas encore supprimé les groupes de réponses du pool de sources, supprimez les groupes de réponses du pool de sources. Dans la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

