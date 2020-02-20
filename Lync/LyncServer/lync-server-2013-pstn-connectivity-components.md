---
title: 'Lync Server 2013 : composants de connectivité PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08764f432eb90f1b16a0c91ed810d394e94c6193
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Composants de connectivité PSTN dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (PSTN) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. De leur point de vue, un appel entre l’infrastructure Voix Entreprise et le RTC doit ressembler à toute autre session SIP.

Pour les connexions PSTN, vous pouvez déployer une jonction SIP ou une passerelle PSTN (avec un PBX, également appelé lien SIP direct, ou sans PBX).

<div>

## <a name="sip-trunking"></a>Jonction SIP

Une alternative à l’utilisation des passerelles PSTN consiste à connecter votre solution Voix Entreprise au PSTN à l’aide d’une jonction SIP. La jonction SIP autorise les scénarios suivants :

  - Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau PSTN en tant que service du fournisseur de services correspondant.

  - Chaque abonné PSTN peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) associé à cet utilisateur.

L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Passerelles PSTN

Les passerelles PSTN sont des périphériques tiers qui traduisent la signalisation et le trafic multimédia entre l’infrastructure Voix Entreprise et un PSTN ou un PBX. Les passerelles PSTN fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client Voix Entreprise. Le serveur de médiation présente également des appels de clients Voix Entreprise à la passerelle PSTN pour le routage vers le PSTN ou le PBX. Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils qui fonctionnent avec Lync Server, consultez le site Web Microsoft Unified Communications Partners à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).

</div>

<div>

## <a name="private-branch-exchanges"></a>Autocommutateurs privés (PBX, Private branch exchange)

Si vous disposez d’une infrastructure vocale existante qui utilise un autocommutateur privé (PBX, Private Branch Exchange), vous pouvez utiliser votre système PBX avec Lync Server Enterprise Voice.

Les scénarios d’intégration Voix Entreprise-PBX pris en charge sont les suivants :

  - IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.

  - IP-PBX qui requiert une passerelle PSTN autonome.

  - PBX TDM (multiplexage temporel), avec une passerelle PSTN autonome.

<div>


> [!NOTE]  
> Le contournement de média n’interagit pas avec chaque passerelle PSTN, système IP-PBX et contrôleur de session en périphérie (SBC). Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à.



</div>

Pour plus d’informations sur les partenaires qui proposent des solutions voix entreprise, voir le site Web [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)des partenaires de communications unifiées de Microsoft à l’adresse.

Pour plus d’informations sur les partenaires qui proposent des solutions matérielles voix entreprise, y compris les passerelles PSTN, [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)consultez le site Web Microsoft Unified Communications Partners.

</div>

</div>

<span> </span>

</div>

</div>

</div>

