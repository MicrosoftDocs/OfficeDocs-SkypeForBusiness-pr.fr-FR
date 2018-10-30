---
title: Configuration des clients pour la migration
TOCTitle: Configuration des clients pour la migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49891437
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des clients pour la migration

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique recense les étapes de déploiement des clients qu’il est recommandé d’effectuer avant de procéder à la migration vers Lync Server 2013. Ces modifications de configuration doivent être apportées sur Office Communications Server 2007 R2. Il est très important que vous suiviez ces étapes avant de procéder à la migration. Pour plus d’informations, reportez-vous à [Planification des clients et périphériques dans Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

## Pour configurer les clients avant la migration

1.  Déployez les mises à jour (correctifs logiciels) les plus récentes pour les serveurs, les clients et les périphériques Office Communications Server 2007 R2 :
    
      - [Application des mises à jour d’Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Description du package cumulatif de mise à jour pour Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtaining Software Updates for Devices](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour autoriser uniquement la connexion des clients Office Communications Server 2007 R2 disposant des mises à jour les plus récentes.

3.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour empêcher les clients Lync Server 2013 de se connecter. Suivez les étapes décrites dans l’article **Configuration du filtrage de version du client** disponible à l’adresse [http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0x40c) pour ajouter les filtres de version répertoriés dans le tableau suivant. Pour chaque filtre de version, affectez l’action **Bloquer** .
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>En-tête d’agent utilisateur</th>
    <th>Version</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>

