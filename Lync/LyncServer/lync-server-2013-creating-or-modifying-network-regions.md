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
ms.openlocfilehash: 52518c76efdb302661ed3f097cb382d399299798
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Création ou modification de régions réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour créer et modifier des régions réseau. Pour plus d’informations sur la suppression des régions réseau existantes, voir [Suppression de régions réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).

<div>

## <a name="to-create-a-network-region"></a>Pour créer une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur **Nouveau**.

5.  Tapez une valeur dans le champ **Nom** de la page **Nouvelle région**. Cette valeur doit être unique dans votre déploiement de Microsoft Lync Server 2013.

6.  Dans la liste déroulante **Site central**, sélectionnez le site central pour cette région réseau.

7.  La case à cocher **Activer un autre chemin d’accès à l’audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

8.  La case à cocher **Activer un autre chemin d’accès à la vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région, car son nom seul ne suffit pas à la décrire.

10. Cliquez sur **Valider**.

Le tableau **Sites associés** n’est pas utilisé pour la création d’une région réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, reportez-vous à la rubrique [création ou modification de sites réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

</div>

<div>

## <a name="to-modify-a-network-region"></a>Pour modifier une région réseau

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la région**, vous pouvez modifier les paramètres permettant d’activer et de désactiver les chemins audio et vidéo alternatifs et modifier également la description (pour plus d’informations, voir la section « Pour créer une région réseau » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à titre de référence pour vous informer des sites qui seront affectés par la modification des paramètres de région.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression des régions réseau existantes dans Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
[Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  


[New-applet csnetworkregion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-applet csnetworkregion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-applet csnetworkregion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-applet csnetworkregion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

