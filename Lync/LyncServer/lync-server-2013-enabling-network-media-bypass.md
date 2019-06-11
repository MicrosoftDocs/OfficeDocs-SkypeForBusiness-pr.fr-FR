---
title: 'Lync Server 2013: activation du contournement de média réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a>Activation du contournement de média réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Les paramètres de contournement de média s’appliquent globalement dans le déploiement de Microsoft Lync Server 2013. Bypass Media accepte les appels pour ignorer le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement du contenu multimédia, voir [planification d’une dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section planification.

Vous pouvez activer et configurer le contournement multimédia à partir du panneau de configuration de Lync Server.

<div>

## <a name="to-enable-and-configure-media-bypass"></a>Pour activer et configurer le contournement multimédia

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **Global**.

4.  Dans la page **Global** , cliquez sur configuration **globale** . Il n’y a toujours qu’une seule configuration et elle est toujours nommée global.

5.  Dans le menu **édition** , cliquez sur **afficher les détails**.

6.  Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contournement du contenu multimédia** .

7.  Sélectionnez l’une des options suivantes:
    
      - **Toujours ignorer**   sélectionnez cette option pour essayer la dérivation multimédia sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels (CAC) est activé. Si le CAC n’est pas activé, sélectionnez cette option dans les situations suivantes:
        
          - Le contrôle de la bande passante n’est pas nécessaire.
        
          - Il n’est pas nécessaire de disposer d’une configuration précise pour déterminer le moment où un contournement se produit.
        
          - Il existe une connectivité complète entre les passerelles et les clients.
    
      - **Utiliser la configuration**   des sites et des régions si le CAC est activé, cette option est activée par défaut et ne peut pas être modifiée. Lorsque cette option est sélectionnée, les sites et les régions de configuration réseau sont utilisés pour déterminer à quel moment une dérivation de média est possible. Si vous sélectionnez cette option, vous pouvez choisir d’activer le contournement pour les sites qui ne sont pas mappés. Activez la case à cocher **activer le contournement pour les sites non mappés** uniquement si vous avez un ou plusieurs sites de grande taille associés à la même région qui n’ont pas de contraintes de bande passante (par exemple, un site central de grande taille) et si des sites de succursales sont également associés au même région qui comporte des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est simplifiée, car vous spécifiez uniquement les sous-réseaux associés aux sites de succursale plutôt que d’indiquer tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer la case à cocher **activer le contournement pour les sites non mappés** si le CAC est activé.

8.  Cliquez sur **valider** pour enregistrer vos modifications.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactivation de la contournement de média réseau dans Lync Server 2013](lync-server-2013-disabling-network-media-bypass.md)  


[Options de contournement global de médias dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

