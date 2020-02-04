---
title: 'Lync Server 2013 : options de contournement global de médias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Options de contournement global de médias dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

<div>


> [!NOTE]  
> Cette rubrique part du principe que vous avez déjà configuré une dérivation multimédia pour des Trunks vers un homologue (une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un contrôleur de bordure de session (SBC) sur un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour vous voulez que le média ignore le serveur de médiation.



</div>

Outre l’activation de la déviation du trafic multimédia pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres généraux de déviation du trafic multimédia. Les paramètres généraux de déviation du trafic multimédia peuvent spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC ou de l’employer en utilisant le mappage des sous-réseaux vers les sites et les régions réseau, ce qui est similaire à ce que fait le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque la déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés, les informations relatives aux régions, aux sites et aux sous-réseaux qui sont spécifiées pour le contrôle d’admission des appels sont utilisées automatiquement pour déterminer si la déviation du trafic multimédia doit être employée. Cela signifie que vous ne pouvez pas spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC lorsque le contrôle d’admission des appels est activé.

Cette rubrique décrit l’utilisation conjointe du panneau de configuration de Lync Server et de Lync Server Management Shell pour configurer les paramètres globaux de contournement de médias.

<div>


> [!NOTE]  
> Pour configurer la déviation du trafic multimédia en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle RTC, un PBX IP ou un contrôleur SBC d’un fournisseur de jonction SIP [Session Initiation Protocol]) doit être de bonne qualité. Si des restrictions de bande passante sont appliquées sur la liaison, la déviation du trafic multimédia ne peut pas être appliquée aux appels. La déviation du trafic multimédia ne va pas interagir avec chaque passerelle RTC, chaque système IP-PBX et chaque contrôleur SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Étapes suivantes : sélectionner les paramètres globaux de contournement du média

Une fois que vous avez activé la contournement multimédia sur une connexion de Trunk à un homologue pour des sites ou services spécifiques, utilisez le contenu suivant :

  - Activez toujours la dérivation multimédia, comme décrit dans la rubrique [configurer la contournement multimédia dans Lync Server 2013 pour ignorer toujours le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Vous pouvez aussi configurer la contournement multimédia pour utiliser les informations sur les sites et les régions, comme décrit dans [configurer les paramètres globaux de contournement du contenu multimédia dans Lync Server 2013 pour utiliser les informations relatives au site et à la région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

