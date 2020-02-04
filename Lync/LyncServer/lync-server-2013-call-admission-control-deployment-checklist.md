---
title: 'Lync Server 2013 : liste de vérification de déploiement de contrôle d’admission des appels'
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
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Liste de contrôle du déploiement de contrôle d’admission des appels pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Utilisez la liste de vérification suivante pour vérifier que vous avez effectué toutes les tâches de configuration nécessaires pour déployer le contrôle d’admission des appels (CAC).

  - Si au moins un serveur Edge est déployé, chaque adresse IP de l’interface externe doit être ajoutée à la liste des sous-réseaux dans les paramètres de configuration du réseau, avec un masque de bits de 32. Vous devez également associer ce sous-réseau (adresse IP) à l’ID de site réseau pour l’emplacement géographique auquel le service Edge A/V est déployé.
    
    <div>
    

    > [!NOTE]  
    > Il n’est pas nécessaire de mettre en place des serveurs de périphérie pour le CAC.

    
    </div>

  - Assurez-vous que l’option CAC est activée via le panneau de configuration de Lync Server ou en exécutant l’applet de commande, comme indiqué dans [activer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Vérifiez que le contrôle d’admission des appels est activé sur tous les sites centraux. Cette opération peut être réalisée par le biais du générateur de topologie. Si un avertissement s’affiche lors de la publication, ne l’ignorez *pas*.

  - Vérifiez que tous les sous-réseaux gérés dans le réseau d’entreprise sont configurés dans les paramètres de configuration réseau. Il est également essentiel que chaque sous-réseau soit associé à un site réseau, comme décrit dans la rubrique [associez un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Vérifiez que les adresses IP ou de sous-réseau de tous les serveurs frontaux, SBA (Survivable Branch Appliances), serveurs de conférence audio/vidéo (s’ils figurent dans un pool distinct) et serveurs de médiation sont configurées dans les paramètres de configuration réseau.

</div>

<span> </span>

</div>

</div>

</div>

