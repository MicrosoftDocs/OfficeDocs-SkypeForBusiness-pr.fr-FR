---
title: 'Lync Server 2013 : suppression des régions réseau existantes'
description: 'Lync Server 2013 : suppression des régions réseau existantes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b148f0bd92ad398ab7057a5a291bf3245df3e47e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552670"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Suppression des régions réseau existantes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour supprimer des régions réseau. Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [Creating or Modifying Network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Pour supprimer une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région à supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur la touche Ctrl et, tout en la maintenant enfoncée, sélectionnez plusieurs régions. Pour sélectionner toutes les régions, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Vous ne pouvez pas supprimer une région réseau si elle est associée à un site réseau. Si vous essayez, un message d’erreur s’affiche. Pour savoir si une région est associée à des sites, sélectionnez-la, puis cliquez sur <STRONG>Afficher les détails</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification de régions réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

