---
title: Planifier le routage basé sur l’emplacement dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planification du routage basé sur l’emplacement dans Skype Entreprise Server Voix Entreprise, y compris l’interaction avec la sonnerie et la délégation simultanées, et scénarios pris en charge pour le routage géolocal.
ms.openlocfilehash: aada1db39d4dacbd5a6ec7f5dec1ede08468c50e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855331"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planifier le routage basé sur l’emplacement dans Skype Entreprise

Planification du routage basé sur l’emplacement dans Skype Entreprise Server Voix Entreprise, y compris l’interaction avec la sonnerie et la délégation simultanées, et scénarios pris en charge pour le routage géolocal.

Location-Based routage permet de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison PSTN en fonction de l’emplacement des parties dans l’appel. Location-Based routage des appels est une fonctionnalité de gestion des appels qui contrôle la façon dont les appels sont acheminés par Skype Entreprise Server. Il applique des règles d’autorisation d’appel pour déterminer si les appels peuvent être acheminés vers des points de terminaison PBX ou PSTN en fonction de l’emplacement géographique Skype Entreprise’appelant.

Location-Based routage des appels introduit un nouvel ensemble de règles qui modifie le routage des appels PSTN nationaux et internationaux afin d’empêcher le contournement de frais. Location-Based routage fournit la flexibilité nécessaire pour définir l’étendue de ces règles à des régions spécifiques, à des passerelles spécifiques ou à un ensemble spécifique d’utilisateurs uniquement.

Les scénarios suivants illustrent les principaux types de restrictions que Location-Based routage peut appliquer :

- Egress appels : le routage Location-Based peut appliquer des appels sortants vers une passerelle PSTN située dans la même région que l’appelant pour empêcher le contournement de frais RSTN, ce qui empêche les appels de sortir vers une passerelle PSTN située dans une autre région que l’appelant.

- Appels entrants : le routage Location-Based peut empêcher les appels PSTN entrants de sonner les points de terminaison Skype Entreprise si la passerelle PSTN qui a routage l’appel entrant n’est pas située dans la même région que l’utilisateur Skype Entreprise appelé.

- Régions inconnues : Location-Based le routage limite les appels PSTN entrants et sortants vers et depuis des utilisateurs situés dans des emplacements non déterminés (c’est-à-dire, des utilisateurs distants se connectant à partir d’Internet ou situés dans des régions inconnues).

- Régions internationales : Location-Based routage applique le routage des appels sortants via des passerelles PSTN internationales si une passerelle locale vers l’emplacement de l’utilisateur est in trouvée.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Recommandations sur l’application du Location-Based routage

Location-Based routage en fonction de la situation peut être appliqué à l’emplacement du site réseau du point de terminaison de l’utilisateur ou à l’emplacement du site réseau de la passerelle PSTN. Cette rubrique fournit des instructions sur la façon Location-Based routage est appliqué.

### <a name="applying-location-based-routing-at-the-users-location"></a>Application du Location-Based routage à l’emplacement de l’utilisateur

Location-Based routage exploite les mêmes régions réseau, sites et sous-réseaux que définis dans les Skype Entreprise Server utilisés par E9-1-1, cac et le contournement de média pour appliquer des restrictions de routage des appels afin d’empêcher le contournement de frais PSTN. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP du ou des points de terminaison Skype Entreprise’utilisateur sont connectés. Chaque sous-réseau IP est associé à un site réseau, qui est agrégé en régions réseau définies par l’administrateur. Location-Based routage est appliqué en fonction du site réseau de l’utilisateur.

Location-Based règles de routage sont appliquées par site réseau, ce qui signifie qu’un ensemble donné de règles sera appliqué à tous les points de terminaison activés pour le routage Location-Based situés dans le même site réseau. Les administrateurs peuvent appliquer Location-Based routage aux sites réseau qui en ont besoin.

Les stratégies de routage des voix peuvent être définies par site réseau pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés sur le site réseau pour appeler des numéros de téléphone PSTN. Ces stratégies de routage des voix prévalent sur le routage défini par la stratégie de voix de l’utilisateur lorsque l’utilisateur se trouve dans un site réseau activé pour le routage Location-Based et empêche le routage des appels via d’autres passerelles PSTN activées pour le routage Location-Based. Lorsqu’un Skype Entreprise passe un appel PSTN, la stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à prendre l’appel. Si la stratégie de voix de l’utilisateur permet à l’utilisateur de placer l’appel, Location-Based Routage détermine la passerelle PSTN à partir de laquelle l’appel doit être émis. Location-Based routage effectue cette détermination en fonction de l’emplacement de l’utilisateur.

Un emplacement d’utilisateur peut être catégorisé des manières suivantes :

- L’utilisateur se trouve dans un site réseau connu activé pour le routage Location-Based et son numéro DID (Direct Inward Dial) se termine sur une passerelle PSTN placée dans le même site réseau (bureau). Le routage des appels sortants s’fera par le biais de la stratégie de routage des voix du site réseau dans lequel se trouve l’utilisateur. Les appels PSTN entrants à l’utilisateur sont acheminés vers des points de terminaison situés dans le même site réseau que la passerelle PSTN.

- L’utilisateur se trouve dans un site réseau connu différent du site réseau où se trouve la passerelle PSTN. (c’est-à-dire que l’utilisateur s’est rendu dans un autre bureau d’entreprise). Le routage des appels sortants utilise la stratégie de routage des voix du site réseau dans lequel se trouve l’utilisateur. Les appels PSTN entrants à l’utilisateur ne seront pas acheminés vers des points de terminaison situés sur des sites différents de la passerelle PSTN pour empêcher le contournement des frais PSTN.

- Lorsqu’un utilisateur se trouve dans un site réseau inconnu du déploiement Skype Entreprise Server, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur aux passerelles PSTN non liées aux restrictions de routage Location-Based. Les appels PSTN entrants ne seront pas acheminés vers les points de terminaison situés dans des sites réseau inconnus afin d’empêcher le contournement des frais PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Application du Location-Based routage à l’emplacement de la passerelle PSTN

Les appels acheminés via des passerelles PSTN et des PBX peuvent nécessiter Location-Based restrictions de routage en fonction de l’emplacement de ces systèmes. Location-Based routage peut être activé au niveau de granularité par branche.

Location-Based routage introduit l’ensemble de règles suivant lorsqu’il est activé sur une trunk :

- Lorsque Location-Based routage est activé par branche, les règles définies sur cette liaison ne sont appliquées qu’aux appels acheminés via cette liaison.

- Pour empêcher le contournement des frais de réseau téléphonique public (PSTN) lorsque les appels proviennent d’un site réseau différent du site réseau où se trouve la passerelle PSTN, le routage Location-Based introduit l’association d’un site réseau à une acheminement donnée. Cela définit le site réseau qui permet d’router les appels vers une liaison donnée.

Les trunks peuvent être activées pour Location-Based routage de deux manières :

- La trunk est définie pour une passerelle PSTN qui appelle le PSTN. Les appels entrants acheminés par une liaison de ce type seront acheminés uniquement vers les points de terminaison situés dans le même site réseau que la liaison.

- La ligne est définie pour un homologue de serveur de médiation qui ne remet pas les appels au réseau téléphonique public public (PSTN) et qui prend en charge les utilisateurs avec des téléphones hérités à des emplacements statiques (c’est-à-dire, des téléphones PBX). Pour cette configuration particulière, tous les appels entrants acheminés par une ligne de ce type sont considérés comme provenant du même site réseau que la liaison. Les appels provenant d’utilisateurs PBX auront la même Location-Based'application du routage Skype Entreprise utilisateurs qui se trouvent dans le même site réseau que la trunk. Si deux systèmes PBX situés dans des sites réseau distincts sont connectés via Skype Entreprise Server, le routage Location-Based autorise le routage d’un point de terminaison PBX d’un site réseau vers un autre point de terminaison PBX dans l’autre site réseau. Ce scénario ne sera pas bloqué par le Location-Based routage. Outre ce scénario et de la même manière qu’un utilisateur Skype Entreprise au même emplacement, les points de terminaison connectés à un homologue de serveur de médiation avec cette configuration pourront effectuer ou recevoir des appels vers et depuis d’autres homologues de serveur de médiation qui n’a routent pas les appels vers le réseau téléphonique public (c’est-à-dire un point de terminaison connecté à un autre PBX) quel que soit le site réseau auquel l’homologue de serveur de médiation est associé. Tous les appels entrants, les appels sortants, les transferts d’appels et les transferts d’appels impliquant des points de terminaison PSTN seront soumis au routage basé sur l’emplacement pour utiliser uniquement les passerelles PSTN définies comme étant locales pour cet homologue de serveur de médiation.

## <a name="scenarios-for-location-based-routing"></a>Scénarios de Location-Based routage

Location-Based routage des appels applique les règles générales suivantes lors du routage des appels dans les scénarios suivants.

### <a name="outgoing-calls"></a>Appels sortants

Le routage des appels sortants des utilisateurs activés pour Location-Based routage est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant illustre l’impact Location-Based routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

**Appelant plaçant un appel sortant vers le PSTN**

|&nbsp;|Point de terminaison utilisateur situé dans un site réseau activé pour le routage Location-Based réseau|Point de terminaison utilisateur situé dans un site réseau inconnu ou non activé pour Location-Based routage|
|:-----|:-----|:-----|
|Autorisation des appels sortants   |L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur   |L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur   |
|Routage de l’appel sortant   |L’appel est routage conformément à la stratégie de routage des voix du site réseau   |L’appel est routage conformément à la stratégie de voix de l’utilisateur et uniquement par le biais de Location-Based routage (si disponible)   |

### <a name="incoming-calls"></a>Appels entrants

Le routage des appels entrants vers les utilisateurs activés pour Location-Based routage dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté de la manière suivante. Si un utilisateur a un appel entrant vers un point de terminaison situé dans un site réseau activé pour le routage Location-Based et que le point de terminaison se trouve dans le même site réseau que la passerelle PSTN, l’appel est acheminé. Si un utilisateur a un appel entrant vers un point de terminaison situé dans un site réseau activé pour le routage Location-Based et que le point de terminaison se trouve dans un autre site réseau que la passerelle PSTN, l’appel n’est pas routage. Lorsqu’un utilisateur n’a pas de point de terminaison situé dans le même site réseau que la passerelle PSTN d’où provient l’appel entrant, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel en absence est envoyée à l’appelé.

Les paramètres de forwardage d’appel d’un utilisateur activé pour le routage Location-Based continueront d’être appliqués, mais les appels transmis seront soumis aux restrictions de routage Location-Based de l’utilisateur.

Le tableau suivant montre comment Location-Based routage affecte le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelé. Le site réseau de la passerelle PSTN est activé pour le routage Location-Based, et le routage Location-Based permet uniquement le routage des appels PSTN vers les points de terminaison au sein du même site réseau.

**Appelé recevant un appel entrant du PSTN**

|&nbsp;|Point de terminaison de l’appelé situé dans le même site réseau que la passerelle PSTN|Point de terminaison de l’appelé non situé dans le même site réseau que la passerelle PSTN|Point de terminaison de l’appelé situé dans un site réseau inconnu ou non activé pour Location-Based routage|
|:-----|:-----|:-----|:-----|
|Routage des appels PSTN entrants   |L’appel entrant est acheminé vers les points de terminaison de l’appelé   |L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé   |L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelé   |

### <a name="call-transfers-and-call-forwarding"></a>Transferts d’appels et transfert d’appel

Lorsqu’un point de terminaison PSTN est impliqué, le routage Location-Based analyse l’emplacement du point de terminaison de l’appelant et le point de terminaison vers lequel l’appel sera transféré ou transféré (cible de transfert/transfert). Location-Based routage détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison.

Le tableau suivant illustre le scénario d’un utilisateur Skype Entreprise dans un appel avec un point de terminaison PSTN, et l’utilisateur Skype Entreprise transfère l’appel à un autre Skype Entreprise utilisateur. Selon l’emplacement du site réseau du point de terminaison de la personne à l’origine du transfert, Location-Based routage affecte le routage du transfert ou du transfert d’appel.

**Lancer le transfert ou le transfert d’appel**

|Utilisateur à l’origine du transfert/transfert d’appel|Le point de terminaison cible se trouve dans le même site réseau que l’utilisateur qui lance le transfert ou le transfert d’appel|Point de terminaison cible se trouve dans un site réseau différent en tant qu’utilisateur à l’origine du transfert ou du transfert d’appel|Le point de terminaison cible se trouve dans un site réseau inconnu ou un site réseau non activé pour Location-Based routage
|:-----|:-----|:-----|:-----|
|Skype Entreprise utilisateur   |Transfert ou transfert d’appel autorisé   |Transfert ou transfert d’appel non autorisé   |Transfert ou transfert d’appel non autorisé   |

Par exemple : un Skype Entreprise dans un appel avec un point de terminaison PSTN transfère l’appel à un autre utilisateur Skype Entreprise qui se trouve dans le même site réseau. Dans ce cas, le transfert d’appel est autorisé.

Le tableau suivant illustre le scénario d’un utilisateur Skype Entreprise dans un appel avec un autre utilisateur Skype Entreprise, et l’un des utilisateurs transfère l’appel vers un point de terminaison PSTN. Selon l’emplacement de l’utilisateur vers qui l’appel est transféré, le tableau détaille l’impact Location-Based routage sur l’appel.

**Transfert d’appel ou transfert vers le point de terminaison PSTN**

|Cible de point de terminaison transfert/transfert d’appel|Skype Entreprise utilisateurs dans le même site réseau|Skype Entreprise utilisateurs dans différents sites réseau|Un ou les deux Skype Entreprise utilisateurs dans un site réseau inconnu ou un site réseau non activé pour le routage Location-Based réseau|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN   |Transfert ou transfert d’appel autorisé par la stratégie de routage des voix du site de l’utilisateur transféré   |Transfert ou transfert d’appel autorisé par la stratégie de routage des voix du site de l’utilisateur transféré   |Transfert ou transfert d’appel autorisé par la stratégie de voix de l’utilisateur transféré uniquement par le biais de Location-Based routage   |

Par exemple : un utilisateur Skype Entreprise dans un appel avec un autre utilisateur Skype Entreprise qui se trouve sur le même site réseau transfère l’appel vers un point de terminaison PSTN et le transfert d’appel est autorisé.

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsque la sonnerie simultanée est activée pour la partie appelée, le routage Location-Based analyse l’emplacement de l’appelant et les points de terminaison des parties appelées pour déterminer si l’appel doit être acheminé.

Le tableau suivant illustre un utilisateur configuré avec la sonnerie simultanée et la cible de sonnerie simultanée est un utilisateur du même site réseau, d’un autre site réseau ou d’un site réseau inconnu.

****

|Appel PSTN entrant pour|Situé dans le même site réseau que l’appelé|Situé dans un site réseau différent de l’appelé|Situé dans un site réseau inconnu ou non activé pour le routage Location-Based réseau|
|:-----|:-----|:-----|:-----|
|Skype Entreprise utilisateur   |Sonnerie simultanée autorisée   |Sonnerie simultanée non autorisée   |Sonnerie simultanée non autorisée   |

Le tableau suivant illustre un appel d’un utilisateur Skype Entreprise (c’est-à-dire un appelant Skype Entreprise) dans le même site réseau, dans un autre site réseau ou à partir d’un site réseau inconnu. L’appelé dispose d’un point de terminaison PSTN (téléphone portable) configuré en tant que cible de sonnerie simultanée. Dans ce scénario, Location-Based routage détermine si l’appel doit être acheminé vers la cible de sonnerie simultanée (téléphone portable) de l’appelé ou non.

****

|Cible de sonnerie simultanée|Situé dans le même site réseau que l’appelé|Situé dans un site réseau différent de l’appelé|Situé dans un site réseau inconnu ou non activé pour le routage Location-Based réseau|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN   |Sonnerie simultanée autorisée via la stratégie de routage des voix du site de l’appelant   |Sonnerie simultanée autorisée via la stratégie de routage des voix du site de l’appelant   |Sonnerie simultanée autorisée par le biais de la stratégie de voix de l’appelant vers des Location-Based routage   |

### <a name="skype-for-business-cumulative-update-4"></a>Skype Entreprise Mise à jour cumulative 4

Avec la mise à jour cumulative 4, vous verrez les informations suivantes :

- Location-Based routage des messages continuera d’être activé via la stratégie de voix, y compris Skype Entreprise clients mobiles.

- Le comportement d’appel des clients Skype Entreprise Mobile est basé sur le fait qu’ils soient activés pour le routage Location-Based et le client de communication. Ceci est conçu pour être statique, mais il peut y avoir, dans certaines situations, un effort pour associer un client Skype Entreprise Mobile à une passerelle PSTN locale et autoriser certains comportements, tels qu’une escalade

- Quel que soit votre système d’exploitation, votre client Skype Entreprise Mobile doit avoir les mêmes fonctionnalités.

Le tableau suivant vous aidera à parcourir certains scénarios post-mise à jour cumulative 4 :

|Location-Based de routage des données|Autre partie|Action|Résultat|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile   |RTCP   |Skype Entreprise Mobile reçoit un appel PSTN entrant.   |L’appel est acheminé via Appel via le travail (CvW), et non via VoIP.   |
|Skype Entreprise Mobile   |RTCP   |Skype Entreprise Mobile effectue un appel PSTN sortant.   |L’appel est acheminé via CvW, et non via VoIP.   |
|Skype Entreprise Mobile   |RTCP   |Skype Entreprise Mobile est dans un appel PSTN. Skype Entreprise Mobile passe ensuite l’appel à un autre utilisateur ou contact.   |L’appel est acheminé via VoIP si l’utilisateur ou le contact est local sur la partie passerelle PSTN.  <br/> Si l’utilisateur ou le contact est distant de la partie passerelle PSTN, l’appel est acheminé via CvW.  <br/> Si l’utilisateur cible n’est pas accessible via le réseau téléphonique téléphonique public (PSTN), l’appel échoue.  <br/> Si le contact cible est une conférence Standard automatique (CAA), l’appel est bloqué.   |
|Skype Entreprise Mobile   |Skype Entreprise client ou un utilisateur fédéré   |Un Skype Entreprise Mobile lance un appel vocal vers un autre client Skype Entreprise ou un utilisateur fédéré.   |L’appel est effectué via VoIP.   |
|Skype Entreprise Mobile   |Skype Entreprise client ou un utilisateur fédéré   | Un Skype Entreprise ou un utilisateur fédéré lance un appel vocal à un utilisateur Skype Entreprise Mobile Location-Based Routage.  |L’appel est effectué via VoIP.   |
|Skype Entreprise Mobile   |Skype Entreprise client ou un utilisateur fédéré   |Un Skype Entreprise ou un utilisateur fédéré est en appel VoIP à un Skype Entreprise Mobile. L’une ou l’autre des parties passe à un utilisateur Skype Entreprise ou fédéré.   |L’appel est effectué via VoIP.   |
|Skype Entreprise Mobile   |Utilisateur fédéré   |Un utilisateur fédéré est en appel vocal à un utilisateur Skype Entreprise Mobile Location-Based Routage ; une Skype Entreprise mobile passe à un utilisateur PSTN.   |L’appel est bloqué.   |
|Skype Entreprise Mobile   |Utilisateur fédéré   |Un utilisateur fédéré est en appel VoIP vers un utilisateur Skype Entreprise Mobile Location-Based Routage ; l’une ou l’autre des parties fait une escalade vers un contact CAA.   |L’appel escalade est bloqué, avec un message d’erreur approprié.   |
|Skype Entreprise Mobile   |Utilisateur fédéré   |Un utilisateur fédéré est en appel VoIP vers un utilisateur Skype Entreprise Mobile Location-Based Routage, et l’utilisateur fédéré passe à un utilisateur PSTN.   |L’escalade sera autorisée ou non autorisée en fonction du Location-Based routage de l’utilisateur fédéré. L Skype Entreprise’application Location-Based Mobile Location-Based'utilisateur de routage n’agit pas.   |

### <a name="delegation"></a>Délégation

Les fonctionnalités de délégation Skype Entreprise sont affectées par Location-Based routage de la manière suivante :

- Lorsqu’un délégué activé pour le routage Location-Based passe un appel au nom d’un responsable, la stratégie de voix du délégué est utilisée pour autoriser l’appel et la stratégie de routage des communications vocales du site du délégué est utilisée pour router l’appel.

- Pour les appels PSTN entrants à un responsable, les mêmes règles applicables au transfert d’appel ou à la sonnerie simultanée s’appliquent comme décrit dans les rubriques Transferts et transferts d’appels et sonnerie simultanée.

- Lorsqu’un délégué définit un point de terminaison PSTN comme cible de sonnerie simultanée, pour un appel entrant au responsable, la stratégie de routage des communications vocales du site associé à la liaison entrante est utilisée pour router l’appel vers le point de terminaison PSTN du délégué.

- Pour la délégation, il est recommandé que le responsable et ses délégués associés soient généralement situés sur le même site réseau.

## <a name="other-planning-considerations"></a>Autres considérations sur la planification

Lorsque vous planifiez Location-Based routage, vous devez prendre en compte l’impact sur les scénarios suivants.

### <a name="disaster-recovery"></a>Récupération d'urgence

Lors d’un passage du pool principal vers un pool de sauvegarde, ainsi que lors de la restauration d’opérations normales sur le pool principal, le routage Location-Based reste appliqué en permanence pendant une procédure d’urgence et de récupération.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configuration Location-Based routage des appareils a une incidence sur la planification de l’endroit où vous déployez les passerelles associées à vos Survivable Branch Appliances. La passerelle associée à votre SBA doit se trouver dans le même site réseau que votre Survivable Branch Appliance . Dans le cas contraire, les utilisateurs de votre Survivable Branch Appliance ne seront pas autorisés à prendre des appels sortants si Location-Based routage est configuré. Lorsque la connexion WAN entre votre Survivable Branch Appliance et le site central est en panne, Location-Based restrictions de routage reste appliquées.

## <a name="client-and-server-support-for-location-based-routing"></a>Prise en charge du client et du serveur pour Location-Based routage

Location-Based routage est appliqué par les Skype Entreprise Server. Skype Entreprise Server identifier les sites réseau depuis lequel les utilisateurs se connectent au sein du réseau d’entreprise. Étant donné que les utilisateurs distants se trouve en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.

### <a name="server-support"></a>Prise en charge du serveur

Location-Based routage nécessite que Skype Entreprise Server ou Lync Server 2013 CU1 soit déployé sur tous les pools frontux et serveurs Édition Standard dans une topologie donnée. Si ces versions du serveur ne sont pas installées, les restrictions de routage en fonction de l’emplacement ne peuvent pas être entièrement appliquées.

Le tableau suivant identifie la combinaison des rôles serveur et des versions pris en charge pour Location-Based routage.

****

|Version du pool|Version du serveur de médiation|Pris en charge|
|:-----|:-----|:-----|
|Skype Entreprise Server ou la mise à jour cumulative de février 2013 de Lync Server 2013   |Skype Entreprise Server ou la mise à jour cumulative de février 2013 de Lync Server 2013   |oui   |
|Skype Entreprise Server ou la mise à jour cumulative de février 2013 de Lync Server 2013   |Lync Server 2013   |Non   |
|Skype Entreprise Server ou la mise à jour cumulative de février 2013 de Lync Server 2013   |Lync Server 2010   |Non   |
|Skype Entreprise Server ou la mise à jour cumulative de février 2013 de Lync Server 2013   |Office Communications Server 2007 R2   |Non   |
|Lync Server 2013   |indifférent   |Non   |
|Lync Server 2010   |indifférent   |Non   |
|Office Communications Server 2007 R2   |indifférent   |Non   |

### <a name="client-support"></a>Prise en charge du client

Le tableau suivant identifie les clients que le routage Location-Based prend en charge.

****

|Type de client|Pris en charge|Détails|
|:-----|:-----|:-----|
|Skype Entreprise   |oui   ||
|Lync 2013   |oui   ||
|Lync 2010   |oui   ||
|Office Communicator 2007 R2   |Non   ||
|Lync Phone Edition   |oui   ||
|Lync Attendant   |oui   ||
|Lync pour Windows 8   |Non   ||
|Lync Mobile 2013   |Non   |VoIP doit être désactivé pour les clients Lync Mobile 2013 s’il est utilisé par les utilisateurs Location-Based routage activé.   |
|Lync Mobile 2010   |oui   ||

> [!NOTE]
> Pour désactiver voIP pour les clients Skype Entreprise, affectez une stratégie de mobilité avec le paramètre IP Audio/Vidéo, désactivé pour tous les utilisateurs activés pour le routage Location-Based réseau. Pour plus d’informations sur la stratégie de mobilité, voir [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non pris en charge par Location-Based routage

Location-Based routage ne s’applique pas aux types d’interactions suivants. Location-Based routage n’est pas appliqué Skype Entreprise points de terminaison interagissent avec les points de terminaison PSTN à l’aide de ces fonctionnalités.

- Conférences par numérotation PSTN

- Appels PSTN entrants et sortants via Response Group

- Parc d’appel ou récupération d’appels PSTN par le biais du parc d’appel

- Appels PSTN entrants au service d’annonce

- Appels PSTN entrants récupérés via la prise d’appel de groupe

Pour appliquer Location-Based de routage aux types d’interactions de la liste suivante, vous devez activer Location-Based routage pour les conférences :

- Appel sortant PSTN à partir de conférences

- Escalades entre les conversations audio d’égal à égal et les conférences impliquant des points de terminaison PSTN

- Transferts consultatifs impliquant des points de terminaison PSTN

Pour activer Location-Based routage des conférences, voir Routage géoconférence [pour les conférences.](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)