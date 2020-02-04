---
title: Configuration des clients pour la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configuration des clients pour la migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-21_

Cette rubrique contient les étapes de déploiement de client recommandées avant de procéder à la migration vers Lync Server 2013. Ces modifications de configuration doivent être apportées à Office Communications Server 2007 R2. Il est très important que vous effectuiez ces étapes avant de procéder à la migration. Pour plus d’informations, reportez-vous à la section [planification des clients et des appareils dans Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Pour configurer des clients avant la migration

1.  Déployez les mises à jour les plus récentes du serveur Office Communications Server 2007 R2, des clients et des appareils (HotFix) :
    
      - [Appliquer des mises à jour d’Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Description du package de mise à jour cumulative pour Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtention des mises à jour logicielles pour les appareils](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version de client pour autoriser uniquement les clients Office Communications Server 2007 R2 avec les mises à jour les plus récentes pour la connexion.

3.  Sur Office Communications Server 2007 R2, utilisez le filtrage de version de client pour empêcher les clients Lync Server 2013 de se connecter. Suivez la procédure décrite dans la rubrique Configuration du filtrage des [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) versions du **client** à l’adresse pour ajouter les filtres de version indiqués dans le tableau suivant. Pour chaque filtre de version, attribuez le **bloc**d’action.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>En-tête de l’agent utilisateur</th>
    <th>Version</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*..* *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*..* *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
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

