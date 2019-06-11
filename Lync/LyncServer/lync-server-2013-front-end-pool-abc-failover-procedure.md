---
title: 'Lync Server 2013 : Procédure de basculement ABC vers un pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6cb610d153374f6f4c9ba8a3c2798c50b88ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procédure de basculement ABC vers un pool frontal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-05-22_

Procédez comme suit pour effectuer la procédure de basculement ABC. Cette procédure contient une description de haut niveau de chaque étape, suivie de commandes et d’applets de commande à exécuter pour chaque étape.

Pour exécuter les applets de cmdlet, ouvrez Lync Server Management Shell à l’aide de l’applet exécuter en tant qu’administrateur.

<div>

## <a name="to-perform-an-abc-failover"></a>Pour effectuer un basculement ABC

1.  Vérifiez si le pool A est l’hôte du serveur de gestion central (CMS).
    
      - Exécutez l’applet de commande suivante :
        
            Get-CsService -CentralManagement
        
        Si le champ Identity du CMS actif pointe vers le nom de domaine complet (FQDN) du pool A, vous devez commencer par suivre les étapes 2 et 3 de cette procédure pour basculer d’abord sur le serveur de gestion central. Dans le cas contraire, passez à l’étape 4.

2.  Basculez le CMS vers le pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Après cela, nous vous recommandons de déplacer le MCG du pool B vers un autre pool couplé existant pour une résilience supplémentaire. Pour plus d’informations, reportez-vous à [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Si le regroupement A contient le MCG, importez la configuration de LIS de la liste de la base de données LIS de pool A (LIS. mdf). Cela ne fonctionnera que si vous sauvegardez vos données LIS de façon régulière. Pour importer la configuration de LIS, exécutez les applets de commande suivantes:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importez des flux de travail de service de groupe de réponse de groupe avec le regroupement A dans le pool B.
    
    <div>
    

    > [!NOTE]  
    > Pour l’instant, l’applet de demande <STRONG>Import-CsRgsConfiguration</STRONG> nécessite que les noms de files d’attente et de flux de travail du pool A sont différents des noms de file d’attente et de flux de travail du pool B. Si les noms ne sont pas distincts, vous obtiendrez une erreur lors de l’exécution de l’applet <STRONG>de cmdlet Import-CsRgsConfiguration</STRONG> , et les files d’attente et les flux de travail devront être renommées dans le pool B avant de procéder à l’applet de passe <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Deux options s’offrent à vous pour importer la configuration du groupe de réponses du pool A à la liste B. L’option utilisée varie selon que vous voulez remplacer les paramètres au niveau de l’application du pool B par les paramètres au niveau de l’application dans le groupe A.
    
      - Si vous voulez remplacer les paramètres du pool B, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne voulez pas remplacer les paramètres du pool B, utilisez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Rappelez-vous que si vous ne voulez pas remplacer les paramètres au niveau de l’application du pool de sauvegarde (pool B) avec les paramètres du pool principal (pool A), les paramètres au niveau de l’application de regroupement seront perdus si le pool A est perdu, car l’application de groupe de réponse peut ne stockez qu’un ensemble de paramètres au niveau de l’application par liste. Lorsque le pool C est déployé pour remplacer le pool A, les paramètres au niveau de l’application doivent être reconfigurés, y compris le fichier audio par défaut de musique.

    
    </div>

5.  Vérifiez que l’importation de la configuration du groupe de réponse a réussi en exécutant les applets de commande suivantes pour afficher les groupes de réponse importés. Notez que les groupes de réponse importés sont encore possédés par le groupe A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Pour les numéros non attribués, déplacez les plages de numéros non affectées qui utilisent «annonce» en tant que service d’annonce sélectionné du pool A à pool B. Pour cela, procédez comme suit:
    
      - Recréez toutes les annonces qui ont été déployées dans le pool A du pool B. Si des fichiers audio étaient utilisés lors du déploiement des annonces dans le pool A, ces fichiers seront nécessaires pour recréer les annonces dans le pool B. Pour recréer les annonces dans le pool B, utilisez les applets de nouvelle applet de **CsAnnouncement** , avec le pool b en tant que service parent.
    
      - Reciblez toutes les plages de numéros non attribués ciblant une annonce dans le pool A aux nouvelles annonces déployées dans le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués ciblant une annonce de groupe A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Cette étape n’est pas requise pour les plages de nombres non affectées qui utilisent le service d’annonce «Exchange UM».

    
    </div>

7.  Basculez le pool A vers le pool B en mode de reprise après sinistre (DR) en exécutant l’applet de commande suivante:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Pool de génération C, mais ne démarrez aucun service sur le pool C.
    
    Notez que cette étape peut être effectuée en même temps que les étapes 5 et 6.

9.  Faites en sorte que les utilisateurs hébergés sur le pool A puissent accéder au pool C en exécutant l’applet de commande suivante:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    À ce stade, les utilisateurs hébergés sur le pool A commenceront à utiliser une panne de service. Cette interruption continuera jusqu’à l’étape 16, à partir de laquelle les services de pointage sont démarrés sur le pool C.

10. Forcez le répertoire de conférences du groupe A à déplacer vers le pool C en exécutant l’applet de commande suivante:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Forcez l’objet de contact de la Conférence automatique (CAA) à passer du pool A au pool C en exécutant l’applet de commande suivante:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copier le contenu d’une conférence du pool B vers le pool C.

13. Exportez les données utilisateur à partir du pool B et importez les données utilisateur dans le pool C en exécutant les applets de commande suivantes:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaurez les données d’application du parc d’appels sauvegardés à partir du pool A dans le pool C et attribuez-leur les plages d’orbites du pool A au pool C.
    
      - Vous pouvez réattribuer une plage d’orbites du pool A au pool C à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell. Pour Lync Server Management Shell, exécutez l’applet de commande suivante pour chaque plage d’orbite de parc d’appels affectée au pool A (Notez que le paramètre Identity fait référence à des plages d’orbite de parking qui appartiennent au pool A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si un morceau de musique personnalisé a été configuré pour le parc d’appels dans le pool A, restaurez le parc d’appels personnalisé musique en attente dans le pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Par exemple :
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Pour finir, reconfigurez les paramètres de parc d’appels sur le pool C à l’aide de l’applet de la cmdlet **Set-CsCpsConfiguration** . L’application de parc d’appels ne peut stocker qu’un seul ensemble de paramètres et un fichier audio en attente personnalisé par liste, et ces paramètres ne sont pas sauvegardés ou conservés en cas de sinistre.

15. Si le pool de prochains tronçons pour une conversation permanente pointe vers le regroupement A, effectuez et publiez les modifications de topologie de telle sorte que le serveur du tronçon suivant pointe vers le pool C.
    
      - Dans le générateur de topologie, modifiez le pool de conversation permanente de manière à ce qu’il pointe vers le pool C comme tronçon suivant. Pour ce faire, cliquez avec le bouton droit de la touche dans la liste de conversations permanentes, cliquez sur l’onglet **général** , puis tapez le nom du pool C dans le **pool de sauts suivant**.
    
      - Démarrez les services sur le pool C en exécutant l’applet de commande suivante:
        
            Start-csWindowsService
    
    À ce stade, l’interruption du service se termine pour les utilisateurs initialement hébergés sur le pool A.

16. Exportez les flux de travail du service de groupe de réponse de Lync Server du pool B possédé par le pool A pour l’importation dans le pool C en exécutant l’applet de commande suivante:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importez les flux de travail du service de groupe de réponse de Lync Server dans le pool C du pool B.
    
    Deux options s’offrent à vous pour importer la configuration de groupe de réponses du pool B au pool C. L’option utilisée varie selon que vous voulez remplacer les paramètres au niveau de l’application du pool C par les paramètres au niveau de l’application dans le pool B.
    
      - Si vous voulez remplacer les paramètres C du pool, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne voulez pas remplacer les paramètres C du pool, utilisez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Gardez à l’esprit que si vous ne voulez pas remplacer les paramètres au niveau de l’application du pool C avec les paramètres du pool de sauvegarde (pool B), les paramètres au niveau de l’application du pool B seront perdus, car l’application du groupe de réponse ne peut stocker qu’un seul ensemble de niveau application. paramètres par liste.

    
    </div>

18. Vérifiez que l’importation de la configuration du groupe de réponse a été réussie en exécutant les applets de commande suivants pour afficher les groupes de réponse ayant été importés dans le pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Lorsque la configuration importée a été vérifiée dans le pool C, supprimez les groupes de réponse appartenant au pool principal du pool B. Cela permet de réduire les temps d’arrêt des groupes de réponse.
    
    Cette étape permet de créer un fichier avec la configuration exportée, puis de supprimer le fichier du pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Déplacer vers le groupe C les plages de numéros non affectées qui ont été déplacées du pool A au pool B.
    
      - Recréer dans le pool C toutes les annonces qui ont été recréées à partir du pool A dans le pool B. Si des fichiers audio étaient utilisés lors du déploiement des annonces à déplacer, vous devrez utiliser ces fichiers pour recréer les annonces dans le pool C. Pour recréer les annonces dans le pool C, utilisez les applets de nouvelle applet de **nouvelle-CsAnnouncement** , avec le service parent du pool c.
    
      - Reciblez le pool C toutes les plages de numéros non attribuées qui ont été reciblées du pool A vers le pool B. Exécutez l’applet de commande suivante pour chaque plage de nombres non affectée qui doit être reciblée:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Facultatif Supprimer du groupe B les annonces qui ont été recréées dans le pool C, si elles ne sont plus utilisées dans le pool B. Pour supprimer des annonces, utilisez l’applet de passe **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Cette étape n’est pas requise pour les plages de nombres non affectées qui utilisent le service d’annonce «UM Exchange».

        
        </div>

21. Nettoyez les données utilisateur du pool A dans le pool B en exécutant l’applet de commande suivante:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Procédez comme suit dans le générateur de topologie:
    
      - Découpler le pool A et le pool B Supprimez ensuite le regroupement A de la topologie et publiez-le. Pour ce faire :
        
          - Dans le générateur de topologie, cliquez avec le bouton droit sur le pool B, puis cliquez sur **modifier les propriétés**.
        
          - Cliquez **** sur résilience dans le volet gauche.
        
          - Dans la zone située en dessous de **pool de sauvegarde associé**, sélectionnez Pool C. Notez que la zone de sélection de pool de sauvegarde associée affiche le pool a pour la première fois, car le pool B a été précédemment associé au pool.
        
          - Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK **.
            
            Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**. 
        
          - Dans l’arborescence de la console, cliquez avec le bouton droit sur l’ensemble de la liste, puis cliquez sur supprimer.
        
          - Publiez la topologie.

23. Exécutez l’application de démarrage sur le pool C pour installer l’application de service de sauvegarde, puis démarrez l’application de service de sauvegarde en exécutant la commande suivante à partir du dossier de déploiement sur un ordinateur local dans le pool C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Redémarrez l’application de service de sauvegarde sur le pool B en exécutant les applets de commande suivantes:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. S’il s’agit d’un pool standard édition (SE) et du pool B de CMS, installez la base de données CMS manuellement sur le pool C en exécutant l’applet de commande suivante:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Invoquez le service de sauvegarde pour synchroniser les anciens contenus de conférences du pool B vers le pool C qui a été généré avant de jumeler les paires B et C, et pour synchroniser le nouveau contenu de conférences du pool C vers le pool B qui a été généré après le démarrage du pool C et avant le jumelage entre B et C. Pour cela, exécutez les applets de commande suivantes:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Pour chaque appareil de branchement Survivable X associé au pool A:
    
      - Arrêtez l’argument SBA X en exécutant l’applet de commande suivante:
        
            Stop-CsWindowsService
    
      - Créez un fichier contenant une liste d’utilisateurs hébergés sur SBA X. La liste sera nécessaire lorsque les utilisateurs seront redirigés vers SBA X à l’étape 30. Pour cela, exécutez l’applet de commande suivante:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Faites en sorte que les utilisateurs hébergés sur SBA X soient déplacés vers le pool C en exécutant l’applet de commande suivante:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Mettez à jour les données de ces utilisateurs en exécutant d’abord les applets de commande suivantes:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Puis exécutez le script suivant:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Une panne de service survient pour les utilisateurs qui sont hébergés sur SBAs qui sont associés au pool A jusqu’à ce que ces utilisateurs soient déplacés vers le pool C.

        
        </div>

28. Dans le générateur de topologie, pour chaque SBA X précédemment associé au pool A, procédez comme suit:
    
      - Remplacez l’Association par le pool C. Pour cela, cliquez sur le site de la succursale, développez le nœud périphériques et périphériques Survivables, puis cliquez sur **appareil de branchement Survivable**. Sélectionnez ensuite le pool **frontal, le pool de services d’utilisateurs** auquel cette application de branche Survivable sera connectée en tant que Pool C, puis cliquez sur **suivant**.
    
      - Publiez la topologie. Pour ce faire, dans l’arborescence de la console, cliquez avec le bouton droit sur la nouvelle **application branche Survivable**, cliquez sur **Topology**, puis sur **publier**.

29. Pour chaque SBA X désormais associé au pool C:
    
      - Démarrez SBA X en exécutant l’applet de commande suivante sur l’unité de commande Survivable:
        
            Start-CsWindowsService
    
      - Déplacez les utilisateurs initialement hébergés sur SBA X du pool C à SBA X en exécutant l’applet de commande suivante.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

