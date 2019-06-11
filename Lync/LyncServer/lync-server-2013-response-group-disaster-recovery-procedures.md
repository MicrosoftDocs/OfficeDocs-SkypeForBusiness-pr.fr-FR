---
title: Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Lors de la phase de reprise après incident, les groupes de réponse résident dans plusieurs pools: dans le pool principal (non disponible) et dans le pool de sauvegarde. Les groupes Response dans les deux pools ont le même nom et le même propriétaire (le pool principal), mais ils ont des parents différents. Pendant ce temps, les cmdlets de groupe de réponse fonctionnent légèrement différemment. Veillez à utiliser les paramètres comme spécifié dans la procédure suivante. Pour plus d’informations sur le fonctionnement des cmdlets lors de la phase de basculement, voir l’article de blog NextHop «Lync Server 2013: récupération de [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)Response Groups en cours de reprise après sinistre». Ce blog s’applique également à la version publiée de Lync Server 2013.

Suivez les étapes décrites dans la procédure ci-dessous pour préparer et exécuter une reprise après sinistre pour le service Response Group de Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Pour basculer et annuler le regroupement de réponses

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez régulièrement des sauvegardes. Dans la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Au cours d’une panne, après le basculement vers le pool de sauvegarde, importez les groupes de réponses dans le pool de sauvegarde. À partir de la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Si vous voulez remplacer les paramètres au niveau de l’application dans le pool de sauvegarde par les paramètres de la liste principale, incluez le paramètre – ReplaceExistingSettings. Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Si vous ne souhaitez pas remplacer les paramètres dans le pool de sauvegarde et que le pool principal ne peut pas être récupéré, les paramètres du pool principal seront perdus. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planification d’une reprise après sinistre de Response Group dans Lync Server 2013</A>.

    
    </div>

4.  Vérifiez que l’importation est réussie en affichant les groupes de réponse importés. Les groupes de réponse importés sont encore possédés par le pool principal. Procédez comme suit :
    
      - Affichez tous les flux de travail du pool de sauvegarde dont le pool principal est possédé, puis vérifiez que tous les flux de travail de pool principal sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Exemple :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Affichez toutes les files d’attente du pool de sauvegarde détenu par le pool principal, puis vérifiez que tous les files d’attente du pool principal sont incluses. Dans la ligne de commande, tapez :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Exemple :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez tous les groupes d’agents dans le pool de sauvegarde appartenant au pool principal, puis vérifiez que tous les groupes d’agents de pool principal sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Exemple :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez toutes les heures d’activité dans le pool de sauvegarde qui sont détenues par le pool principal, puis vérifiez que tous les horaires d’activité du pool principal sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Exemple :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Affichez tous les jeux de jours fériés dans le pool de sauvegarde appartenant au pool principal, puis vérifiez que tous les jeux de jours de vacances du pool principal sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Exemple :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Par ailleurs, vous pouvez afficher tous les groupes de réponses du pool de sauvegarde, y compris ceux appartenant au pool principal et ceux appartenant au pool de sauvegarde, à l’aide du paramètre-ShowAll à la place du paramètre – owner. Par exemple :
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez utiliser le paramètre – ShowAll ou – owner. Si vous n’utilisez pas l’un de ces paramètres, les groupes de réponse que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de requête.

    
    </div>

5.  Vérifiez que l’importation est réussie en effectuant un appel vers un groupe de réponse importé et en vérifiant que l’appel est correctement géré.

6.  Demandez aux agents membres de groupes d’agents formels de se connecter à leurs groupes d’agents dans le pool de sauvegarde.

7.  Gestion et modification des groupes de réponse importés comme d’habitude.
    
    <div>
    

    > [!IMPORTANT]  
    > Lorsque les groupes de réponse figurent dans le pool de sauvegarde, vous devez utiliser Lync Server Management Shell pour les gérer. Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer les groupes de réponse que vous avez importés dans le pool de sauvegarde.

    
    </div>

8.  Lorsque le pool principal est restauré et que le retour arrière est terminé, exportez les groupes de réponses de la liste principale qui ont été importés dans le pool de sauvegarde. À partir de la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importez les groupes de réponse dans le pool principal. Dans la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Si vous reconstruisez un pool lors de la récupération, qu’il s’agisse d’un nom de domaine complet, ou d’un nom de domaine complet différent, vous devez utiliser le paramètre – OverwriteOwner. En règle générale, vous pouvez toujours utiliser le paramètre – OverwriteOwner lorsque vous importez des groupes de réponses vers le pool principal.

    
    </div>
    
    Si vous avez déployé un nouveau pool (avec le même nom ou un nom de domaine complet différent) pour remplacer le pool principal et que vous souhaitez utiliser les paramètres au niveau de l’application du pool de sauvegarde pour le nouveau pool, incluez le paramètre – ReplaceExistingSettings. Dans la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous ne voulez pas remplacer les paramètres au niveau de l’application et le fichier audio en attente par défaut de musique pour le nouveau pool avec les paramètres du pool de sauvegarde, le nouveau pool utilisera les paramètres de niveau application par défaut.

    
    </div>

10. Assurez-vous que l’importation du pool principal est réussie en affichant la configuration de groupe de réponse importée. Procédez comme suit :
    
      - Affichez tous les flux de travail dans la liste principale, puis vérifiez que tous les flux de travail importés sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Exemple :
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Affichez toutes les files d’attente dans la liste principale, puis vérifiez que toutes les files d’attente importées sont incluses. Dans la ligne de commande, tapez :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Exemple :
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez tous les groupes d’agents dans la liste principale des agents et vérifiez que tous les groupes d’agents importés sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Exemple :
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez toutes les heures d’activité dans la liste principale, puis vérifiez que toutes les heures d’activité importées sont incluses. Dans la ligne de commande, tapez :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Exemple :
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Affichez tous les ensembles de jours fériés dans la liste principale, puis vérifiez que tous les jeux de jours de vacances importés sont inclus. Dans la ligne de commande, tapez :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Exemple :
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Vérifiez que l’importation est réussie en effectuant un appel vers un groupe de réponse importé et en vérifiant que l’appel est correctement géré.

12. Vous pouvez également supprimer les groupes de réponse appartenant au pool principal du pool de sauvegarde. Dans la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Cette étape permet de créer un fichier avec la configuration exportée, puis de le supprimer du pool de sauvegarde.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

