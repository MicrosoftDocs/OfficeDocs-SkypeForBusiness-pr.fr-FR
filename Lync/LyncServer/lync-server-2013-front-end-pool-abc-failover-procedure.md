---
title: 'Lync Server 2013 : procédure de basculement ABC de pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500801"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procédure de basculement ABC de pool frontal dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-22_

Procédez comme suit pour effectuer la procédure de basculement ABC. Cette procédure contient une description détaillée de chaque étape, suivies des commandes et des cmdlets à exécuter pour chaque étape.

Pour exécuter les applets de commande, ouvrez un environnement Lync Server Management Shell à l’aide de l’applet de commande exécuter en tant qu’administrateur.

<div>

## <a name="to-perform-an-abc-failover"></a>Pour effectuer un basculement ABC

1.  Vérifiez si le pool A est l’hôte du serveur central de gestion (CMS).
    
      - Exécutez la l’applet commande suivant :
        
            Get-CsService -CentralManagement
        
        Si le champ Identity du MCG actif pointe vers le nom de domaine complet (FQDN) du pool A, utilisez les étapes 2 et 3 de cette procédure pour faire basculer d’abord le serveur de gestion centralisée. Sinon, passez à l’étape 4.

2.  Basculez le CMS vers le pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante :
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Une fois cette opération effectué, nous vous recommandons de déplacer le MCG du pool B vers un autre pool existant pour une résilience supplémentaire. Pour plus d’informations, consultez la rubrique [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Si le pool A contient le MCG, importez la configuration LIS du pool A dans la base de données locale de pool B (LIS. mdf). Cela ne fonctionnera que si vous avez sauvegardé les données LIS de manière régulière. Pour importer la configuration de LIS, exécutez les applets de commande suivantes :
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importez les flux de travail de service Response Group Lync Server sauvegardés du pool A dans le pool B.
    
    <div>
    

    > [!NOTE]  
    > Actuellement, l’applet de commande <STRONG>Import-applet csrgsconfiguration</STRONG> nécessite que les noms de file d’attente et de flux de travail du pool A soient différents des noms de file d’attente et de flux de travail sur le pool B. Si les noms ne sont pas distincts, vous obtiendrez une erreur lors de l’exécution de la cmdlet <STRONG>Import-applet csrgsconfiguration</STRONG> , et les files d’attente et les flux de travail doivent être renommés dans le pool B avant de procéder à l’applet de commande <STRONG>Import-applet csrgsconfiguration</STRONG> .

    
    </div>
    
    Vous disposez de deux options pour importer la configuration Response Group à partir du pool A vers le pool B. L’option que vous utilisez dépend si vous voulez remplacer les paramètres au niveau de l’application du pool B par les paramètres au niveau de l’application dans le pool A.
    
      - Si vous souhaitez remplacer les paramètres du pool B, exécutez l’applet de commande **Import-applet csrgsconfiguration** avec l’option **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne souhaitez pas remplacer les paramètres du pool B, utilisez l’applet de commande **Import-applet csrgsconfiguration** sans l’option **ReplaceExistingSettings**
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > N’oubliez pas que si vous ne souhaitez pas remplacer les paramètres au niveau de l’application du pool de sauvegarde (pool B) par les paramètres du pool principal (pool A), les paramètres au niveau de l’application du pool A seront perdus si le pool A est perdu, car l’application Response Group ne peut stocker qu’un seul ensemble de paramètres au niveau de l’application par pool. Lorsque le pool C est déployé pour remplacer le pool A, les paramètres de niveau application doivent être reconfigurés, y compris le fichier audio de l’attente musicale par défaut.

    
    </div>

5.  Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les cmdlets suivantes pour afficher les groupes Response Group importés. Notez que les groupes Response Group importés sont toujours détenus par le pool A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Pour les numéros non attribués, déplacez les plages de numéros non attribués qui utilisent « annonce » comme service d’annonce sélectionné dans le pool A vers le pool B. Pour cela, procédez comme suit :
    
      - Recréez toutes les annonces qui ont été déployées dans le pool A sur le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces dans le pool A, ces fichiers seront nécessaires pour recréer les annonces dans le pool B. Pour recréer les annonces dans le pool B, utilisez les cmdlets **New-CsAnnouncement** avec le pool b comme service parent.
    
      - Reciblez toutes les plages de numéros non attribués ciblant une annonce dans le pool A vers les annonces nouvellement déployées dans le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribué ciblant une annonce du pool A :
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Cette étape n’est pas obligatoire pour les plages de numéros non attribués qui utilisent « messagerie unifiée Exchange » comme service d’annonce sélectionné.

    
    </div>

7.  Basculez le pool A vers le pool B en mode de récupération d’urgence (DR) en exécutant l’applet de commande suivante :
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Créez le pool C, mais ne démarrez aucun service sur le pool C.
    
    Notez que cette étape peut être exécutée en même temps que les étapes 5 et 6.

9.  Forcez les utilisateurs hébergés sur le pool A à déplacer vers le pool C en exécutant l’applet de commande suivante :
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    À ce stade, les utilisateurs hébergés sur le pool A commencent à subir une panne de service. Cette panne se poursuivra jusqu’à l’étape 16, à laquelle les services pointent sur le pool C.

10. Forcez l’annuaire des conférences du pool A à se déplacer vers le pool C en exécutant l’applet de commande suivante :
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Forcez l’objet contact du standard automatique de conférence (CAA) à passer du pool A au pool C en exécutant l’applet de commande suivante :
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copiez le contenu de la Conférence du pool B vers le pool C.

13. Exportez les données utilisateur du pool B et importez les données utilisateur dans le pool C en exécutant les cmdlets suivantes :
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaurez les données de l’application de parcage d’appel sauvegardée du pool A dans le pool C et affectez les plages d’orbites de parcage d’appel du pool A au pool C.
    
      - Vous pouvez réaffecter une plage d’orbites de parcage d’appel du pool A vers le pool C via le panneau de configuration Lync Server ou Lync Server Management Shell. Pour Lync Server Management Shell, exécutez l’applet de commande suivante pour chaque plage d’orbites de parcage d’appel assignée au pool A (Notez que le paramètre Identity fait référence aux plages d’orbites de parcage d’appel qui appartiennent au pool A) :
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si une mise en attente musicale personnalisée a été configurée pour le parcage d’appel dans le pool A, restaurez le fichier de mise en attente musicale personnalisé du parcage d’appel dans le pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Par exemple :
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Enfin, reconfigurez les paramètres de parcage d’appel sur le pool C à l’aide de la cmdlet **Set-CsCpsConfiguration** . L’application de parcage d’appel ne peut stocker qu’un seul ensemble de paramètres et un seul fichier audio de conservation de musique personnalisé par pool, et ces paramètres ne sont ni sauvegardés ni conservés en cas de sinistre.

15. Si le pool du tronçon suivant pour la conversation permanente pointe vers le pool A, effectuez et publiez les modifications de topologie de sorte que le serveur du tronçon suivant pointe vers le pool C.
    
      - Dans le générateur de topologies, modifiez le pool de conversation permanente de sorte qu’il pointe vers le pool C en tant que tronçon suivant. Pour ce faire, cliquez avec le bouton droit sur le pool de conversations permanentes, cliquez sur l’onglet **général** , puis tapez le nom du pool C dans **pool du tronçon suivant**.
    
      - Démarrez les services sur le pool C en exécutant l’applet de commande suivante :
        
            Start-csWindowsService
    
    À ce stade, l’interruption du service se termine pour les utilisateurs hébergés dans le pool A.

16. Exportez les flux de travail de service de groupe réponse de Lync Server depuis le pool B appartenant au pool A pour l’importer dans le pool C en exécutant l’applet de commande suivante :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importez les flux de travail de service Response Group Lync Server dans le pool C à partir du pool B.
    
    Deux options s’offrent à vous pour importer la configuration Response Group à partir du pool B vers le pool C. L’option que vous utilisez dépend si vous voulez remplacer les paramètres au niveau de l’application du pool C par les paramètres au niveau de l’application dans le pool B.
    
      - Si vous souhaitez remplacer les paramètres du pool C, exécutez l’applet de commande **Import-applet csrgsconfiguration** avec l’option **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne souhaitez pas remplacer les paramètres du pool C, utilisez l’applet de commande **Import-applet csrgsconfiguration** sans l’option **ReplaceExistingSettings**
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > N’oubliez pas que si vous ne souhaitez pas remplacer les paramètres au niveau de l’application du pool C par les paramètres du pool de sauvegarde (pool B), les paramètres au niveau de l’application du pool B seront perdus car l’application Response Group ne peut stocker qu’un seul ensemble de paramètres au niveau de l’application par pool.

    
    </div>

18. Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les cmdlets suivantes pour afficher les groupes Response Group qui ont été importés dans le pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Lorsque la configuration importée a été vérifiée dans le pool C, supprimez les groupes Response Group appartenant au pool principal du pool B. Cela réduira le temps d’arrêt des groupes Response Group.
    
    Cette étape crée un fichier avec la configuration exportée, puis supprime le fichier du pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Déplacer vers le pool C plages de numéros non attribués qui ont été déplacées du pool A vers le pool B.
    
      - Recréer dans le pool C toutes les annonces qui ont été recréées à partir du pool A dans le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces à déplacer, vous devrez utiliser ces fichiers pour recréer les annonces dans le pool C. Pour recréer les annonces dans le pool C, utilisez les cmdlets **New-CsAnnouncement** , avec le pool c comme service parent.
    
      - Recibler vers le pool C toutes les plages de numéros non attribués qui ont été reciblées du pool A vers le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués qui doit être reciblée :
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Module Supprimez du pool B les annonces qui ont été recréées dans le pool C s’ils ne sont plus utilisés dans le pool B. Pour supprimer des annonces, utilisez la cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Cette étape n’est pas obligatoire pour les plages de numéros non attribués qui utilisent « messagerie unifiée Exchange » en tant que service d’annonce.

        
        </div>

21. Nettoyez les données utilisateur du pool A dans le pool B en exécutant l’applet de commande suivante :
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Procédez comme suit dans le générateur de topologie :
    
      - Découpler les pools A et B. paire B et pool C. Supprimez ensuite le pool A de la topologie et publiez-le. Pour ce faire, procédez comme suit :
        
          - Dans le générateur de topologies, cliquez avec le bouton droit sur le pool B, puis cliquez sur **modifier les propriétés**.
        
          - Cliquez sur **résistance** dans le volet de gauche.
        
          - Dans la zone située sous le **pool de sauvegarde associé**, sélectionnez Pool C. Notez que la zone de sélection du pool de sauvegarde associé affiche le pool A, car le pool B était précédemment associé à ce pool.
        
          - Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.
            
            Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**.
        
          - Dans l’arborescence de la console, cliquez avec le bouton droit sur pool A, puis cliquez sur supprimer.
        
          - Publiez la topologie.

23. Exécutez l’application d’amorçage sur le pool C pour installer l’application de service de sauvegarde, puis démarrez l’application de service de sauvegarde en exécutant ce qui suit à partir du dossier de déploiement sur un ordinateur local dans le pool C :
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Redémarrez l’application de service de sauvegarde sur le pool B en exécutant les cmdlets suivantes :
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Si le pool C est un pool Standard Edition (SE) et que le pool B a CMS, installez la base de données CMS manuellement sur le pool C en exécutant l’applet de commande suivante :
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Appelez le service de sauvegarde pour synchroniser l’ancien contenu de conférence du pool B vers le pool C généré avant le jumelage de B et C, et pour synchroniser le nouveau contenu de conférence du pool C vers le pool B qui a été généré après le démarrage du pool C et avant l’Association de B et C. Pour cela, exécutez les applets de commande suivantes :
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Pour chaque serveur Survivable Branch Appliance X associé au pool A :
    
      - Arrêtez SBA X en exécutant l’applet de commande suivante :
        
            Stop-CsWindowsService
    
      - Créez un fichier contenant une liste d’utilisateurs hébergés sur SBA X. La liste est nécessaire lorsque les utilisateurs sont déplacés de SBA X à l’étape 30. Pour ce faire, exécutez l’applet de commande suivante :
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Forcez les utilisateurs hébergés sur SBA X à se déplacer vers le pool C en exécutant l’applet de commande suivante :
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Mettez à jour les données de ces utilisateurs en exécutant d’abord les cmdlets suivantes :
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Puis exécutez ce script :
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Une panne de service se produit pour les utilisateurs hébergés sur SBA qui sont associés au pool A jusqu’à ce que ces utilisateurs soient déplacés vers le pool C.

        
        </div>

28. Dans le générateur de topologies, pour chaque SBA X précédemment associé au pool A, procédez comme suit :
    
      - Modifiez l’Association en pool C. Pour ce faire, cliquez sur le site de succursale, développez le nœud Survivable Branch Appliances ou Servers, puis cliquez sur **Survivable Branch Appliance**. Ensuite, sélectionnez le pool **frontal, le pool de services d’utilisateurs** auquel ce Survivable Branch appliance se connectera en tant que Pool C, puis cliquez sur **suivant**.
    
      - Publiez la topologie. Pour ce faire, dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau **Survivable Branch Appliance**, cliquez sur **topologie**, puis sur **publier**.

29. Pour chaque SBA X maintenant associé au pool C :
    
      - Démarrez SBA X en exécutant l’applet de commande suivante sur le Survivable Branch Appliance :
        
            Start-CsWindowsService
    
      - Déplacez les utilisateurs hébergés à l’origine sur SBA X du pool C vers SBA X en exécutant l’applet de commande suivante.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

