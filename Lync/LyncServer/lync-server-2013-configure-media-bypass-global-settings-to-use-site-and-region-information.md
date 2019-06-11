---
title: Configuration des paramètres généraux de déviation du trafic multimédia pour utiliser les informations de site et de région
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

<div>


> [!NOTE]
> Cette rubrique part du principe que vous avez déjà configuré le contournement multimédia pour toutes les connexions de Trunk du serveur de médiation à un homologue (une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un contrôleur de bordure de session (SBC) sur un service de téléphonie sur Internet. Fournisseur (ITSP) pour un site ou un service spécifique pour lequel vous souhaitez que le média ignore le serveur de médiation.<BR>Cette rubrique part du principe que vous avez défini tous les sites centraux et les sites de succursale dans le générateur de topologie de telle sorte qu’ils correspondent à la région du réseau, au site réseau et à la configuration de sous-réseau que vous avez exécutées conformément aux étapes de la rubrique <A href="lync-server-2013-create-or-modify-a-network-region.md">créer ou modifier une région réseau dans Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">créez ou modifiez un site réseau dans lync Server 2013</A>, puis <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associez un sous-réseau à un site réseau dans Lync Server 2013</A>. S’il ne correspond pas, l’action de contournement du support n’aboutira pas.



</div>

Outre l’activation de l’exclusion de médias pour les connexions de Trunk individuelles associées à un homologue, vous devez également configurer des paramètres globaux. Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour la dérivation de médias, il est supposé que l’une ou les deux situations suivantes affectent votre configuration:

  - Vous *ne disposez pas* de la bonne connectivité entre les points de terminaison Lync Server et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.

  - Le contrôle d’admission des appels (CAC) pour la gestion de la bande passante est activé.
    
    <div>
    

    > [!NOTE]
    > Pour plus d’informations sur les considérations relatives aux contrôles d’admission des appels et au contournement du contenu multimédia, voir la section «contrôle d’admission des appels de connexions RTC» dans le <A href="lync-server-2013-media-bypass-and-mediation-server.md">serveur de contournement de média et le serveur de médiation de Lync server 2013</A> dans la documentation de planification.

    
    </div>

Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de déviation du trafic multimédia lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure ci-dessous pour modifier les informations relatives aux sites et aux régions destinées à la déviation du trafic multimédia. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres de déviation du trafic multimédia.

Vous pouvez aussi suivre ces étapes si vous voulez utiliser les informations sur les sites et les régions pour faire la décision d’ignorer, mais n’avez pas l’intention d’activer le contrôle d’admission des appels. Dans d’autres cas, les liens limités en bande passante doivent toujours être représentés par le biais de stratégies d’intersite réseau, comme décrit dans la rubrique [créer des stratégies de réseau intersite dans Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). Les contraintes de bande passante réelles ne sont pas aussi importantes dans ce cas, car le contrôle d’admission des appels n’a pas été activé. Ces liens servent à partitionner les sous-réseaux pour spécifier ceux qui n’ont pas de limites de bande passante et qui peuvent donc utiliser une dérivation multimédia. Notez que cela est également vrai lorsque le contrôle d’admission des appels et l’exclusion de médias sont activés.

Par ailleurs, en cas de contournement, il est nécessaire de garantir une cohérence entre un site défini dans le générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau. Par exemple, si vous disposez d’un site de succursale que vous avez défini dans le générateur de topologie comme ayant uniquement une passerelle RTC déployée, ce site de succursale doit être configuré avec une stratégie vocale d’entreprise permettant aux utilisateurs du site de succursale d’avoir leurs appels RTC via le RTC. passerelle sur le site de la succursale.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Pour configurer les informations relatives aux sites et aux régions pour la déviation du trafic multimédia

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Double-cliquez sur la configuration **Globale** dans le tableau.

4.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.

5.  Cliquez sur **Utiliser la configuration des sites et des régions**.

6.  Si nécessaire, activez la case à cocher **Activer la déviation pour les sites non mappés**.
    
    <div>
    

    > [!NOTE]
    > N’activez cette case à cocher que si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez la déviation du trafic pour les sites non mappés, la configuration est rationalisée. Vous ne spécifiez que les sous-réseaux associés aux sites de succursale au lieu d’avoir à spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.

    
    </div>

7.  Cliquez sur **Valider**.

Ensuite, ajoutez des sous-réseaux au site réseau, comme décrit dans la section [associer des sous-réseaux avec les sites réseau pour le contournement de médias dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Les procédures réelles pour l’Association de sous-réseaux avec les sites réseau sont décrites dans [la section associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Après avoir associé tous les sous-réseaux aux sites réseau, le déploiement par dérivation de média est terminé.

<div>


> [!IMPORTANT]
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour poursuivre le déploiement de la déviation du trafic multimédia. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-create-or-modify-a-network-region.md">création ou modification d’une région réseau dans Lync server 2013</A> et <A href="lync-server-2013-create-or-modify-a-network-site.md">création ou modification d’un site réseau dans Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Associez des sous-réseaux aux sites réseau pour une dérivation multimédia dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

