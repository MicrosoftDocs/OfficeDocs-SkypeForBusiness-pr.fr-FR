---
title: 'Lync Server 2013 : Procédure de basculement ABC vers un pool frontal'
TOCTitle: Procédure de basculement ABC vers un pool frontal
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945635(v=OCS.15)
ms:contentKeyID: 53095443
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procédure de basculement ABC vers un pool frontal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-05-22_

Exécutez les étapes suivantes pour effectuer la procédure de basculement ABC. Cette procédure contient une description de haut niveau de chaque étape, suivie de commandes et d’applets de commande à exécuter pour chaque étape.

Pour exécuter les applets de commande, ouvrez Lync Server Management Shell avec l’option Exécuter en tant qu’administrateur.

## Pour effectuer un basculement ABC

1.  Vérifiez si le pool A est l’hôte du serveur de gestion centralisée.
    
      - Exécutez l’applet de commande suivante :
        
            Get-CsService -CentralManagement
        
        Si le champ Identity du serveur de gestion centralisée actif pointe sur le nom de domaine complet du Pool A, vous devez effectuer les étapes 2 et 3 de cette procédure pour procéder d’abord au basculement du serveur de gestion centralisée. Sinon, passez à l’étape 4.

2.  Procédez au basculement du serveur de gestion centralisée vers le Pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante :
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Après cela, nous vous recommandons de déplacer le serveur de gestion centralisée du pool B vers un autre pool associé existant afin d’augmenter la résistance. Pour plus d’informations, reportez-vous à [Move-CsManagementServer](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsManagementServer).

3.  Si le Pool A contient un serveur de gestion centralisée, importez la configuration LIS du pool A vers la base de données LIS du pool B (Lis.mdf). Cette opération fonctionnera uniquement si vous avez procédé à une sauvegarde régulière des données LIS. Pour importer la configuration LIS, exécutez les applets de commande suivantes :
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importez les flux de travail de service Response Group Lync Server du pool A vers le pool B.
    
    > [!NOTE]  
    > À l’heure actuelle, l’applet de commande <strong>Import-CsRgsConfiguration</strong> exige que les noms de files d’attente et de flux de travail sur le pool A soient distincts de ceux du pool B. Si ce n’est pas le cas, une erreur se produit lors de l’exécution de l’applet de commande <strong>Import-CsRgsConfiguration</strong> et les files d’attente et flux de travail devront être renommés dans le pool B avant de poursuivre l’exécution de l’applet de commande <strong>Import-CsRgsConfiguration</strong>.    
    
    
    Deux options sont disponibles pour l’importation de la configuration Response Group du pool A vers le pool B. L’option choisie variera selon que vous souhaitez remplacer les paramètres de niveau application du pool B par ceux du pool A.
    
      - Si vous souhaitez remplacer les paramètres du pool B, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings**  :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne souhaitez pas remplacer les paramètres du pool B, exécutez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]  
    > Sachez que si vous ne souhaitez pas remplacer les paramètres de niveau application du pool de sauvegarde (pool B) par les paramètres du pool principal (pool A), les paramètres de niveau application du pool A seront perdus en cas de perte du pool A, car l’application Response Group ne peut stocker qu’un jeu de paramètres de niveau application par pool. Lors du déploiement du pool C pour remplacer le pool A, les paramètres de niveau application doivent être reconfigurés, dont le fichier audio de mise en attente musicale.

5.  Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les applets de commande suivantes pour afficher les groupes Response Group importés. Notez que le pool A est toujours propriétaire des groupes Response Group importés.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Pour les numéros non attribués, déplacez les plages de numéros non attribués qui utilisent « Annonce » comme service d’annonce sélectionné du pool A vers le pool B. Pour cela :
    
      - Recréez toutes les annonces qui ont été déployées dans le pool A sur le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces dans le pool A, ils seront nécessaires pour recréer les annonces dans le pool B. Pour recréer les annonces dans le pool B, utilisez les applets de commande **New-CsAnnouncement** avec le pool B comme service parent.
    
      - Reciblez toutes les plages de numéros non attribués qui ciblent une annonce dans le pool A vers les annonces nouvellement déployées dans le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués qui cible une annonce du pool A :
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    > [!NOTE]  
    > Cette étape n’est pas nécessaire pour les plages de numéros non attribués qui utilisent « Messagerie unifiée Exchange » comme service d’annonce sélectionné.

7.  Procédez au basculement du pool A vers le Pool B en mode de récupération d’urgence en exécutant l’applet de commande suivante :
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Générez le pool C, mais ne démarrez aucun service dessus.
    
    Notez que cette étape peut être exécutée en même temps que les étapes 5 et 6.

9.  Forcez le déplacement des utilisateurs hébergés sur le pool A vers le pool C en exécutant l’applet de commande suivante :
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    À ce stade, les utilisateurs hébergés sur le pool A commenceront à subir une panne du service qui se poursuivra jusqu’à l’étape 16, où les services seront démarrés sur le pool C.

10. Forcez le déplacement de l’annuaire des conférences du pool A vers le pool C en exécutant l’applet de commande suivante :
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Forcez le déplacement de l’objet de contact Standard automatique des conférences du pool A vers le pool C en exécutant l’applet de commande suivante :
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copiez le contenu des conférences du pool B vers le pool C.

13. Exportez les données utilisateur du pool B et importez les données utilisateur dans le pool C en exécutant les applets de commande suivantes :
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaurez les données d’application Parcage d’appel sauvegardées du pool A vers le pool C et affectez les plages d’orbites de parcage d’appel du pool A au pool C.
    
      - Vous pouvez réaffecter une plage d’orbites de parcage d’appel du pool A au pool C par le biais du Panneau de configuration de Lync Server ou à l’aide de Lync Server Management Shell. Pour Lync Server Management Shell, exécutez l’applet de commande suivante pour chaque plage d’orbites de parcage d’appel affectée au pool A (notez que le paramètre Identity fait référence aux plages d’orbites de parcage d’appel qui appartiennent au pool A) :
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si une mise en attente musicale personnalisée a été configurée pour le Parcage d’appel dans le pool A, restaurez le fichier de mise en attente musicale personnalisé de Parcage d’appel dans le pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Exemple :
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Pour finir, reconfigurez les paramètres de parcage d’appel sur le pool C à l’aide de l’applet de commande **Set-CsCpsConfiguration**. L’application Parcage d’appel peut stocker un seul jeu de paramètres et un seul fichier audio de mise en attente musicale personnalisé par pool, et ces paramètres ne sont pas sauvegardés ou conservés en cas de sinistre.

15. Si le pool de tronçon suivant pour la conversation permanente pointe sur le pool A, apportez des modifications de topologie et publiez-les de sorte que le serveur de tronçon suivant pointe sur le pool C.
    
      - Dans le générateur de topologie, modifiez le pool de conversation permanente de sorte qu’il pointe vers le pool C comme tronçon suivant. Pour cela, cliquez avec le bouton droit sur le pool de conversation permanente, cliquez sur l’onglet **Général** , puis tapez le nom du pool C dans **Pool du tronçon suivant** .
    
      - Démarrez les services sur le pool C en exécutant l’applet de commande suivante :
        
            Start-csWindowsService
    
    À ce stade, le service est rétabli pour les utilisateurs hébergés à l’origine sur le pool A.

16. Exportez les flux de travail de service Response Group Lync Server du pool B détenus par le pool A pour importation dans le pool C en exécutant l’applet de commande suivante :
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importez les flux de travail de service Response Group Lync Server du pool B vers le pool C.
    
    Deux options sont disponibles pour l’importation de la configuration Response Group du pool B vers le pool C. L’option choisie variera selon que vous souhaitez remplacer les paramètres de niveau application du pool C par ceux du pool B.
    
      - Si vous souhaitez remplacer les paramètres du pool C, exécutez l’applet de commande **Import-CsRgsConfiguration** avec l’option **ReplaceExistingSettings**  :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si vous ne souhaitez pas remplacer les paramètres du pool C, exécutez l’applet de commande **Import-CsRgsConfiguration** sans l’option **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]  
    > Sachez que si vous ne souhaitez pas remplacer les paramètres de niveau application du pool C par les paramètres du pool de sauvegarde (pool B), les paramètres de niveau application du pool B seront perdus car l’application Response Group ne peut stocker qu’un jeu de paramètres de niveau application par pool.

18. Vérifiez que l’importation de la configuration Response Group a réussi en exécutant les applets de commande suivantes pour afficher les groupes Response Group qui ont été importés dans le pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Une fois la configuration importée vérifiée dans le pool C, supprimez du pool B les groupes Response Group détenus par le pool principal. Cela permettra de limiter le temps mort des groupes Response Group.
    
    Cette étape crée un fichier avec la configuration exportée, puis le supprime du pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Déplacez vers le pool C les plages de numéros non attribués qui ont été déplacées du pool A vers le pool B.
    
      - Recréez dans le pool C toutes les annonces qui ont été recréées à partir du pool A dans le pool B. Si des fichiers audio ont été utilisés lors du déploiement des annonces à déplacer, vous aurez besoin de ces fichiers pour recréer les annonces dans le pool C. Pour recréer les annonces dans le pool C, utilisez les applets de commande **New-CsAnnouncement** avec le pool C comme service parent.
    
      - Reciblez sur le pool C toutes les plages de numéros non attribués qui ont été reciblées du pool A vers le pool B. Exécutez l’applet de commande suivante pour chaque plage de numéros non attribués qui doit être reciblée :
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - (Facultatif) Supprimez du pool B les annonces qui ont été recrées dans le pool C si elles ne sont plus utilisées dans le pool B. Pour supprimer des annonces, utilisez l’applet de commande **Remove-CsAnnouncement**.
        
        > [!NOTE]  
        > Cette étape n’est pas nécessaire pour les plages de numéros non attribués qui utilisent « Messagerie unifiée Exchange » comme service d’annonce.

21. Nettoyez les données utilisateur du pool A dans le pool B en exécutant l’applet de commande suivante :
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Procédez comme suit dans le générateur de topologie :
    
      - Dissociez le pool A et le pool B. Associez le pool B et le pool C. Ensuite, supprimez le pool A de la topologie et publiez-la. Pour cela, procédez comme suit :
        
          - Dans le générateur de topologie, cliquez avec le bouton droit sur le pool B, puis cliquez sur **Modifier les propriétés** .
        
          - Cliquez sur **Résistance** dans le volet gauche.
        
          - Dans la zone sous **Pool de stockage associé** , sélectionnez le pool C. Notez que la zone de sélection Pool de stockage associé affiche initialement le pool A, car le pool B était précédemment associé à ce pool.
        
          - Sélectionnez **Basculement et restauration automatiques pour Voice** , puis cliquez sur **OK** .
            
            Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance** .
        
          - Dans l’arborescence de la console, cliquez avec le bouton droit sur le pool A, puis cliquez sur Supprimer.
        
          - Publiez la topologie.

23. Exécutez l’application de démarrage sur le pool C pour installer l’application de service de sauvegarde, puis démarrez l’application de service de sauvegarde en exécutant la commande suivante à partir du dossier de déploiement sur un ordinateur local dans le pool C :
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Redémarrez l’application de service de démarrage sur le pool B en exécutant les applets de commande suivantes :
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Si le pool C est un pool Standard Edition (SE) et que le pool B possède un serveur de gestion centralisée, installez la base de données du serveur de gestion centralisée manuellement sur le pool C en exécutant l’applet de commande suivante :
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Exécutez le service de sauvegarde pour synchroniser l’ancien contenu de conférence du pool B vers le pool C qui a été généré avant l’association des pools B et C et pour synchroniser le nouveau contenu de conférence du pool C vers le pool B qui a été généré après le démarrage du pool C et avant l’association des pools B et C. Pour cela, exécutez les applets de commande suivantes :
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Pour chaque Survivable Branch Appliance X associé au pool A :
    
      - Arrêtez le SBA X en exécutant l’applet de commande suivante :
        
            Stop-CsWindowsService
    
      - Créez un fichier qui contient une liste des utilisateurs hébergés sur le SBA X. Cette liste sera nécessaire lors du redéplacement des utilisateurs vers le SBA X à l’étape 30. Pour cela, exécutez l’applet de commande suivante :
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Forcez le déplacement des utilisateurs hébergés sur le SBA X vers le pool C en exécutant l’applet de commande suivante :
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Mettez à jour les données de ces utilisateurs en exécutant d’abord les applets de commande suivantes :
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Exécutez ensuite le script suivant :
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        > [!NOTE]  
        > Les utilisateurs hébergés sur des SBA associés au pool A subiront une panne du service jusqu’à ce qu’ils soient déplacés vers le pool C.

28. Dans le générateur de topologie, pour chaque SBA X précédemment associé au pool A, procédez comme suit :
    
      - Modifiez l’association au pool C. Pour cela, cliquez sur le site de succursale, développez le nœud Survivable Branch Appliances ou Serveurs, puis cliquez sur **Survivable Branch Appliance** . Ensuite, sélectionnez le **pool frontal, pool de services d’utilisateurs** auquel ce Survivable Branch Appliance se connectera en tant que pool C, puis cliquez sur **Suivant** .
    
      - Publiez la topologie. Pour cela, dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau **Survivable Branch Appliance** , cliquez sur **Topologie** , puis sur **Publier** .

29. Pour chaque SBA X maintenant associé au pool C :
    
      - Démarrez le SBA X en exécutant l’applet de commande suivante sur le survivable branch appliance :
        
            Start-CsWindowsService
    
      - Déplacez les utilisateurs initialement hébergés sur le SBA X du pool C vers le SBA X en exécutant l’applet de commande suivante.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

