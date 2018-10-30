---
title: Déplacement des groupes Response Group vers un nouveau pool
TOCTitle: Déplacement des groupes Response Group vers un nouveau pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205298(v=OCS.15)
ms:contentKeyID: 49299023
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des groupes Response Group vers un nouveau pool

 

_**Dernière rubrique modifiée :** 2012-11-01_

Lync Server 2013 inclut la prise en charge de nouvelles applets de commande pour déplacer les groupes Response Group d’un pool vers un autre, même lorsque le nom de domaine complet est différent.

La procédure suivante permet de déplacer les groupes Response Groupe d’un pool de serveurs frontaux vers un autre pool de serveurs frontaux avec un nom de domaine complet différent.

> [!NOTE]  
> Dans un environnement de coexistence, vous ne pouvez déplacer les groupes Response Group qu’entre les pools de serveurs frontauxLync Server 2013.

## Pour déplacer les groupes Response Group avec un nom de domaine complet différent

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exportez les groupes Response Group dans le pool source. Sur la ligne de commande, tapez :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Par exemple :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Pour supprimer les groupes Response Group du pool source durant l’exportation, incluez le paramètre –RemoveExportedConfiguration. Par exemple :
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importez les groupes Response Group vers le pool de destination et affectez ce dernier comme nouveau propriétaire. Sur la ligne de commande, tapez :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Si vous voulez également copier les paramètres de niveau d’application Response Group du pool source vers le pool de destination, incluez le paramètre –ReplaceExistingSettings. Vous ne pouvez définir qu’un seul ensemble de paramètres de niveau d’application par pool. Si vous copiez les paramètres de niveau d’application du pool source vers le pool de destination, les paramètres du pool source remplacent ceux du pool de destination. Si vous ne copiez pas les paramètres de niveau d’application du pool source, les paramètres existants du pool de destination s’appliquent aux groupes Response Group importés.
    
    Par exemple :
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    
    > [!NOTE]  
    > Les paramètres de niveau d’application comprennent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de la reprise d’appel parqué des agents ainsi que la configuration du contexte de l’appel. Pour afficher ces paramètres de configuration, exécutez l’applet de commande <strong>Get-CsRgsConfiguration</strong>. Pour plus d’informations sur cette applet de commande, voir <a href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</a>.

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

