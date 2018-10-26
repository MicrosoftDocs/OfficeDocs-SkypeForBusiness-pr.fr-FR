---
title: Restauration d’un serveur Standard Edition
TOCTitle: Restauration d’un serveur Standard Edition
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202190(v=OCS.15)
ms:contentKeyID: 53095531
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration d’un serveur Standard Edition

 

_**Dernière rubrique modifiée :** 2013-02-21_

Si un serveur Standard Edition qui n’héberge pas le magasin central de gestion est défaillant, suivez les procédures indiquées dans cette section. En cas d’échec du magasin central de gestion, voir [Restauration du serveur hébergeant le magasin central de gestion](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

> [!TIP]  
> Nous vous recommandons de faire une image du système avant de démarrer la restauration. Vous pourrez utiliser cette copie comme point de restauration au cas où un problème surviendrait lors de la restauration. Il peut être préférable de créer cette copie instantanée après avoir installé le système d’exploitation et SQL Server et après avoir restauré ou réinscrit les certificats.

## Pour restaurer un serveur Standard Edition

1.  Démarrez avec un nouveau serveur ayant le même nom de domaine complet que l’ordinateur ayant subi une défaillance, installez le système d’exploitation, puis restaurez ou réinscrivez les certificats.
    
    > [!NOTE]  
    > Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs locaux, ouvrez une session sur le serveur que vous êtes en train de restaurer.

3.  Restaurez le magasin de fichiers en copiant le magasin de fichiers approprié depuis $Backup vers l’emplacement du magasin de fichiers sur le serveur, puis partagez le dossier.
    
    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être strictement identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.

4.  Exécutez le Générateur de topologie :
    
    1.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.

5.  Accédez au dossier ou support d’installation de Lync Server, démarrez l’Assistant Déploiement de Lync Server situé à l’emplacement \\setup\\amd64\\Setup.exe. Utilisez l’Assistant Déploiement de Lync Server pour effectuer ce qui suit :
    
    1.  Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l’**Étape 2 : Installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.
    
    3.  Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.
    
    4.  Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement relative au rôle serveur que vous restaurez.

6.  Restaurez les données utilisateur en effectuant ce qui suit :
    
    1.  Copiez le fichier ExportedUserData.zip depuis $Backup\\ vers un répertoire local.
    
    2.  Avant de restaurer les données utilisateurs, vous devez arrêter les services Lync. Pour cela, tapez :
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, à la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez les services Lync en tapant :
        
            Start-CsWindowsService

7.  Si vous avez déployé Response Group sur ce serveur Standard Edition, restaurez les données de configuration Response Group. Pour plus d’informations, voir [Restauration des paramètres Response Group](lync-server-2013-restoring-response-group-settings.md).

8.  Si vous avez déployé la conversation permanente sur ce serveur Standard Edition, restaurez la base de données de conversation permanente (mgc.mdf).
    
    Si vous avez utilisé la Sauvegarde SQL Server pour sauvegarder la base de données de conversation permanente, appliquez les procédures de restauration SQL Server pour la restaurer.
    
    Si vous avez utilisé l’applet de commande Export-CsPersistentChatData pour la sauvegarder, exécutez Import-CsPersistentChatData pour la restaurer.

