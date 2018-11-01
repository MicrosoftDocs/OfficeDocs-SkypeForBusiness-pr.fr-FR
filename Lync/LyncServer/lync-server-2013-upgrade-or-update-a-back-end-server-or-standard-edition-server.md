---
title: "Màn ou màj serv. princ. ou serveur Standard Edition Server dans LS 2013"
TOCtitle: "Màn ou màj serv. princ. ou serveur Standard Edition Server dans LS 2013"
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49891619
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mise à niveau ou mise à jour d’un serveur principal ou d’un serveur Standard Edition Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Cette rubrique explique comment installer une mise à jour sur un serveur principalEnterprise Edition ou un serveur Standard Edition.

Si un serveur principal est arrêté durant au moins 30 minutes lors de sa mise à niveau, les utilisateurs peuvent être placés en mode Résilience. Lorsque la mise à mise à niveau est terminée et que les serveurs principaux sont encore connectés aux serveurs frontaux du pool, les utilisateurs repassent en fonctionnalité complète. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne seront pas affectés.

## Pour mettre à jour un serveur principal ou un serveur Standard Edition

1.  Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.

2.  Téléchargez la mise à jour et extrayez-la sur le disque dur local.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Arrêtez les services Lync Server. À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

5.  Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net stop w3svc

6.  Fermez toutes les fenêtres Lync Server Management Shell.

7.  Installez la mise à jour.

8.  Démarrez Lync Server Management Shell : Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

9.  Arrêtez de nouveau les services Lync Server pour rattraper les assemblys mis dans le Global Assembly Cache (GAC). À partir de la ligne de commande, tapez :
    
        Stop-CsWindowsService

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
        net start w3svc

11. Appliquez les modifications apportées par LyncServerUpdateInstaller.exe sur les bases de données SQL Server en effectuant l’une des opérations suivantes :
    
      - S’il s’agit d’un serveur principalEnterprise Edition et qu’il n’y a aucune base de données colocalisée sur ce serveur (par exemple, des bases de données d’archivage ou de surveillance), alors tapez ce qui suit sur la ligne de commande :
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - S’il s’agit d’un serveur principalEnterprise Edition et que ce serveur contient des bases de données colocalisées, alors tapez ce qui suit sur la ligne de commande :
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - S’il s’agit d’un serveur Standard Edition, tapez ce qui suit sur la ligne de commande :
        
            Install-CsDatabase -Update -LocalDatabases

