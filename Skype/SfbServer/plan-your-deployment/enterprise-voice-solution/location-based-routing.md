---
title: Planifier le routage par emplacement dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planification du routage par emplacement dans Skype pour Business Server Enterprise Voice, y compris l’interaction avec sonnerie simultanée et la délégation et les scénarios pris en charge pour le routage basé sur l’emplacement.
ms.openlocfilehash: c1b9730161e7814ba26e167a2b6b4ee79bd40a9e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924226"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planifier le routage par emplacement dans Skype pour les entreprises

Planification du routage par emplacement dans Skype pour Business Server Enterprise Voice, y compris l’interaction avec sonnerie simultanée et la délégation et les scénarios pris en charge pour le routage basé sur l’emplacement.

Routage basé sur l’emplacement rend possible de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC basées sur l’emplacement des parties de l’appel. Routage basé sur l’emplacement est une fonctionnalité de gestion des appels qui contrôle la façon dont les appels sont routés par Skype pour Business Server. Il applique les règles de l’autorisation d’appel sur si les appels peuvent être acheminés vers les points de terminaison PBX ou PSTN en fonction de la Skype pour l’emplacement géographique de l’appelant de l’entreprise.

Le routage géodépendant introduit de nouvelles règles modifiant le routage des appels RTC nationaux et internationaux pour empêcher le contournement des frais de réseau téléphonique commuté. Il offre la flexibilité nécessaire pour appliquer ces règles à certaines régions, passerelles ou groupes d’utilisateurs uniquement.

Les scénarios suivants illustrent les principaux types de routage basé sur l’emplacement permettre appliquer des restrictions :

- Les appels sortants - routage basé sur l’emplacement peut appliquer les appels sortants vers la sortie vers une passerelle PSTN qui se trouve dans la même région dans lequel l’appelant est d’empêcher toute PSTN payant contournement de média, ce qui empêche les appels vers la sortie vers une passerelle PSTN située dans une région différente que l’appelant.

- Appels entrants - routage basé sur l’emplacement peut empêcher les appels PSTN entrants pour faire sonner Skype pour systèmes d’extrémité Business si la passerelle PSTN acheminer l’appel entrant n’est pas située dans la même région en tant que l’appelé Skype pour l’utilisateur d’entreprise.

- Régions inconnues - routage basé sur l’emplacement se limite aux appels PSTN entrants et sortants vers et depuis les utilisateurs qui sont trouvent aux emplacements indéterminées (c'est-à-dire les utilisateurs distants se connectent depuis Internet ou situées dans des régions inconnues).

- Régions internationales - routage basé sur l’emplacement impose de routage des appels par le biais des passerelles PSTN internationales sortants si une passerelle locale de l’utilisateur est introuvable.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Conseils pour appliquer le routage basé sur l’emplacement où

Emplacement de routage en fonction de la situation peut être appliqué à l’emplacement de site de l’utilisateur du point de terminaison réseau ou à l’emplacement de sites de réseau de la passerelle PSTN. Cette rubrique fournit des conseils sur la fonction de routage est appliqué.

### <a name="applying-location-based-routing-at-the-users-location"></a>Application de routage emplacement à l’emplacement de l’utilisateur

Fonction routage exploite les mêmes régions réseau, sites et sous-réseaux définis dans Skype pour Business Server utilisé par le système E9-1-1, CAC et le contournement de média pour appliquer des restrictions de routage d’appel pour empêcher les appels PSTN de contournement. Emplacement de l’utilisateur est déterminé par le sous-réseau IP de Skype l’utilisateur pour point de terminaison Business est connectés depuis. Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur. Routage basé sur l’emplacement est appliqué selon les sites de réseau de l’utilisateur.

En fonction des règles de routage sont appliquées à un par chaque site de réseau, ce qui signifie qu’un ensemble de règles donné s’appliqueront à tous les systèmes d’extrémité activés pour le routage basé sur l’emplacement qui se trouvent dans le même site réseau. Les administrateurs peuvent appliquer le routage basé sur l’emplacement aux sites du réseau qui en ont besoin.

Voix stratégies de routage peuvent être définis sur un par chaque site de réseau pour définir une passerelle PSTN spécifique qui doit être utilisée par tous les utilisateurs situés sur le site réseau à appeler des numéros de téléphone PSTN. Ces stratégies de routage voix sont prioritaires définis par la stratégie de voix de l’utilisateur lorsque l’utilisateur se trouve dans un site réseau activé pour le routage basé sur l’emplacement, et elle empêche le routage des appels via les passerelles PSTN qui sont activés pour le routage Routage basé sur l’emplacement Lorsqu’un Skype pour l’utilisateur passe un appel RTC, stratégie de voix de l’utilisateur détermine si l’utilisateur peut être autorisé à effectuer l’appel. Si la stratégie de voix de l’utilisateur permet à l’utilisateur émettre l’appel, routage basé sur l’emplacement détermine quelle passerelle PSTN l’appel doit sortie à partir de. Routage basé sur un emplacement pour ce faire basée sur l’emplacement de l’utilisateur.

L’emplacement d’un utilisateur peut être classé comme suit :

- L’utilisateur se trouve dans un site réseau connus activé pour le routage basé sur l’emplacement et son numéro de l’arrivée (SDA Direct) s’arrête sur une passerelle PSTN placée dans le même site réseau (c'est-à-dire office). Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

- L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.

- Lorsqu’un utilisateur se trouve dans un site réseau qui n’est pas connu le Skype pour le déploiement de serveur d’entreprise, le routage des appels sortants est basé sur la stratégie de voix attribuée à l’utilisateur pour les passerelles PSTN non lié à des restrictions de routage basé sur l’emplacement. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Application de routage emplacement à l’emplacement de la passerelle PSTN

Les appels acheminés par le biais des passerelles PSTN et PBX peut nécessiter des restrictions de routage basé sur l’emplacement en fonction de l’emplacement de ces systèmes. Routage basé sur l’emplacement peut être activé au niveau de granularité par trunk.

Routage basé sur l’emplacement présente l’ensemble des règles lorsqu’il est activé sur une jonction suivants :

- Lorsque routage basé sur l’emplacement est activée sur par trunk, les règles définissent sur cette jonction sera appliquée uniquement aux appels acheminés via ce tronçon.

- Pour empêcher PSTN frais contournement appels origine à partir d’un site réseau autre que le site de réseau où se trouve la passerelle PSTN, en fonction de routage présente l’association d’un site réseau à une jonction donné. Cela permet de définir le site réseau qui permet l’acheminement des appels vers une jonction donnée.

Jonctions peuvent être activées pour le routage d’en fonction de deux manières :

- La jonction est définie pour une passerelle RTC qui fait sortir les appels vers le réseau téléphonique commuté (RTC). Les appels entrants pris en charge par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.

- La jonction est définie pour un homologue du serveur de médiation qui ne sortie les appels vers les utilisateurs PSTN et services avec les téléphones hérités dans un emplacement statique (c'est-à-dire les téléphones PBX). Pour cette configuration particulière, tous les appels entrants acheminés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction. Appels des utilisateurs PBX aura la même application routage basé sur l’emplacement en tant que Skype pour les utilisateurs professionnels qui se trouvent dans le même site réseau en tant que la jonction. Si deux systèmes PBX situés dans les sites de réseau distincts connectés par le biais de Skype pour Business Server, routage basé sur l’emplacement permettra de routage à partir d’un point de terminaison PBX dans un site réseau à un autre point de terminaison PBX dans les autres sites du réseau. Ce scénario n’est pas bloqué par le routage basé sur l’emplacement. En plus de ce scénario et de la même façon en tant qu’un Skype pour l’utilisateur d’entreprise au même emplacement, points de terminaison connectés à un homologue du serveur de médiation avec cette configuration seront en mesure d’émettre ou recevoir des appels vers et depuis autre homologue du serveur de médiation qui n’opèrent aucun routage d’appels t o RTC (c'est-à-dire un point de terminaison connecté à un système PBX différents) quel que soit le site réseau auquel est associé l’homologue du serveur de médiation. Tous les appels entrants, les appels sortants, transfert d’appel et appel transfère des points de terminaison RTC seront soumis à l’emplacement en fonction de routage à utiliser uniquement les passerelles PSTN qui sont définis en tant que local à ce homologue du serveur de médiation.

## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Le routage géodépendant applique les règles générales suivantes lors du routage des appels dans les scénarios suivants.

### <a name="outgoing-calls"></a>Appels sortants

Le routage des appels sortants d’utilisateurs activés pour le routage basé sur l’emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant illustre comment gÉodÉpendante routage a une incidence sur le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

**Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)**

||**Point de terminaison d’un utilisateur situé dans un site réseau pour lequel le routage géodépendant est activé**|**Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé**|
|:-----|:-----|:-----|
|Autorisation des appels sortants  <br/> |Appel est autorisé en fonction de la stratégie de voix de l’utilisateur  <br/> |Appel est autorisé en fonction de la stratégie de voix de l’utilisateur  <br/> |
|Routage de l’appel sortant  <br/> |L’appel est acheminé en fonction de la stratégie de routage voix du site réseau  <br/> |L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement par le biais de jonctions ne pas activées pour le routage basé sur l’emplacement (si disponible)  <br/> |

### <a name="incoming-calls"></a>Appels entrants

Le routage des appels entrants vers les utilisateurs activés pour le routage basé sur l’emplacement dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté de la manière suivante. Si l’utilisateur a un appel entrant vers un point de terminaison situé dans un routage basé sur l’emplacement activé site réseau et le point de terminaison se trouve dans le même site de réseau que la passerelle PSTN, l’appel est acheminé. Si l’utilisateur a un appel entrant vers un point de terminaison situé dans un routage basé sur l’emplacement activé site réseau et le point de terminaison se trouve dans un site autre réseau que la passerelle PSTN, l’appel n’est pas acheminé. Lorsqu’un utilisateur n’a aucun point de terminaison situé dans le même site de réseau que la passerelle PSTN dont provient l’appel entrant, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel manqué sera envoyée à l’appelé.

Le transfert des paramètres d’un utilisateur est activé pour le routage basé sur l’emplacement d’appel continuera à être appliquée, cependant, les appels soient transférés sont soumises aux restrictions de routage basé sur l’emplacement de l’utilisateur.

Le tableau suivant illustre comment gÉodÉpendante routage a une incidence sur le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelé. Le site de réseau de la passerelle PSTN est activé pour le routage basé sur l’emplacement, et uniquement le routage basé sur l’emplacement permet le routage des appels PSTN aux points de terminaison dans le même site réseau.

**Appelé recevant un appel entrant à partir de la passerelle RTC**

||**Point de terminaison de l’appelé situé dans le même site réseau comme passerelle PSTN**|**Point de terminaison de l’appelé que se trouvent ne pas dans le même site réseau comme passerelle PSTN**|**Point de terminaison de l’appelé situé dans un site réseau inconnu ou non activés pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Routage de l’appel RTC entrant  <br/> |Appel entrant est acheminé vers les points de terminaison de l’appelé  <br/> |Appel entrant n’est pas routé aux points de terminaison de l’appelé  <br/> |Appel entrant n’est pas routé aux points de terminaison de l’appelé  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferts et renvois d’appels

Lorsqu’un point de terminaison RTC est impliqué, en fonction de routage analyse l’emplacement du point de terminaison de l’AV et le point de terminaison où l’appel sera transféré ou transféré à (c'est-à-dire transfert/transférer cible). Routage basé sur l’emplacement détermine si l’appel doit être transféré ou transféré selon l’emplacement de deux points de terminaison.

Le tableau suivant illustre le scénario d’un Skype pour l’utilisateur d’entreprise dans un appel avec un point de terminaison RTC et le Skype pour utilisateur professionnel transfère l’appel vers un autre Skype pour l’utilisateur d’entreprise. Selon l’emplacement du site réseau du point de terminaison du cessionnaire, routage basé sur l’emplacement affecte le routage du transfert d’appel ou transférer.

**Lancement du transfert ou du renvoi d’appel**

|**Utilisateur à l’origine du transfert/renvoi d’appel**|**Point de terminaison cible dans le même site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel**|**Point de terminaison cible dans un autre site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel**|**Point de terminaison cible est dans site réseau inconnue ou réseau pas activé pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Skype pour utilisateur professionnel  <br/> |Le transfert ou renvoi de l’appel est autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |

Par exemple : une Skype pour l’utilisateur d’entreprise dans un appel avec un point de terminaison RTC transfère l’appel vers un autre Skype pour l’utilisateur d’entreprise qui se trouve dans le même site réseau. Dans ce cas, le transfert de l’appel est autorisé.

Le tableau suivant illustre le scénario d’un Skype pour l’utilisateur d’entreprise dans un appel avec une autre Skype pour l’utilisateur d’entreprise et un des utilisateurs transfère l’appel vers un point de terminaison RTC. Selon l’emplacement de l’utilisateur, que l’appel est transféré vers les détails de la table comment routage basé sur l’emplacement affecte l’appel.

**Transfert ou renvoi de l’appel vers le point de terminaison RTC**

|**Point de terminaison cible du transfert/renvoi de l’appel**|**Skype pour les utilisateurs professionnels dans le même site réseau**|**Skype pour les utilisateurs professionnels dans les sites de réseau**|**Un ou les deux Skype pour les utilisateurs professionnels dans site réseau inconnue ou réseau non activés pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Transfert d’appel ou transfert autorisé par la stratégie de routage voix site l’utilisateur transféré  <br/> |Transfert d’appel ou transfert autorisé par la stratégie de routage voix site l’utilisateur transféré  <br/> |Transfert d’appel ou transfert autorisé par la stratégie de voix de l’utilisateur transféré uniquement par le biais de jonctions pas activé pour le routage basé sur l’emplacement  <br/> |

Par exemple : une Skype pour l’utilisateur d’entreprise dans un appel avec une autre Skype pour l’utilisateur d’entreprise qui se trouve dans le même site réseau transfère l’appel vers un point de terminaison RTC et le transfert d’appel est autorisé.

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsque la personne appelée a la sonnerie simultanée activée, routage basé sur l’emplacement analyse l’emplacement de l’appelant et les points de terminaison des parties appelées pour déterminer si l’appel doit être acheminé.

Le tableau ci-dessous illustre un utilisateur pour lequel la sonnerie simultanée est configurée. La cible de la sonnerie simultanée est un utilisateur appartenant au même site réseau, à un autre site réseau ou à un site réseau inconnu.

****

|**Appel RTC entrant pour**|**Situé dans le même site réseau que l’appelé**|**Situé dans un autre site réseau que l’appelé**|**Situé dans le site réseau inconnu ou non activés pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Skype pour utilisateur professionnel  <br/> |Sonnerie simultanée autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |

Le tableau suivant illustre un appel à partir d’un Skype pour l’utilisateur professionnel (c'est-à-dire Skype pour l’appelant de l’entreprise) dans le même site réseau, dans un site autre réseau ou d’un site réseau inconnu. L’appelé a un point de terminaison RTC (téléphone portable) configuré comme cible de la sonnerie simultanée. Dans ce scénario, routage basé sur l’emplacement détermine si l’appel doit être acheminé vers la cible de la sonnerie simultanée (autrement dit cellulaire) de l’appelé ou non.

****

|**Cible de la sonnerie simultanée**|**Situé dans le même site réseau que l’appelé**|**Situé dans un autre site réseau que l’appelé**|**Situé dans le site réseau inconnu ou non activés pour le routage basé sur l’emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Sonnerie simultanée autorisée par le biais de stratégie de routage voix site l’appelant  <br/> |Sonnerie simultanée autorisée par le biais de stratégie de routage voix site l’appelant  <br/> |Sonnerie simultanée autorisée par le biais de stratégie de voix de l’appelant à jonctions ne pas activé pour le routage basé sur l’emplacement  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Mise à jour cumulative 4 de Skype Entreprise

Avec la mise à jour cumulative 4 :

- Routage basé sur l’emplacement continuera à être activée via une stratégie de voix, notamment Skype pour les clients mobiles de l’entreprise.

- Le comportement d’appel pour Skype pour les clients mobiles Business dépendra si elles sont activées pour le routage basé sur l’emplacement et la communication client. Cette condition est conçue pour être statique ; toutefois dans certains cas, une action peut être nécessaire pour associer un client mobile Skype Entreprise à une passerelle PSTN et autoriser certains comportements, tels qu’une escalade.

- Quel que soit votre système d’exploitation, votre client mobile Skype Entreprise doit disposer de la même fonction.

Le tableau suivant vous indique quelques scénarios post-mise à jour cumulative 4 :

|**Utilisateur de routage basée sur un emplacement**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype pour Business Mobile reçoit un appel RTC.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype pour Business Mobile effectue un appel RTC sortant.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype pour Business Mobile transmet ensuite l’appel vers un autre utilisateur ou contact.  <br/> |L’appel est acheminé via VoIP s’il s’agit d’un utilisateur ou contact local par rapport à la partie passerelle PSTN.  <br/> S’il s’agit d’un utilisateur ou contact distant par rapport à la partie passerelle PSTN, l’appel est acheminé via la fonctionnalité Appel via le bureau.  <br/> Si l’utilisateur cible n’est pas joignable via PSTN, l’appel échouera.  <br/> Si le contact cible est un standard automatique des conférences (CAA), l’appel sera bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour client d’entreprise ou un utilisateur fédéré  <br/> |Un Skype pour Business Mobile lance un appel vocal à un autre Skype pour client d’entreprise ou un utilisateur fédéré.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour client d’entreprise ou un utilisateur fédéré  <br/> | Un Skype pour client d’entreprise ou un utilisateur fédéré lance un appel vocal à un Skype pour utilisateur Business Mobile Location-Based de routage. <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Skype pour client d’entreprise ou un utilisateur fédéré  <br/> |Un Skype pour client d’entreprise ou un utilisateur fédéré est sur un appel VoIP une Skype pour utilisateur Mobile de l’entreprise. Chaque partie est transmise à un Skype supplémentaire pour un utilisateur fédéré ou de l’entreprise.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel vocal à un Skype pour le routage Business Mobile Location-Based utilisateur ; un Skype pour la partie Business Mobile transmet à un utilisateur PSTN.  <br/> |L’appel est bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel VoIP une Skype pour le routage Business Mobile Location-Based utilisateur ; chaque partie est transmise à un contact CAA.  <br/> |L’appel escaladé est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur un appel VoIP une Skype pour utilisateur Business Mobile Location-Based le routage et l’utilisateur fédéré est transmise à un utilisateur PSTN.  <br/> |L’escalade sera autorisé ou non en fonction de la gamme en fonction de l’utilisateur fédéré. Aucune action ne prend pas la Skype pour l’application de routage Business Mobile Location-Based utilisateur.  <br/> |

### <a name="delegation"></a>Délégation

Les fonctionnalités de délégation dans Skype pour les entreprises sont affectées par le routage en fonction de la manière suivante :

- Lorsqu’un délégué activé pour les emplacements de routage basé sur l’emplacement un appel de la part d’un responsable, la stratégie de voix du délégué est utilisée pour autoriser l’appel et voix de site du délégué stratégie de routage sera utilisé pour acheminer l’appel

- Pour les appels RTC passés à un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée sont utilisées, comme décrit dans les rubriques « Transfert et renvoi des appels » et « Sonnerie simultanée ».

- Lorsqu’un délégué définit un point de terminaison RTC comme cible de la sonnerie simultanée, pour un appel entrant vers le responsable, la stratégie de routage voix du site qui est associé à la jonction entrante sera utilisée pour acheminer l’appel au point de terminaison du délégué PSTN.

- Pour la délégation, il est recommandé que le responsable et ses délégués associés se trouve généralement dans le même site réseau.

## <a name="other-planning-considerations"></a>Autres considérations de planification

Lorsque vous planifiez le routage basé sur l’emplacement, vous devez envisager l’impact sur les scénarios suivants.

### <a name="disaster-recovery"></a>Récupération d’urgence

Pendant un basculement du pool principal vers un pool de sauvegarde que lors de la restauration des opérations normales vers le pool principal, routage basé sur l’emplacement reste appliquée à toutes les heures pendant une procédure d’urgence et de récupération.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Configuration de routage basée sur l’emplacement a un impact sur la planification d’où vous déployez les passerelles associées à votre serveur Survivable Branch Appliances. La passerelle associée à votre SBA doit se trouver dans le même site de réseau que votre Survivable Branch Appliance ; dans le cas contraire, les utilisateurs hébergés sur votre serveur Survivable Branch Appliance ne sera pas autorisé à passer des appels sortants si routage basé sur l’emplacement est configuré. Lorsque la connexion WAN entre votre Survivable Branch Appliance et le site central est interrompue, les restrictions de routage basé sur l’emplacement reste appliqué.

## <a name="client-and-server-support-for-location-based-routing"></a>Prise en charge des clients et des serveurs pour le routage géodépendant

Routage basé sur l’emplacement est appliqué par Skype pour Business Server. Skype pour Business Server permettre identifier les sites de réseau dans lequel les utilisateurs sont connectent à partir du réseau d’entreprise. Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.

### <a name="server-support"></a>Prise en charge du serveur

Routage basé sur l’emplacement nécessite que Skype pour Business Server ou de Lync Server 2013 CU1 est déployée sur tous les pools frontaux et les serveurs Standard Edition Server dans une topologie donnée. Si ces versions du serveur ne sont pas installées, les restrictions de routage basé sur l’emplacement ne peut pas être appliquées entièrement.

Le tableau suivant indique les combinaisons de versions et les rôles de serveur pris en charge pour le routage basé sur l’emplacement.

****

|**Version du pool**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Skype pour la mise à jour Cumulative Business Server ou de Lync Server 2013 de février 2013  <br/> |Skype pour la mise à jour Cumulative Business Server ou de Lync Server 2013 de février 2013  <br/> |Oui  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Lync Server 2013 de février 2013  <br/> |Lync Server 2013  <br/> |Non  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Lync Server 2013 de février 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Skype pour la mise à jour Cumulative Business Server ou de Lync Server 2013 de février 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Lync Server 2013  <br/> |Quelconque  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Quelconque  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Quelconque  <br/> |Non  <br/> |

### <a name="client-support"></a>Prise en charge des clients

Le tableau suivant identifie les clients qui prend en charge le routage basé sur l’emplacement.

****

|**Type de client**|**Prise en charge**|**Détails**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> ||
|Lync 2013  <br/> |Oui  <br/> ||
|Lync 2010  <br/> |Oui  <br/> ||
|Office Communicator 2007 R2  <br/> |Non  <br/> ||
|Lync Phone Edition  <br/> |Oui  <br/> ||
|Lync Attendant  <br/> |Oui  <br/> ||
|Lync pour Windows 8  <br/> |Non  <br/> ||
|Lync Mobile 2013  <br/> |Non  <br/> |VoIP doit être désactivée pour les clients Lync Mobile 2013 si utilisé par les utilisateurs avec extension de routage basée sur l’emplacement.  <br/> |
|Lync Mobile 2010  <br/> |Oui  <br/> ||

> [!NOTE]
> Pour désactiver VoIP pour Skype pour les clients d’entreprise, attribuer une stratégie de mobilité avec le paramètre IP Audio/vidéo, désactivé pour tous les utilisateurs activés pour le routage basé sur l’emplacement. Pour plus d’informations sur la stratégie de mobilité, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Routage basé sur l’emplacement ne s’applique pas aux types d’interactions suivants. Routage basé sur l’emplacement n’est pas appliqué lorsque Skype pour systèmes d’extrémité Business interagir avec les systèmes d’extrémité PSTN à l’aide de ces fonctionnalités.

- Appels RTC entrants pour les conférences

- Appels RTC entrants et sortants via le groupe de réponse

- Parcage d’appel ou récupération des appels via le parcage d’appels

- Appels RTC entrants pour le service d’annonce

- Appels RTC entrants récupérés via la prise d’appel de groupe

Pour appliquer les règles de routage basé sur un emplacement pour les types d’interactions dans la liste suivante, vous devez activer le routage basé sur l’emplacement de la conférence :

- Appels RTC sortants à partir des conférences

- Escalades à partir de conversations audio d’P2P vers des conférences impliquant des points de terminaison RTC

- Transferts consultatifs impliquant les points de terminaison RTC

Pour activer le routage basé sur l’emplacement de la conférence, consultez [basée sur l’emplacement de routage pour la conférence](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


