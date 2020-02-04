---
title: 'Lync Server 2013 : suppression des régions réseau existantes'
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
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Supprimer des zones réseau existantes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Chaque région du réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution. Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer des régions réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour supprimer des régions réseau existantes. Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [création ou modification des régions réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-delete-a-network-region"></a>Pour supprimer une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **région**.

4.  Dans la page **zone** , cliquez sur la zone que vous voulez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs régions tout en maintenant la touche CTRL enfoncée. Vous pouvez sélectionner toutes les <STRONG>régions dans le</STRONG> menu <STRONG>Edition</STRONG> .

    
    </div>

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!WARNING]  
    > Une région réseau ne peut pas être supprimée si elle est associée à un site réseau. Si vous tentez de supprimer une région associée à un site, vous recevez un message d’erreur. Pour déterminer si une région est associée à des sites, sélectionnez la région, puis cliquez sur <STRONG>afficher les détails</STRONG> dans le menu <STRONG>modifier</STRONG> .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification des régions réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

