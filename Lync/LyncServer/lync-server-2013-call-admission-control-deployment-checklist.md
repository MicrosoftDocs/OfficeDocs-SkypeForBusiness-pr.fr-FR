---
title: 'Lync Server 2013 : liste de vérification du déploiement du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a8dc32eb017baf832128301b9639aefe23ae4ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Liste de vérification du déploiement du contrôle d’admission des appels pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Servez-vous de la liste de contrôle suivante pour vérifier que vous avez exécuté toutes les tâches de configuration nécessaires au déploiement du contrôle d’admission des appels (CAC).

  - Si un ou plusieurs serveurs Edge sont déployés, chaque adresse IP de l’interface externe doit être ajoutée à la liste de sous-réseaux dans les paramètres de configuration réseau, avec un masque de 32 bits. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique où est déployé le service Edge A/V.
    
    <div>
    

    > [!NOTE]  
    > Il n’est pas obligatoire que les serveurs Edge implémentent le contrôle d’admission des appels.

    
    </div>

  - Assurez-vous que le contrôle d’admission des appels est activé, soit via le panneau de configuration de Lync Server, soit en exécutant l’applet de commande, comme indiqué dans [Enable Call Admission Control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Pour ce faire, vous pouvez utiliser le générateur de topologie. Si un avertissement s’affiche lors de la publication, ne l’ignorez *pas*.

  - Vérifiez que tous les sous-réseaux qui sont gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme expliqué dans [Associate a Subnet with a Network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence Audio/Vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.

</div>

<span> </span>

</div>

</div>

</div>

