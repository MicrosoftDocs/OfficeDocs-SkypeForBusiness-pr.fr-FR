---
title: Association de rapports de surveillance avec une base de données miroir
TOCTitle: Association de rapports de surveillance avec une base de données miroir
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945624(v=OCS.15)
ms:contentKeyID: 53095402
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Association de rapports de surveillance avec une base de données miroir

 

_**Dernière rubrique modifiée :** 2014-02-07_

Si vous configurez une instance miroir pour votre base de données de surveillance, cette base de données miroir prendra la relève en tant que base de données principale en cas de basculement. Toutefois, si vous utilisez les rapports de surveillance Lync Server et qu'un basculement se produit, vous pourriez constater que vos rapports de surveillance ne se connectent pas à la base de données miroir. Et ce, car, lorsque vous installez des rapports de surveillance, vous spécifiez seulement l'emplacement de la base de données principale ; vous devez aussi spécifier l'emplacement de la base de données miroir.

Pour que les rapports basculent automatiquement sur la base de données miroir, vous devez ajouter la base de données miroir comme « partenaire de basculement » pour les deux bases de données utilisées par les rapports de surveillance (l'une pour les données d'enregistrement des détails des appels, et l'autre pour les données de la qualité de l'expérience (QoE)). (Notez que cette étape doit être effectuée après l'installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire de basculement en modifiant manuellement les valeurs des chaînes de connexion utilisées par ces deux bases de données. Pour cela, procédez comme suit :

1.  Utilisez Internet Explorer pour ouvrir la page d'accueil de **SQL Server Reporting Services**. L'URL de cette page d'accueil comprend ce qui suit :
    
      - Le préfixe **http:**.
    
      - Le nom de domaine complet (FQDN) de l'ordinateur sur lequel les services de surveillance sont installés (par exemple, **atl-sql-001.litwareinc.com**).
    
      - La chaîne de caractères **/Reports\_**.
    
      - Le nom de l'instance de la base de données où les rapports de surveillance sont installés (par exemple, **archinst**).
    
    Par exemple, si SQL Server Reporting Services a été installé sur l'ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l'instance de base de données archinst, l'URL de la page d'accueil doit ressembler à ceci :
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Après avoir accédé à la page d'accueil des services de surveillance, cliquez sur **LyncServerReports**, puis sur **Reports\_Content**. Vous accédez alors à la page **Reports\_Content** de Lync Server Monitoring Reports.

3.  Sur la page **Reports\_Content**, cliquez sur la source de données **CDRDB**.

4.  Sur la page **CDRDB**, sous l'onglet **Propriétés**, recherchez le texte intitulé **Chaîne de connexion**. La chaîne de connexion actuelle a un format similaire à celui-ci :
    
    **Data source=(local)\\archinst;initial catalog=LcsCDR**

5.  Modifiez la chaîne de connexion façon à y inclure le nom du serveur et l'instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-miroir-001 et que la base de données miroir est dans l'instance archinst, vous devez en plus spécifier la base de données miroir en utilisant cette syntaxe :
    
    **Failover Partner=atl-mirror-001\\archinst**
    
    Votre chaîne de connexion modifiée ressemblera à ceci :
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**

6.  Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer**.

7.  Sur la page **CDRDB**, cliquez sur le lien **Reports\_Content**. Cliquez sur la source de données **QMSDB**, puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**

8.  Cliquez sur **Appliquer**.

## Voir aussi

#### Concepts

[Installation des rapports de surveillance Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Utilisation des rapports de surveillance dans Lync Server 2013](lync-server-2013-using-monitoring-reports.md)

