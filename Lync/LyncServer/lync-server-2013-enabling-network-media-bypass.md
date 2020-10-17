---
title: 'Lync Server 2013 : activation de la déviation du trafic multimédia réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528521"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Activation de la déviation du trafic multimédia réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les paramètres de contournement de média s’appliquent globalement à un déploiement de Microsoft Lync Server 2013. La déviation du trafic multimédia autorise les appels à contourner le serveur de médiation. Pour plus d’informations sur l’utilisation de la déviation du trafic multimédia, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section Planning.

Vous pouvez activer et configurer le contournement de média à partir du panneau de configuration Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer la déviation du trafic multimédia

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Sur la page **modifier les paramètres globaux** , activez la case à cocher **activer le contournement de média** .

7.  Sélectionnez l’une des options suivantes :
    
      - **Toujours ignorer**     Sélectionnez cette option pour essayer la déviation du trafic multimédia sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé. Si CAC n’est pas activé, sélectionnez cette option dans les situations suivantes :
        
          - Il n’est pas nécessaire de contrôler la bande passante.
        
          - Il n’est pas nécessaire d’utiliser une configuration affinée pour déterminer à quel moment la déviation doit se produire.
        
          - Il existe une connectivité complète entre les passerelles et les clients.
    
      - **Utiliser la configuration**     des sites et des régions Si le contrôle d’admission des accès est activé, cette option est sélectionnée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, les sites de configuration réseau et les régions seront utilisés pour déterminer quand la déviation du trafic multimédia est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés. Activez la case à cocher **activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs grands sites associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central important) et que vous disposez également de sites de succursale associés à la même région qui ont des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer la case à cocher **activer le contournement pour les sites non mappés** si le contrôle d’admission des tâches est activé.

8.  Cliquez sur **OK ** pour enregistrer vos modifications.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactivation de la déviation du trafic multimédia réseau dans Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Options globales de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

