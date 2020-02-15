---
title: Configurer les paramètres globaux de déviation du trafic multimédia pour utiliser les informations de site et de région
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configurer les paramètres globaux de déviation du trafic multimédia dans Lync Server 2013 pour utiliser les informations de site et de région

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

<div>


> [!NOTE]
> Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des connexions de jonction depuis le serveur de médiation vers un homologue (une passerelle PSTN, un PBX IP ou un contrôleur SBC d’un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le contournement de média contourne toujours le serveur de médiation.<BR>Cette rubrique suppose également que vous avez défini tous les sites centraux et les sites de succursale dans le générateur de topologie de manière à ce qu’il corresponde à la région réseau, au site réseau et à la configuration de sous-réseau que vous avez effectués conformément aux étapes décrites dans <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or Modify a Network site in lync 2013 Server</A> <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">2013</A> Si ce n’est pas le cas, le contournement de média échouera.



</div>

En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux. Si vous suivez la procédure indiquée dans cette rubrique pour configurer les paramètres globaux pour le contournement de média, les situations suivantes peuvent avoir un impact sur la configuration :

  - Vous *n’avez pas* une connectivité correcte entre les points de terminaison Lync Server et les homologues pour lesquels vous avez configuré le contournement de média sur la connexion de jonction.

  - Le contrôle d’admission des appels pour la gestion de la bande passante est activé.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les considérations relatives au contrôle d’admission des appels et à la déviation du trafic multimédia, reportez-vous à la section « contrôle d’admission des appels des connexions PSTN » dans la documentation de planification du <A href="lync-server-2013-media-bypass-and-mediation-server.md">contournement de média et du 2013 serveur de médiation</A> .

    
    </div>

Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de contournement de média lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure suivante pour modifier les informations relatives aux sites et aux régions destinées au contournement de média. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres du contournement de média.

Ou bien suivez ces étapes si vous souhaitez utiliser les informations relatives aux sites et aux régions pour appliquer le contournement de média sans activer le contrôle d’admission des appels. Dans ce cas, les liens limités de bande passante devront toujours être représentés par des stratégies intersite réseau, comme décrit dans [Create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). Les contraintes réelles de bande passante ne sont pas aussi importantes dans ce cas, car le contrôle d’admission des appels n’a pas été activé. Ces liaisons servent alors à partitionner les sous-réseaux afin de déterminer ceux qui n’ont aucune limite de bande passante et qui peuvent par conséquent avoir recours au contournement de média. Notez que cela est également vrai lorsque le contrôle d’admission des appels et le contournement de média sont tous les deux activés.

Par ailleurs, pour que le contournement fonctionne correctement, il doit exister une cohérence entre un site défini dans le générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau. Par exemple, si vous disposez d’un site de succursale que vous avez défini dans le générateur de topologie comme n’ayant qu’une passerelle PSTN déployée, ce site de succursale doit être configuré avec une stratégie de voix entreprise qui permet aux utilisateurs de site de succursale d’acheminer leurs appels PSTN via le réseau téléphonique commuté (RTC). passerelle sur le site de succursale.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Pour configurer les informations relatives aux sites et aux régions pour le contournement de média

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Double-cliquez sur la configuration **Globale** dans le tableau.

4.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.

5.  Cliquez sur **Utiliser la configuration des sites et des régions**.

6.  Si nécessaire, activez la case à cocher **Activer le contournement pour les sites non mappés**.
    
    <div>
    

    > [!NOTE]
    > Activez uniquement cette case à cocher si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée. Vous devez uniquement spécifier les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.

    
    </div>

7.  Cliquez sur **Valider**.

Ensuite, ajoutez des sous-réseaux au site réseau, comme décrit dans [associer des sous-réseaux à des sites réseau pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Les procédures réelles pour l’Association de sous-réseaux à des sites réseau sont décrites dans [associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)). Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement du contournement de média est terminé.

<div>


> [!IMPORTANT]
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour pouvoir poursuivre le déploiement du contournement de média. Pour plus d’informations, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync server 2013</A> et <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or Modify a Network site in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Associer des sous-réseaux à des sites réseau pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

