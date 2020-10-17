---
title: Configurer les clients pour la migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a0b7bfead8f74e27d8539038cf768b1a85b72e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499561"
---
# <a name="configure-clients-for-migration"></a>Configurer les clients pour la migration

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-21_

Cette rubrique contient les étapes de déploiement de clients recommandées que vous devez prendre avant de migrer vers Lync Server 2013. Ces modifications de configuration doivent être effectuées sur Office Communications Server 2007 R2. Il est très important que vous suiviez ces étapes avant de procéder à la migration. Pour plus d’informations, reportez-vous à la rubrique [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Pour configurer les clients avant la migration

1.  Déployez les dernières mises à jour du serveur, du client et du périphérique Office Communications Server 2007 R2 (correctifs) :
    
      - [Appliquer les mises à jour d’Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Description du package de mise à jour cumulative pour Communicator 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtention de mises à jour logicielles pour les périphériques](https://go.microsoft.com/fwlink/?linkid=335809)

2.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour autoriser uniquement les clients Office Communications Server 2007 R2 sur lesquels les mises à jour les plus récentes sont installées.

3.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour bloquer la connexion des clients Lync Server 2013. Suivez les étapes décrites dans **Configuring Client version Filtering** à [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) la rubrique pour ajouter les filtres de version répertoriés dans le tableau suivant. Pour chaque filtre de version, assignez l’action **Bloquer**.
    
    
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
    <td><p>Lync 2013</p></td>
    <td><p>O</p></td>
    <td><p>15.*.*. *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*. *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*..* *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

