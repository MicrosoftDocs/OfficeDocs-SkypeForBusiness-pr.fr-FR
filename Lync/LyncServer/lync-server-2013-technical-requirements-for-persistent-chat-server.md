---
title: "Lync Server 2013 : Conf. tech. pour le serveur de conversation permanente"
TOCTitle: Configuration technique requise pour le serveur de conversation permanente
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398495(v=OCS.15)
ms:contentKeyID: 49297487
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Chaque ordinateur qui héberge un serveur de conversations permanentes doit avoir accès à une topologie Lync Server 2013 existante avec les composants suivants :

  - **Lync Server 2013,  serveur frontal.** Le serveur frontal constitue la base du routage SIP (Session Initiation Protocol) qui rend possible la communication entre les ordinateurs exécutant le serveur de conversations permanentes et la fonctionnalité de conversation permanente. Avant de commencer à déployer le serveur de conversations permanentes, vérifiez le déploiement de Lync Server 2013, Standard Edition ou d’un pool de serveurs frontauxLync Server, mais aussi des autres ordinateurs internes exécutant Lync Server, selon les besoins de votre organisation.

Les sections suivantes décrivent la configuration requise pour le serveur de conversations permanentes et la base de données qui stocke les données conversation permanente.

## Configuration requise pour serveur de conversations permanentes

Pour plus d’informations sur le matériel recommandé pour le déploiement de Lync Server et la dernière version du serveur de conversations permanentes, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

Pour plus d’informations sur la prise en charge du système d’exploitation pour le serveur et les outils, pour Lync Server et le serveur de conversations permanentes, reportez-vous à [Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Pour plus d’informations sur les logiciels supplémentaires requis pour le déploiement du serveur de conversations permanentes, reportez-vous au tableau suivant.

### Logiciels prérequis pour le serveur de conversations permanentes

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciels</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Message Queuing</p></td>
<td><p>Utilisé par le service de conformité du serveur de conversations permanentes et de conversation permanente s’il est déployé.</p></td>
</tr>
</tbody>
</table>


## Configuration requise pour les bases de données du serveur de conversations permanentes

Le serveur de conversations permanentes utilise la base de données de conversation permanente pour stocker l’historique des conversations, la configuration et les données de provisionnement d’utilisateur. Il utilise éventuellement la base de données de conformité de conversation permanente pour stocker les données de conformité.

> [!IMPORTANT]  
> La base de données de conversation permanente (mgc) et la base de données de conformité (mgccomp) peuvent se trouver sur la même instance de SQL Server ou sur des serveurs SQL Server différents.

Pour préparer une plateforme de serveur de base de données, vérifiez que chaque ordinateur respecte la configuration matérielle requise, puis installez les logiciels prérequis.

La plateforme de serveur pour les serveurs de base de données de conversation permanente requiert le même matériel que le serveur de la base de données principale Lync Server. Pour plus d’informations, reportez-vous à [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

Sur le serveur de bases de données, vérifiez que l’une des applications logicielles suivantes est installée :

  - Microsoft SQL Server 2012. Pour plus d’informations sur l’installation de Microsoft SQL Server 2012, reportez-vous à « Installer SQL Server 2012 » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Pour plus d’informations sur l’installation de Microsoft SQL Server 2008 R2, reportez-vous à « Installation SQL Server (SQL Server 2008 R2) » à l’adresse [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).

## Exigences en matière de certificats pour le serveur de conversations permanentes

Pour plus d’informations sur l’acquisition de certificats, la création de la base de données SQL Server et la création de magasins de fichiers, reportez-vous à [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md) (contenu éventuellement en anglais) dans la documentation relative au déploiement.

