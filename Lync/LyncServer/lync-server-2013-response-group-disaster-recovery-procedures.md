---
title: Procédures de récupération d’urgence de groupe Response Group Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254f9e95edfb445d996948a17064ae460dbdb7d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pendant la phase de basculement de la récupération d’urgence, les groupes Response Group résident dans plusieurs pools : dans le pool principal (qui n’est pas disponible) et dans le pool de sauvegarde. Les groupes Response Group des deux pools portent le même nom et ont le même propriétaire (le pool principal), mais ils ont des parents différents. Pendant ce temps, les cmdlets Response Group fonctionnent un peu différemment. Veillez à utiliser les paramètres comme spécifié dans la procédure suivante. Pour plus d’informations sur le fonctionnement des cmdlets pendant la phase de basculement, voir l’article du blog NextHop « Lync Server 2013 : Recovering [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)Response Groups during Disaster Recovery » à l’adresse. Cet article du blog s’applique également à la version finale de Lync Server 2013.

Suivez les étapes de la procédure ci-dessous pour préparer et effectuer une récupération d’urgence pour le service de groupe Response Group Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Pour basculer et restaurer un groupe Response Group

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Effectuez régulièrement des sauvegardes. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Pendant une panne, après le basculement vers le pool de sauvegarde, importez les groupes Response Group sur le pool de sauvegarde. Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Si vous voulez remplacer les paramètres de niveau application du pool de sauvegarde par les paramètres du pool principal, incluez le paramètre –ReplaceExistingSettings. Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Si vous ne remplacez pas les paramètres du pool de sauvegarde et que le pool principal ne peut pas être récupéré, les paramètres du pool principal seront perdus. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in Lync Server 2013</A>.

    
    </div>

4.  Vérifiez que l’importation a réussi en affichant les groupes Response Group importés. Ces groupes appartiennent toujours au pool principal. Procédez comme suit :
    
      - Affichez tous les flux de travail du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que tous les flux de travail du pool principal sont inclus. Sur la ligne de commande, tapez :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Par exemple :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Affichez toutes les files d’attente du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les files d’attente du pool principal sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Par exemple :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez tous les groupes d’agents du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que tous les groupes d’agents du pool principal sont inclus. Sur la ligne de commande, tapez :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Par exemple :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez toutes les heures d’ouverture du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les heures d’ouverture du pool principal sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Par exemple :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez toutes les périodes de congé du pool de sauvegarde qui appartiennent au pool principal, et vérifiez que toutes les périodes de congé du pool principal sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Par exemple :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Vous pouvez également afficher tous les groupes Response Group du pool de sauvegarde, y compris ceux appartenant au pool principal et ceux appartenant au pool de sauvegarde, en utilisant du paramètre –ShowAll au lieu du paramètre –Owner. Par exemple :
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez utiliser le paramètre –ShowAll ou le paramètre –Owner. Si vous n’utilisez aucun de ces paramètres, les groupes Response Group que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats retournés par les applets de commande.

    
    </div>

5.  Vérifiez que l’importation a réussi en passant un appel à un groupe Response Group importé et en vérifiant que l’appel est correctement géré.

6.  Demandez aux agents qui sont membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de sauvegarde.

7.  Gérez et modifiez les groupes Response Group importés comme d’habitude.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque les groupes Response Group se trouvent dans le pool de sauvegarde, vous devez utiliser Lync Server Management Shell pour les gérer. Vous ne pouvez pas utiliser le panneau de configuration Lync Server pour gérer les groupes Response Group que vous avez importés dans le pool de sauvegarde.

    
    </div>

8.  Une fois le pool principal restauré et la restauration automatique terminée, exportez les groupes Response Group du pool principal qui ont été importés dans le pool de sauvegarde. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importez à nouveau les groupes Response Group dans le pool principal. Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Si vous reconstruisez un pool pendant la récupération, que ce soit avec le même nom de domaine complet (FQDN) ou avec un nom FQDN différent, vous devez utiliser le paramètre –OverwriteOwner. Généralement, vous pouvez toujours utiliser le paramètre –OverwriteOwner lorsque vous importez à nouveau des groupes Response Group dans le pool principal.

    
    </div>
    
    Si vous avez déployé un nouveau pool (avec le même nom FQDN ou avec un nom différent) pour remplacer le pool principal, et que vous voulez utiliser les paramètres de niveau application du pool de sauvegarde du nouveau pool, incluez le paramètre –ReplaceExistingSettings. Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous ne voulez pas remplacer les paramètres de niveau application et le fichier audio d’attente musicale par défaut du nouveau pool par les paramètres du pool de sauvegarde, le nouveau pool utilise les paramètres de niveau application par défaut.

    
    </div>

10. Vérifiez que la nouvelle importation dans le pool principal a réussi en affichant la configuration des groupes Response Group importés. Procédez comme suit :
    
      - Affichez tous les flux de travail du pool principal, et vérifiez que tous les flux de travail importés sont inclus. Sur la ligne de commande, tapez :

        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Par exemple :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Affichez toutes les files d’attente du pool principal, et vérifiez que toutes les files d’attente importées sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Par exemple :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez tous les groupes d’agents du pool principal, et vérifiez que tous les groupes d’agents importés sont inclus. Sur la ligne de commande, tapez :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Par exemple :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez toutes les heures d’ouverture du pool principal, et vérifiez que toutes les heures d’ouverture importées sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Par exemple :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez toutes les périodes de congé du pool principal, et vérifiez que toutes les périodes de congé importées sont incluses. Sur la ligne de commande, tapez :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Par exemple :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Vérifiez que l’importation a réussi en passant un appel à un groupe Response Group importé et en vérifiant que l’appel est correctement géré.

12. Supprimez éventuellement du pool de sauvegarde les groupes Response Group appartenant au pool principal. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Cette étape crée un fichier avec la configuration exportée, puis le supprime du pool de sauvegarde.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

