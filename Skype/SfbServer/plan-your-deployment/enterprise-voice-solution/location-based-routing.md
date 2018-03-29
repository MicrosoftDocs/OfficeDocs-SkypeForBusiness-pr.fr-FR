---
title: Planification du routage géodépendant dans Skype Entreprise 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/7/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planification basée sur l’emplacement de routage dans Skype pour Business Server Voix Entreprise, y compris l’interaction avec sonnerie simultanée et la délégation et les scénarios pris en charge pour le routage basé sur l’emplacement.
ms.openlocfilehash: 90bf8605f7708d2e444d64005144c30638e03d4a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-location-based-routing-in-skype-for-business-2015"></a>Planification du routage géodépendant dans Skype Entreprise 2015
 
Planification basée sur l’emplacement de routage dans Skype pour Business Server Voix Entreprise, y compris l’interaction avec sonnerie simultanée et la délégation et les scénarios pris en charge pour le routage basé sur l’emplacement.
  
Fondée sur l’emplacement de routage permet de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison RTPC en fonction de l’emplacement des parties dans l’appel. Routage basé sur l’emplacement est une fonctionnalité de gestion d’appel qui contrôle la façon dont les appels sont routés par Skype pour Business Server. Il applique les règles de l’autorisation d’appel sur si les appels peuvent être acheminés vers des points de terminaison PBX ou PSTN selon le Skype pour l’emplacement géographique de l’appelant de l’entreprise.
  
Le routage géodépendant introduit de nouvelles règles modifiant le routage des appels RTC nationaux et internationaux pour empêcher le contournement des frais de réseau téléphonique commuté. Il offre la flexibilité nécessaire pour appliquer ces règles à certaines régions, passerelles ou groupes d’utilisateurs uniquement.
  
Les scénarios suivants illustrent les principaux types de routage basé sur l’emplacement peut appliquer des restrictions :
  
- Appels de sortie - fondée sur l’emplacement de routage peut appliquer des appels sortants vers la sortie à une passerelle PSTN qui se trouve dans la même région comme étant de l’appelant afin d’éviter le contournement de péage RTPC, qui empêche les appels à la sortie à une passerelle PSTN située dans une région autre que l’appelant.
    
- Les appels entrants - fondée sur l’emplacement de routage peut empêcher les appels RTPC entrants à l’anneau Skype pour les points de terminaison Business si la passerelle RTC routage des appels entrants ne se trouve pas dans la même région que l’appelé Skype pour l’utilisateur professionnel.
    
- Régions inconnues - fondée sur l’emplacement de routage limite les appels de RTPC entrantes et sortantes vers et à partir des utilisateurs qui sont trouvent dans des emplacements indéterminées (c'est-à-dire les utilisateurs distants se connectant à partir d’Internet ou situées dans des régions inconnues).
    
- Régions internationales - routage basé sur l’emplacement applique le routage de sortant des appels à travers les passerelles RTPC internationales si une passerelle locale à l’emplacement de l’utilisateur est introuvable.
    
## <a name="guidance-for-where-to-apply-location-based-routing"></a>Conseils pour le champ d’application de routage basé sur l’emplacement

Fondée sur l’emplacement de routage en fonction de la situation peut être appliqué à l’emplacement du site de l’utilisateur point de terminaison réseau, ou à l’emplacement de site de réseau de la passerelle RTPC. Cette rubrique fournit des instructions sur comment fondée sur l’emplacement de routage sont appliquée.
  
### <a name="applying-location-based-routing-at-the-users-location"></a>Application basée sur l’emplacement de routage à l’emplacement de l’utilisateur

Emplacement de routage par exploite le même réseau des régions, des sites et des sous-réseaux, tel que défini dans Skype pour Business Server utilisé par E9-1-1, CAC et Media Bypass pour appliquer des restrictions de routage d’appel afin d’empêcher le numéro payant de RTPC ignorent. Emplacement de l’utilisateur est déterminé par le sous-réseau IP de Skype l’utilisateur pour entreprise de point de terminaison est connectés à partir de. Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur. Routage basé sur l’emplacement est appliquée en fonction du site de réseau de l’utilisateur.
  
Règles de routage basées sur l’emplacement sont appliquées à un par réseau site par site, c'est-à-dire qu’un ensemble de règles s’appliqueront à tous les points de terminaison activés pour le routage basé sur un emplacement qui se trouvent dans le même site de réseau. Les administrateurs peuvent appliquer le routage basé sur l’emplacement pour les sites de réseau qui en ont besoin.
  
Voix stratégies de routage peuvent être définis sur une base de site de réseau pour définir une passerelle PSTN particulier qui doit être utilisée par tous les utilisateurs situés sur le site de réseau pour appeler les numéros de téléphone PSTN. Ces stratégies de routage voix ont priorité sur la gamme définie par la stratégie de voix de l’utilisateur lorsque l’utilisateur se trouve dans un site réseau activé pour le routage basé sur l’emplacement, et il empêche le routage des appels via d’autres passerelles RTPC qui sont activés pour Fondée sur l’emplacement de routage. Lorsqu’un Skype pour l’utilisateur professionnel place un appel RTC, stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à effectuer l’appel. Si la stratégie de voix de l’utilisateur permet à l’utilisateur de placer l’appel, fondée sur l’emplacement de routage détermine quelle passerelle RTPC l’appel doit sortie des passagers. Routage basé sur l’emplacement de ce faire en fonction de l’emplacement de l’utilisateur.
  
L’emplacement d’un utilisateur peut être classé comme suit :
  
- L’utilisateur se trouve dans un site de réseau connu activé pour le routage basé sur l’emplacement et de son numéro DID (Direct à distance vers l’intérieur) s’arrête sur une passerelle PSTN placée sur le même réseau (par exemple, office). Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.
    
- L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.
    
- Lorsqu’un utilisateur se trouve dans un site de réseau qui n’est pas connu du Skype pour le déploiement du serveur de l’entreprise, le routage des appels sortants se fondera sur la stratégie de voix attribuée à l’utilisateur pour les passerelles RTPC ne pas lié à des restrictions de routage basé sur l’emplacement. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté. 
    
### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Application basée sur l’emplacement de routage à l’emplacement de la passerelle RTC

Les appels acheminés via les passerelles RTPC et PBX peut nécessiter des restrictions de routage basé sur l’emplacement en fonction de l’emplacement de ces systèmes. Fondée sur l’emplacement de routage peut être activé au niveau de granularité par trunk.
  
Routage basé sur l’emplacement présente l’ensemble des règles lorsqu’il est activé sur un tronc suivantes :
  
- Lorsque le routage basé sur l’emplacement est activé sur une base par trunk, les règles définissent sur que trunk s’appliquera uniquement aux appels acheminés via ce trunk.
    
- Pour empêcher le contournement de péages RTPC appels origine à partir d’un site de réseau différent qui le site de réseau où se trouve la passerelle RTC, fondée sur l’emplacement de routage présente l’association d’un site de réseau pour une ligne donnée. Cela permet de définir le site réseau qui permet l’acheminement des appels vers une jonction donnée.
    
PUITS peuvent être activés pour le routage de fondée sur l’emplacement de deux manières :
  
- La jonction est définie pour une passerelle RTC qui fait sortir les appels vers le réseau téléphonique commuté (RTC). Les appels entrants pris en charge par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.
    
- Le tronc est défini pour un homologue de serveur de médiation qui ne "sortie" les appels aux utilisateurs RTPC et services avec les téléphones existants dans un emplacement statique (c'est-à-dire les téléphones PBX). Pour cette configuration particulière, tous les appels entrants acheminés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction. Appels des utilisateurs des PBX auront la même application fondée sur l’emplacement de routage comme Skype pour les utilisateurs professionnels qui se trouvent dans le même site de réseau que le tronc. Si les deux systèmes PBX sont situés dans les sites de réseau distincts sont connectés par le biais de Skype pour Business Server, fondée sur l’emplacement de routage permettra de routage à partir d’un point de terminaison PBX dans un site de réseau à un autre point de terminaison PBX dans les autres sites du réseau. Ce scénario ne sera pas bloqué par le routage basé sur l’emplacement. En plus de ce scénario et de la même façon sous la forme d’un Skype pour l’utilisateur professionnel au même emplacement, points de terminaison connectés à un homologue de serveur de médiation avec cette configuration sera en mesure d’effectuer ou de recevoir des appels vers et à partir de l’autre homologue de serveur de médiation qui n’achemine pas d’appels t o le RTPC (c'est-à-dire un point de terminaison connecté à un autre PBX) quel que soit le site de réseau auquel est associé l’homologue de serveur de médiation. Tous les appels entrants, appels sortants, appellent des transferts et appellent les transferts des points de terminaison RTPC impliquant fera l’objet d’emplacement de routage à utiliser uniquement les passerelles RTPC sont définies en local pour l’homologue de ce serveur de médiation.
    
## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Le routage géodépendant applique les règles générales suivantes lors du routage des appels dans les scénarios suivants.
  
### <a name="outgoing-calls"></a>Appels sortants

Le routage des appels sortants des utilisateurs activés pour le routage basé sur l’emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant illustre comment fondée sur l’emplacement routage a une incidence sur le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant. 
  
**Appelant un appel sortant au RTC**

||**Point de terminaison utilisateur situé dans un site réseau activé pour le routage basé sur l’emplacement**|**Point de terminaison utilisateur situé dans un site de réseau inconnu ou pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|
|Autorisation des appels sortants  <br/> |Appel est autorisé en fonction de la stratégie de voix de l’utilisateur  <br/> |Appel est autorisé en fonction de la stratégie de voix de l’utilisateur  <br/> |
|Routage de l’appel sortant  <br/> |Appel est routé en fonction de la stratégie de routage du site réseau vocal  <br/> |L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement par le biais de puits ne pas activés pour le routage basé sur l’emplacement (si disponible)  <br/> |
   
### <a name="incoming-calls"></a>Appels entrants

Le routage des appels entrants vers les utilisateurs activés pour le routage basé sur l’emplacement dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté de la manière suivante. Si un utilisateur a un appel entrant vers un point de terminaison que qui se trouve dans un routage basé sur l’emplacement activé de site du réseau et le point de terminaison se trouve dans le même site de réseau que la passerelle RTC, l’appel sera acheminé. Si un utilisateur a un appel entrant vers un point de terminaison que qui se trouve dans un routage basé sur l’emplacement activé de site du réseau et le point de terminaison se trouve dans un site de réseau autre que la passerelle RTC, l’appel n’est pas routé. Lorsqu’un utilisateur n’a aucun point de terminaison que qui se trouve dans le même site de réseau que la passerelle RTC où l’appel entrant provient de, l’appel entrant est routé directement vers la messagerie vocale de l’utilisateur et une notification d’appel manqué sera envoyée à la personne appelée.
  
Le transfert des paramètres d’un utilisateur qui est activé pour le routage basé sur l’emplacement d’appel va continuer à s’appliquer, toutefois, les appels transférés seront soumises à des restrictions de routage basé sur l’emplacement de l’utilisateur.
  
Le tableau suivant illustre comment fondée sur l’emplacement routage a une incidence sur le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelé. Le site de réseau de la passerelle RTC est activé pour le routage basé sur l’emplacement, et uniquement le routage basé sur l’emplacement permet le routage des appels RTPC aux points de terminaison dans le même site de réseau.
  
**Appelé à la réception d’un appel entrant depuis le PSTN**

||**Point de terminaison de l’appelé que qui se trouve dans le même site de réseau en tant que passerelle PSTN**|**Point de terminaison de l’appelé que ne se trouve ne pas dans le même site de réseau en tant que passerelle PSTN**|**Point de terminaison de l’appelé qui se trouve dans un site de réseau inconnu ou pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Routage de l’appel RTC entrant  <br/> |Appel entrant est acheminé vers les points de terminaison de l’appelé  <br/> |Appel entrant n’est pas acheminé vers les points de terminaison de l’appelé  <br/> |Appel entrant n’est pas acheminé vers les points de terminaison de l’appelé  <br/> |
   
### <a name="call-transfers-and-call-forwarding"></a>Transferts et renvois d’appels

Lorsqu’un point de terminaison du réseau RTPC est impliqué, fondée sur l’emplacement de routage analyse l’emplacement du point de terminaison de l’AV et le point de terminaison où l’appel sera transféré ou transmis à (c'est-à-dire de transfert/transférer cible). Fondée sur l’emplacement de routage détermine si l’appel doit être transféré ou transmis selon l’emplacement de deux points de terminaison.
  
Le tableau suivant illustre le scénario d’un Skype pour l’utilisateur professionnel d’un appel à un point de terminaison du réseau RTPC et le Skype pour l’utilisateur professionnel transfère l’appel à un autre Skype pour l’utilisateur professionnel. En fonction de l’emplacement réseau du site du point de terminaison du cessionnaire, fondée sur l’emplacement de routage affecte le routage du transfert d’appel ou le transférer.
  
**Origine transfert d’appel ou le transfert**

|**Utilisateur à l’origine de l’appel de transfert/transférer**|**Point de terminaison cible se trouve dans le même site de réseau en tant qu’utilisateur qui lance le transfert d’appel ou le transfert**|**Point de terminaison cible est dans un site de réseau en tant qu’utilisateur qui lance le transfert d’appel ou le transfert**|**Point de terminaison cible est dans un site de réseau inconnue ou réseau pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Skype pour l’utilisateur professionnel  <br/> |Le transfert ou renvoi de l’appel est autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |
   
Par exemple : un Skype pour l’utilisateur professionnel d’un appel à un point de terminaison du réseau RTPC transfère l’appel à un autre Skype pour l’utilisateur professionnel qui se trouve dans le même site de réseau. Dans ce cas, le transfert de l’appel est autorisé. 
  
Le tableau suivant illustre le scénario d’un Skype pour les utilisateurs des entreprises dans un appel avec un autre Skype pour l’utilisateur professionnel et un des utilisateurs transfère l’appel à un point de terminaison du réseau RTPC. En fonction de l’emplacement de l’utilisateur, l’appel est en cours de transfert vers les détails de la table comment fondée sur l’emplacement de routage affecte l’appel.
  
**Transfert d’appel ou le transférer vers le point de terminaison RTPC**

|**Appeler la cible de point de terminaison de transfert/transférer**|**Skype pour les utilisateurs professionnels dans le même site de réseau**|**Skype pour les utilisateurs professionnels dans des sites différents**|**Un ou deux Skype pour les utilisateurs dans un site de réseau inconnue ou réseau non activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison RTC  <br/> |Transfert d’appel ou de transfert autorisée par la stratégie de routage voix du site transféré de l’utilisateur  <br/> |Transfert d’appel ou de transfert autorisée par la stratégie de routage voix du site transféré de l’utilisateur  <br/> |Transfert d’appel ou de transfert autorisé par la stratégie de voix de l’utilisateur transférées uniquement par le biais de puits pas activé pour le routage basé sur l’emplacement  <br/> |
   
Par exemple : un Skype pour les utilisateurs des entreprises dans un appel avec un autre Skype pour l’utilisateur professionnel qui se trouve dans le même site réseau transfère l’appel à un point de terminaison du réseau RTPC et le transfert d’appel est autorisé. 
  
### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsque la partie appelée a la sonnerie simultanée activée, fondée sur l’emplacement de routage analyse l’emplacement de la partie appelante et les points de terminaison des parties appelées pour déterminer si l’appel doit être acheminé.
  
Le tableau ci-dessous illustre un utilisateur pour lequel la sonnerie simultanée est configurée. La cible de la sonnerie simultanée est un utilisateur appartenant au même site réseau, à un autre site réseau ou à un site réseau inconnu. 
  
****

|**Appel entrant de RTPC pour**|**Situé dans le même site de réseau que l’appelé**|**Situé dans le site appelé réseau différente**|**Situé dans un site de réseau inconnu ou ne pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Skype pour l’utilisateur professionnel  <br/> |Sonnerie simultanée autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |
   
Le tableau suivant illustre un appel à partir d’un Skype pour l’utilisateur professionnel (c'est-à-dire Skype pour l’appelant de l’entreprise) dans le même site de réseau, dans un autre réseau, ou à partir d’un site réseau inconnue. L’appelé a un point de terminaison RTC (téléphone portable) configuré comme cible de la sonnerie simultanée. Dans ce scénario, fondée sur l’emplacement de routage détermine si l’appel doit être routé vers la cible de sonnerie simultanée (par exemple, téléphone portable) de l’appelé ou non.
  
****

|**Cible de sonnerie simultanée**|**Situé dans le même site de réseau que l’appelé**|**Situé dans le site appelé réseau différente**|**Situé dans un site de réseau inconnu ou ne pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison RTC  <br/> |Autorisé par la stratégie de routage de l’appelant site voix de sonnerie simultanée  <br/> |Autorisé par la stratégie de routage de l’appelant site voix de sonnerie simultanée  <br/> |Sonnerie simultanée autorisé via une stratégie de voix de l’appelant pour puits ne pas activé pour le routage basé sur l’emplacement  <br/> |
   
### <a name="skype-for-business-cumulative-update-4"></a>Mise à jour cumulative 4 de Skype Entreprise

Avec la mise à jour cumulative 4 :
  
- Fondée sur l’emplacement de routage continuera à être activée via une stratégie Voice, notamment Skype pour les clients mobiles de l’entreprise.
    
- Le comportement d’appel pour Skype pour les clients d’entreprise Mobile dépendra si elles sont activées pour le routage basé sur l’emplacement et la communication client. Cette condition est conçue pour être statique ; toutefois dans certains cas, une action peut être nécessaire pour associer un client mobile Skype Entreprise à une passerelle PSTN et autoriser certains comportements, tels qu’une escalade.
    
- Quel que soit votre système d’exploitation, votre client mobile Skype Entreprise doit disposer de la même fonction.
    
Le tableau suivant vous indique quelques scénarios post-mise à jour cumulative 4 :
  
|**Utilisateur de routage basées sur l’emplacement**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype pour entreprise Mobile reçoit un appel RTC.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype pour entreprise Mobile effectue un appel de RTPC sortant.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype pour entreprise Mobile transmet ensuite l’appel à un autre utilisateur ou un contact.  <br/> |L’appel est acheminé via VoIP s’il s’agit d’un utilisateur ou contact local par rapport à la partie passerelle PSTN.  <br/> S’il s’agit d’un utilisateur ou contact distant par rapport à la partie passerelle PSTN, l’appel est acheminé via la fonctionnalité Appel via le bureau.  <br/> Si l’utilisateur cible n’est pas joignable via PSTN, l’appel échouera.  <br/> Si le contact cible est un standard automatique des conférences (CAA), l’appel sera bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour Business ou les utilisateurs fédérés  <br/> |Un Skype pour Mobile d’entreprise lance un appel vocal à un autre Skype pour client d’entreprise ou un utilisateur de fédéré.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour Business ou les utilisateurs fédérés  <br/> | Un Skype pour Business ou fédéré utilisateur lance un appel vocal à un Skype pour le routage de Business Mobile Location-Based un utilisateur. <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour Business ou les utilisateurs fédérés  <br/> |Un Skype pour client d’entreprise ou un utilisateur de fédéré est sur un appel VoIP un Skype pour utilisateur Mobile de l’entreprise. Chaque partie transmet à un Skype supplémentaire pour les utilisateur fédérés ou d’entreprise.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel vocal à un Skype pour l’utilisateur Business Mobile Location-Based le routage ; un Skype pour la partie d’entreprise Mobile transmet un utilisateur PSTN.  <br/> |L’appel est bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel VoIP un Skype pour l’utilisateur Business Mobile Location-Based le routage ; chaque partie transmet à un contact TCHA.  <br/> |L’appel escaladé est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel VoIP un Skype pour utilisateur de routage de Business Mobile Location-Based, et l’utilisateur fédéré transfère un utilisateur PSTN.  <br/> |La remontée est autorisée ou non selon le routage basé sur l’emplacement de l’utilisateur fédéré. Le Skype pour l’application de l’utilisateur Business Mobile Location-Based le routage ne prend aucune action.  <br/> |
   
### <a name="delegation"></a>Délégation

Les fonctionnalités de délégation dans Skype pour l’entreprise sont affectées par le routage basé sur l’emplacement de la manière suivante :
  
- Lorsqu’un délégué activé, les emplacements de routage basé sur l’emplacement, un appel au nom d’un gestionnaire, stratégie de voix du délégué est utilisée pour autoriser l’appel et les voix de site du délégué stratégie de routage sera utilisé pour acheminer l’appel
    
- Pour les appels RTC passés à un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée sont utilisées, comme décrit dans les rubriques « Transfert et renvoi des appels » et « Sonnerie simultanée ».
    
- Lorsqu’un délégué définit un point de terminaison du réseau RTPC comme cible de sonnerie simultanée, pour un appel entrant vers le Gestionnaire de la stratégie de routage voix du site qui est associé à un trunk entrant servira à acheminer l’appel vers le point de terminaison du délégué RTPC.
    
- Pour la délégation, il est recommandé que le gestionnaire et ses délégués associés se trouve généralement dans le même site de réseau.
    
## <a name="other-planning-considerations"></a>Autres considérations de planification

Lorsque vous planifiez un routage basé sur l’emplacement, vous devez étudier l’impact pour les scénarios suivants.
  
### <a name="disaster-recovery"></a>Récupération d’urgence

Lors d’un basculement à partir du pool principal vers un pool de sauvegarde ainsi que lors de la restauration des opérations normales dans le pool principal, fondée sur l’emplacement de routage reste appliquée à tous les fois lors d’une procédure de reprise après sinistre et de récupération.
  
### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Routage basé sur l’emplacement de configuration a une incidence sur la planification d’où vous déployez la passerelle associée à votre programme Survivable Branch Appliances. La passerelle associée à votre SBA doit se trouver dans le même site de réseau que votre Survivable Branch Appliance ; dans le cas contraire, les utilisateurs hébergés sur votre Survivable Branch Appliance n’autorise pas d’effectuer des appels sortants si fondée sur l’emplacement de routage est configuré. Lors de la connexion de réseau étendu entre vos Survivable Branch Appliance et le site central est en panne, les restrictions de routage basé sur l’emplacement reste appliquée.
  
## <a name="client-and-server-support-for-location-based-routing"></a>Prise en charge des clients et des serveurs pour le routage géodépendant

Routage basé sur l’emplacement est appliquée par Skype pour Business Server. Skype pour Business Server permet d’identifier les sites de réseau où les utilisateurs sont connectent à partir du réseau d’entreprise. Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.
  
### <a name="server-support"></a>Prise en charge du serveur

Routage basé sur l’emplacement nécessite que Skype pour Business Server ou le CU1 de Lync Server 2013 est déployé sur tous les pools du Front-End et les serveurs Standard Edition Server dans une topologie donnée. Si ces versions du serveur ne sont pas installées, restrictions de routage basé sur l’emplacement ne peut pas être entièrement appliquées.
  
Le tableau suivant répertorie la combinaison des rôles de serveur et des versions pris en charge pour le routage basé sur l’emplacement.
  
****

|**Version de pool**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Skype pour la mise à jour Cumulative Business Server ou de Microsoft Lync Server 2013 février 2013  <br/> |Skype pour la mise à jour Cumulative Business Server ou de Microsoft Lync Server 2013 février 2013  <br/> |Oui  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Microsoft Lync Server 2013 février 2013  <br/> |Lync Server 2013  <br/> |Non  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Microsoft Lync Server 2013 février 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Microsoft Lync Server 2013 février 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Lync Server 2013  <br/> |Quelconque  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Quelconque  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Quelconque  <br/> |Non  <br/> |
   
### <a name="client-support"></a>Prise en charge des clients

Le tableau suivant identifie les clients prenant en charge le routage basé sur l’emplacement.
  
****

|**Type de client**|**Prise en charge**|**Détails**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> ||
|Lync 2013  <br/> |Oui  <br/> ||
|Lync 2010  <br/> |Oui  <br/> ||
|Office Communicator 2007 R2  <br/> |Non  <br/> ||
|Lync Phone Edition  <br/> |Oui  <br/> ||
|Lync Attendant  <br/> |Oui  <br/> ||
|Lync pour Windows 8  <br/> |Non  <br/> ||
|Lync Mobile 2013  <br/> |Non  <br/> |VoIP doit être désactivé pour les clients Lync Mobile 2013 si utilisé par les utilisateurs avec un routage basé sur l’emplacement activé.  <br/> |
|Lync Mobile 2010  <br/> |Oui  <br/> ||
   
> [!NOTE]
> Pour désactiver la VoIP pour Skype pour les clients de l’entreprise, affecter une stratégie de mobilité avec le paramètre IP Audio/vidéo désactivé pour tous les utilisateurs activés pour le routage basé sur l’emplacement. Pour plus d’informations sur la stratégie de mobilité, consultez [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps). 
  
## <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Routage basé sur l’emplacement ne s’applique pas aux types suivants d’interactions. Routage basé sur l’emplacement n’est pas appliquée lorsque Skype pour les points de terminaison Business interagir avec les points de terminaison TLS à l’aide de ces fonctionnalités.
  
- Appels RTC entrants pour les conférences
    
- Appels RTC entrants et sortants via le groupe de réponse
    
- Parcage d’appel ou récupération des appels via le parcage d’appels
    
- Appels RTC entrants pour le service d’annonce
    
- Appels RTC entrants récupérés via la prise d’appel de groupe
    
Pour appliquer des règles de routage basé sur l’emplacement pour les types d’interactions dans la liste ci-dessous, vous devez activer le routage basé sur l’emplacement pour la conférence :
  
- Appels RTC sortants à partir des conférences
    
- Escalades à partir de conversations audio d’P2P vers des conférences impliquant des points de terminaison RTC 
    
- Transferts consultatifs impliquant les points de terminaison RTC
    
Pour activer le routage basé sur l’emplacement pour la conférence, consultez [fondée sur l’emplacement de routage pour la conférence](http://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).
  

