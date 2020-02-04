---
title: 'Lync Server 2013 : création ou modification de régions réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbebccd02b74c4fbfb69225a6397c1dd7cef862d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Création ou modification des régions réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Chaque région du réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution. Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer des régions réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo. Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour créer et modifier des régions réseau. Pour plus d’informations sur la suppression de régions réseau existantes, voir [Suppression de régions réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Pour créer une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur **nouveau**.

5.  Dans la page **nouvelle région** , tapez une valeur dans le champ **nom** . Cette valeur doit être unique dans le cadre de votre déploiement de Microsoft Lync Server 2013.

6.  Dans la liste déroulante **site central** , sélectionnez le site central pour cette région réseau.

7.  La case à cocher **activer le chemin audio alternatif** est activée par défaut. Ce champ détermine si les appels audio seront routés par le biais d’un autre chemin si la bande passante suffisante n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet. Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.

8.  La case à cocher **activer le chemin vidéo alternatif** est activée par défaut. Ce champ détermine si les appels vidéo sont routés par le biais d’une autre trajectoire si la bande passante suffisante n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet. Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.

9.  Facultatif Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région qui ne peut pas être exprimée à l’aide du nom seul.

10. Cliquez sur **Valider**.

La table **site associée** n’est pas utilisée pour créer une région réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, consultez [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Pour modifier une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis cliquez sur **région**.

4.  Dans la page **zone** , cliquez sur la zone que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier la région** , vous pouvez modifier les paramètres d’activation et de désactivation des chemins audio et vidéo, et modifier la description (pour plus de détails, reportez-vous à la section « créer une région réseau » plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à des fins de référence, afin que vous soyez attentif aux sites qui seront affectés lors de la modification des paramètres régionaux.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer des zones réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configurer des régions réseau pour CAC dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

