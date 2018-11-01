---
title: 'Lync Server 2013 : Documents de connectivité RTC'
TOCTitle: Documents de connectivité RTC
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398504(v=OCS.15)
ms:contentKeyID: 49297524
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Documents de connectivité RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. De leur point de vue, un appel entre l’infrastructure Voix Entreprise et le réseau téléphonique commuté doit ressembler à toute autre session SIP.

Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).

## Jonction SIP

Une alternative à l’utilisation des passerelles RTC consiste à connecter votre solution Voix Entreprise au RTC à l’aide d’une jonction SIP. La jonction SIP autorise les scénarios suivants :

  - Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.

  - Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing \[DID\]) associé à cet utilisateur.

L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.

## Passerelles RTC

Les passerelles RTC sont des périphériques tiers qui traduisent la signalisation et le trafic multimédia entre l’infrastructure Voix Entreprise et un système RTC ou PBX. Les passerelles RTC fonctionnent avec le serveur de médiation pour présenter un appel RTC ou PBX à un client Voix Entreprise. Le serveur de médiation présente également des appels de clients Voix Entreprise à la passerelle RTC pour le routage vers le système RTC ou PBX. Pour obtenir la liste des partenaires collaborant avec Microsoft pour fournir des périphériques fonctionnant avec Lync Server, reportez-vous au site web des partenaires des communications unifiées de Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).

## Autocommutateurs privés (PBX, Private branch exchange)

Si vous disposez d’une infrastructure vocale existante qui utilise un PBX, vous pouvez utiliser ce dernier avec Lync Server Voix Entreprise.

Les scénarios d’intégration Voix Entreprise-PBX pris en charge sont les suivants :

  - IP-PBX qui prend en charge la déviation du trafic multimédia, avec un serveur de médiation.

  - IP-PBX qui requiert une passerelle RTC autonome.

  - PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.

> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé plusieurs passerelles RTC et systèmes SBC en collaboration avec des partenaires agréés et a réalisé plusieurs tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions répertoriés dans « Infrastructure qualifiée pour Microsoft Lync » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</a>.

Pour plus d’informations sur les partenaires fournissant des solutions Voix Entreprise, consultez le site web des partenaires des communications unifiées de Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).

Pour plus d’informations sur les partenaires fournissant des solutions matérielles Voix Entreprise, dont des passerelles RTC, consultez le site web des partenaires des communications unifiées de Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).

