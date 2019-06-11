---
title: 'Lync Server 2013: composants de connectivité PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Composants de connectivité PSTN dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-04_

Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. Du point de vue de l’utilisateur, un appel entre l’infrastructure voix entreprise et le RTC devrait paraître une seule et même session SIP.

Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).

<div>

## <a name="sip-trunking"></a>Jonction SIP

À la place des passerelles RTC, vous pouvez connecter votre solution vocale d’entreprise au RTC en utilisant le trunking SIP. La jonction SIP autorise les scénarios suivants :

  - Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.

  - Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.

L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Passerelles RTC

Les passerelles RTC sont des appareils tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure voix entreprise et un réseau PBX ou PSTN. Les passerelles RTC fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client voix entreprise. Le serveur de médiation présente également des appels de clients voix entreprise vers la passerelle RTC pour le routage vers le RTC ou le PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils compatibles avec Lync Server, voir le site Web Microsoft Unified [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)communications Partners à l’adresse.

</div>

<div>

## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

Si vous disposez d’une infrastructure vocale existante qui utilise un système PBX (Private Branch Exchange), vous pouvez utiliser votre système PBX avec Lync Server Enterprise Voice.

Les scénarios d’intégration PBX voix entreprise pris en charge sont les suivants:

  - IP-PBX prenant en charge la dérivation multimédia, avec un serveur de médiation.

  - IP-PBX qui requiert une passerelle RTC autonome.

  - PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.

<div>


> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Pour plus d’informations sur les partenaires proposant des solutions voix entreprise, consultez le site Web Microsoft [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Unified Communications Partners à l’adresse.

Pour plus d’informations sur les partenaires qui proposent des solutions matérielles voix entreprise, notamment les passerelles RTC, consultez [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)le site Web Microsoft Unified Communications Partners.

</div>

</div>

<span> </span>

</div>

</div>

</div>

