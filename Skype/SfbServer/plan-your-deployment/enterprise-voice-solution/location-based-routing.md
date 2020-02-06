---
title: Planifier le routage sur la base de l’emplacement dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planifiez le routage sur la base de l’emplacement dans Skype entreprise Server Voice, y compris les interactions avec la sonnerie et la délégation simultanées, et les scénarios pris en charge pour le routage sur site.
ms.openlocfilehash: fae78dcbc1aa1d92d6fe192618d9fda5001436a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802904"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planifier le routage sur la base de l’emplacement dans Skype entreprise

Planifiez le routage sur la base de l’emplacement dans Skype entreprise Server Voice, y compris les interactions avec la sonnerie et la délégation simultanées, et les scénarios pris en charge pour le routage sur site.

Le routage basé sur l’emplacement permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties de l’appel. Le routage basé sur l’emplacement est une fonctionnalité de gestion des appels qui contrôle le mode de routage des appels par Skype entreprise Server. Il applique des règles d’autorisation des appels si les appels peuvent être routés vers des points de terminaison PBX ou PSTN en fonction de l’emplacement géographique de l’appelant Skype entreprise.

Le routage géodépendant introduit de nouvelles règles modifiant le routage des appels RTC nationaux et internationaux pour empêcher le contournement des frais de réseau téléphonique commuté. Il offre la flexibilité nécessaire pour appliquer ces règles à certaines régions, passerelles ou groupes d’utilisateurs uniquement.

Les scénarios suivants illustrent les principaux types de routage de restrictions qui peuvent garantir :

- Appels sortants-le routage de géolocalisation peut imposer les appels sortants vers une passerelle RTC qui se trouve dans la même région que celle de l’appelant, qui empêche les appels entrants vers une passerelle RTC située dans une région différente de celle de l’appelant.

- Appels entrants : le routage géolocalisation peut empêcher les appels RTC entrants de sonner sur les points de terminaison Skype entreprise si la passerelle RTC qui achemine l’appel entrant ne se trouve pas dans la même région que l’utilisateur Skype entreprise appelé.

- Régions inconnues : le routage géolocalisation limite les appels RTC entrants et sortants vers et depuis les utilisateurs qui se trouvent dans des endroits indéterminés (c’est-à-dire, des utilisateurs distants qui se connectent à partir d’Internet ou qui se trouvent dans des régions inconnues).

- Régions internationales : le routage de géolocalisation applique le routage des appels sortants par le biais des passerelles RTC internationales s’il n’y a aucune passerelle locale à l’emplacement de l’utilisateur.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Recommandations sur l’emplacement d’application du routage sur site

Le routage basé sur géolocalisation en fonction de la situation peut être appliqué à l’emplacement du site du réseau de points de terminaison de l’utilisateur ou à l’emplacement du site réseau de la passerelle PSTN. Cette rubrique fournit des recommandations sur l’application du routage basé sur l’emplacement.

### <a name="applying-location-based-routing-at-the-users-location"></a>Application du routage par emplacement à l’emplacement de l’utilisateur

Le routage basé sur l’emplacement tire parti des mêmes régions, sites et sous-réseaux tels qu’ils sont définis dans Skype entreprise Server utilisés par E9-1-1, CAC et Media bypass pour appliquer les restrictions de routage des appels pour éviter le contournement du numéro RTC. L’emplacement d’un utilisateur est déterminé par le sous-réseau IP du point de terminaison Skype entreprise de l’utilisateur qui est connecté. Chaque sous-réseau IP est associé à un site réseau, regroupé au sein de régions réseau définies par l’administrateur. Le routage basé sur l’emplacement est appliqué en fonction du site réseau de l’utilisateur.

Les règles de routage basées sur le niveau de géolocalisation sont appliquées au niveau de chaque site du réseau, ce qui signifie qu’un ensemble de règles donné sera appliqué à tous les points de terminaison activés pour le routage par emplacement situés au sein du même site réseau. Les administrateurs peuvent appliquer le routage sur site aux sites réseau qui en ont besoin.

Il est possible de définir les stratégies de routage vocal sur une base de site réseau par site pour définir une passerelle PSTN particulière qui doit être utilisée par tous les utilisateurs situés dans le site réseau pour appeler des numéros de téléphone PSTN. Ces stratégies de routage de la voix prévaudront sur le routage défini par la stratégie vocale de l’utilisateur lorsque celui-ci se trouve dans un site réseau activé pour le routage de l’emplacement et qu’il empêche le routage des appels via d’autres passerelles RTC activées pour Routage basé sur l’emplacement. Lorsqu’un utilisateur de Skype entreprise place un appel RTC, la politique vocale de l’utilisateur détermine si l’utilisateur peut être autorisé à effectuer l’appel. Si la stratégie vocale de l’utilisateur permet à l’utilisateur de passer l’appel, le routage basé sur l’emplacement détermine la passerelle RTC à partir de laquelle l’appel doit être effectué. Le routage basé sur l’emplacement effectue cette détermination en fonction de l’emplacement de l’utilisateur.

L’emplacement d’un utilisateur peut être classé comme suit :

- L’utilisateur se trouve dans un site réseau connu activé pour le routage géolocalisation et il se termine par un numéro sur une passerelle RTC placée sur le même site (par exemple, Office). Le routage des appels sortants est effectué via la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur sont acheminés vers les points de terminaison situés dans le même site réseau que la passerelle RTC.

- L’utilisateur est situé dans un site réseau connu différent du site réseau dans lequel la passerelle RTC est située (l’utilisateur a été déplacé vers une autre agence). Le routage des appels sortants utilise la stratégie de routage des communications vocales du site réseau dans lequel l’utilisateur est situé. Les appels RTC entrants destinés à l’utilisateur ne sont pas acheminés vers les points de terminaison situés dans d’autres sites que la passerelle RTC pour empêcher le contournement des frais de réseau téléphonique commuté.

- Lorsqu’un utilisateur se trouve sur un site réseau qui n’est pas connu du déploiement de Skype entreprise Server, le routage des appels sortants sera basé sur la politique vocale attribuée à l’utilisateur sur les passerelles RTC qui ne sont pas liées aux restrictions de routage basées sur l’emplacement. Les appels RTC entrants ne sont pas acheminés vers les points de terminaison situés dans des sites réseau inconnus pour empêcher le contournement des frais de réseau téléphonique commuté.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Application du routage géolocalisation sur l’emplacement de la passerelle RTC

Les appels routés via des passerelles RTC et des PBX peuvent nécessiter des limitations de routage basées sur l’emplacement selon l’emplacement de ces systèmes. Le routage basé sur l’emplacement peut être activé en fonction du niveau de granularité par Trunk.

Le routage basé sur l’emplacement présente l’ensemble de règles suivant lorsqu’il est activé sur un Trunk :

- Lorsque le routage basé sur l’emplacement est activé sur une base par Trunk, les règles définies sur ce Trunk s’appliquent uniquement aux appels routés via ce Trunk.

- Pour éviter les péages RTC dans lesquels les appels proviennent d’un site réseau différent du site du réseau sur lequel se trouve la passerelle RTC, le routage de géolocalisation présente l’Association d’un site réseau à un Trunk donné. Cela permet de définir le site réseau qui permet l’acheminement des appels vers une jonction donnée.

Les types de Trunk peuvent être activés pour le routage selon l’emplacement de deux manières :

- La jonction est définie pour une passerelle RTC qui fait sortir les appels vers le réseau téléphonique commuté (RTC). Les appels entrants pris en charge par une jonction de ce type sont acheminés uniquement vers les points de terminaison situés au sein du même site réseau que la jonction.

- Le Trunk est défini pour un homologue de serveur de médiation qui ne sort pas les appels vers les utilisateurs RTC et services avec des téléphones hérités dans des emplacements statiques (tels que les téléphones PBX). Pour cette configuration particulière, tous les appels entrants acheminés par une jonction de ce type sont considérés comme provenant du même site réseau que la jonction. Les appels des utilisateurs PBX pourront utiliser la même application de routage basée sur l’emplacement que les utilisateurs Skype entreprise situés sur le même site réseau que le Trunk. Si deux systèmes PBX situés dans des sites de réseau séparés sont connectés via Skype entreprise Server, le routage géolocalisation permettra le routage d’un point de terminaison PBX dans un site réseau à un autre point de terminaison PBX dans l’autre site réseau. Ce scénario ne sera pas bloqué par le routage sur site. En plus de ce scénario et de la même manière que pour un utilisateur Skype entreprise dans le même emplacement, les points de terminaison connectés à un homologue de serveur de médiation doté de cette configuration sont en mesure de passer ou de recevoir des appels vers et à partir d’autres homologues du serveur de médiation qui ne routent pas les appels t o le RTC (c’est-à-dire un point de terminaison connecté à un autre système PBX), quel que soit le site du réseau auquel l’homologue du serveur de médiation est associé. Tous les appels entrants, les appels sortants, les transferts d’appel et les transferts d’appel impliquant des points de terminaison RTC sont soumis à un routage basé sur l’emplacement pour utiliser uniquement les passerelles RTC définies comme étant locales pour ce serveur de médiation.

## <a name="scenarios-for-location-based-routing"></a>Scénarios de routage géodépendant

Le routage géodépendant applique les règles générales suivantes lors du routage des appels dans les scénarios suivants.

### <a name="outgoing-calls"></a>Appels sortants

Le routage des appels sortants d’utilisateurs activés pour le routage par emplacement est affecté par l’emplacement réseau du point de terminaison de l’utilisateur. Le tableau suivant illustre la façon dont le routage en fonction de l’emplacement affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.

**Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)**

||**Point de terminaison d’un utilisateur situé dans un site réseau pour lequel le routage géodépendant est activé**|**Point de terminaison de l’utilisateur situé dans un site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé**|
|:-----|:-----|:-----|
|Autorisation des appels sortants  <br/> |L’appel est autorisé selon la politique vocale de l’utilisateur.  <br/> |L’appel est autorisé selon la politique vocale de l’utilisateur.  <br/> |
|Routage de l’appel sortant  <br/> |L’appel est acheminé conformément à la politique de routage de la voix du site du réseau.  <br/> |L’appel est routé conformément à la politique vocale de l’utilisateur et seuls les Trunks ne sont pas activés pour le routage sur site (le cas échéant).  <br/> |

### <a name="incoming-calls"></a>Appels entrants

Le routage des appels entrants vers les utilisateurs activés pour le routage par emplacement dépend de l’emplacement du point de terminaison de l’utilisateur. Le routage des appels entrants est affecté comme suit. Si un utilisateur dispose d’un appel entrant à un point de terminaison situé dans un site réseau de routage de géolocalisation et que le point de terminaison se trouve sur le même site réseau que la passerelle RTC, l’appel est routé. Si un utilisateur dispose d’un appel entrant vers un point de terminaison situé dans un site réseau compatible avec le routage d’emplacement et que le point de terminaison se trouve dans un autre site réseau que la passerelle RTC, l’appel n’est pas acheminé. Lorsqu’un utilisateur n’a pas de points de terminaison situés dans le même site réseau que la passerelle RTC à partir de laquelle l’appel entrant provient, l’appel entrant est acheminé directement vers la messagerie vocale de l’utilisateur et une notification d’appel manqué est envoyée à la personne appelée.

Les paramètres de transfert d’appel d’un utilisateur qui est autorisé à utiliser le routage de géolocalisation continuent d’être appliqués, toutefois, les appels transférés seront soumis à des restrictions de routage basées sur l’emplacement de l’utilisateur.

Le tableau suivant illustre la façon dont le routage en fonction de l’emplacement affecte le routage des appels entrants en fonction de l’emplacement du point de terminaison de l’appelant. Le site réseau de la passerelle RTC est activé pour le routage d’emplacement et le routage basé sur l’emplacement autorise uniquement le routage des appels RTC vers des points de terminaison au sein du même site réseau.

**Appelé recevant un appel entrant à partir de la passerelle RTC**

||**Point de terminaison de l’appelant localisé sur le même site réseau que la passerelle RTC**|**Le point de terminaison de l’appelant n’est pas situé sur le même site réseau que la passerelle RTC**|**Point de terminaison de l’appelant situé sur un site réseau inconnu ou non activé pour le routage par emplacement**|
|:-----|:-----|:-----|:-----|
|Routage de l’appel RTC entrant  <br/> |L’appel entrant est acheminé vers les points de terminaison de l’appelant  <br/> |L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelant  <br/> |L’appel entrant n’est pas acheminé vers les points de terminaison de l’appelant  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferts et renvois d’appels

Lorsqu’un point de terminaison RTC est impliqué, le routage géolocalisation analyse l’emplacement du point de terminaison de 134 et le point de terminaison de transfert ou de transfert de l’appel (c.-à-d. transférer/transférer la cible). Le routage basé sur l’emplacement détermine si l’appel doit être transféré ou transféré en fonction de l’emplacement des deux points de terminaison.

Le tableau suivant illustre le scénario d’un utilisateur Skype entreprise lors d’un appel avec un point de terminaison PSTN et l’utilisateur de Skype entreprise transfère l’appel vers un autre utilisateur Skype entreprise. En fonction de l’emplacement du site du réseau du point de terminaison du destinataire, le routage de l’emplacement affecte le routage du transfert ou du transfert d’appel.

**Lancement du transfert ou du renvoi d’appel**

|**Utilisateur à l’origine du transfert/renvoi d’appel**|**Point de terminaison cible dans le même site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel**|**Point de terminaison cible dans un autre site réseau que l’utilisateur à l’origine du transfert ou du renvoi d’appel**|**Le point de terminaison cible est dans un site réseau inconnu ou un site réseau non activé pour le routage par emplacement**|
|:-----|:-----|:-----|:-----|
|Utilisateur Skype entreprise  <br/> |Le transfert ou renvoi de l’appel est autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |Le transfert ou renvoi de l’appel n’est pas autorisé  <br/> |

Par exemple, un utilisateur Skype entreprise dans un appel avec un point de terminaison PSTN transfère l’appel vers un autre utilisateur Skype entreprise qui se trouve sur le même site réseau. Dans ce cas, le transfert de l’appel est autorisé.

Le tableau suivant illustre le scénario d’un utilisateur Skype entreprise lors d’un appel avec un autre utilisateur Skype entreprise et l’un de ces utilisateurs transfère l’appel vers un point de terminaison RTC. En fonction de l’emplacement de l’utilisateur sur lequel l’appel est transféré, le tableau décrit les détails relatifs à l’appel par le routage selon l’emplacement.

**Transfert ou renvoi de l’appel vers le point de terminaison RTC**

|**Point de terminaison cible du transfert/renvoi de l’appel**|**Utilisateurs Skype entreprise sur le même site réseau**|**Utilisateurs Skype entreprise dans différents sites réseau**|**L’un ou les deux utilisateurs de Skype entreprise sur un site réseau ou un site réseau inconnu non activé pour le routage par emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Transfert d’appel ou transfert autorisé par la stratégie de routage vocale de l’utilisateur transféré  <br/> |Transfert d’appel ou transfert autorisé par la stratégie de routage vocale de l’utilisateur transféré  <br/> |Transfert d’appel ou transfert autorisé par la stratégie vocale de l’utilisateur transféré uniquement via des lignes non activées pour le routage par emplacement  <br/> |

Par exemple, un utilisateur Skype entreprise dans un appel avec un autre utilisateur de Skype entreprise qui se trouve sur le même site réseau transfère l’appel à un point de terminaison PSTN et le transfert d’appel est autorisé.

### <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsque la partie appelée dispose d’une sonnerie simultanée activée, le routage de géolocalisation analyse l’emplacement de la partie de l’appel et les points de terminaison des parties appelées pour déterminer si l’appel doit être routé.

Le tableau ci-dessous illustre un utilisateur pour lequel la sonnerie simultanée est configurée. La cible de la sonnerie simultanée est un utilisateur appartenant au même site réseau, à un autre site réseau ou à un site réseau inconnu.

****

|**Appel RTC entrant pour**|**Situé dans le même site réseau que l’appelé**|**Situé dans un autre site réseau que l’appelé**|**Se trouve sur un site réseau inconnu ou n’est pas activé pour le routage par emplacement**|
|:-----|:-----|:-----|:-----|
|Utilisateur Skype entreprise  <br/> |Sonnerie simultanée autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |Sonnerie simultanée non autorisée  <br/> |

Le tableau suivant illustre un appel d’un utilisateur Skype entreprise (par exemple, appelant Skype entreprise) sur un même site réseau, sur un autre site réseau ou sur un site réseau inconnu. L’appelé a un point de terminaison RTC (téléphone portable) configuré comme cible de la sonnerie simultanée. Dans ce scénario, le routage en fonction de l’emplacement détermine si l’appel doit être acheminé vers la cible de sonnerie simultanée (c.-à-d. téléphone mobile) de l’appelé ou non.

****

|**Cible de la sonnerie simultanée**|**Situé dans le même site réseau que l’appelé**|**Situé dans un autre site réseau que l’appelé**|**Se trouve sur un site réseau inconnu ou n’est pas activé pour le routage par emplacement**|
|:-----|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Sonnerie simultanée autorisée par le biais de la stratégie de routage vocale de l’appelant  <br/> |Sonnerie simultanée autorisée par le biais de la stratégie de routage vocale de l’appelant  <br/> |Sonnerie simultanée autorisée par la stratégie vocale de l’appelant aux liaisons non activées pour le routage par emplacement  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Mise à jour cumulative 4 de Skype Entreprise

Avec la mise à jour cumulative 4 :

- Le routage de géolocalisation continue d’être activé par le biais d’une politique vocale, y compris pour les clients mobiles Skype entreprise.

- Le comportement d’appel pour les clients mobiles Skype entreprise dépend de leur activation pour le routage géolocalisation et du client de communication. Cette condition est conçue pour être statique ; toutefois dans certains cas, une action peut être nécessaire pour associer un client mobile Skype Entreprise à une passerelle PSTN et autoriser certains comportements, tels qu’une escalade.

- Quel que soit votre système d’exploitation, votre client mobile Skype Entreprise doit disposer de la même fonction.

Le tableau suivant vous indique quelques scénarios post-mise à jour cumulative 4 :

|**Utilisateur de routage en fonction de l’emplacement**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype entreprise mobile reçoit un appel RTC entrant.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype entreprise mobile effectue un appel RTC sortant.  <br/> |L’appel est acheminé via la fonctionnalité Appel via le bureau, non via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype entreprise mobile transfère alors l’appel vers un autre utilisateur ou contact.  <br/> |L’appel est acheminé via VoIP s’il s’agit d’un utilisateur ou contact local par rapport à la partie passerelle PSTN.  <br/> S’il s’agit d’un utilisateur ou contact distant par rapport à la partie passerelle PSTN, l’appel est acheminé via la fonctionnalité Appel via le bureau.  <br/> Si l’utilisateur cible n’est pas joignable via PSTN, l’appel échouera.  <br/> Si le contact cible est un standard automatique des conférences (CAA), l’appel sera bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Client Skype entreprise ou utilisateur fédéré  <br/> |Un mobile Skype entreprise effectue un appel vocal vers un autre client Skype entreprise ou un utilisateur fédéré.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Client Skype entreprise ou utilisateur fédéré  <br/> | Un client Skype entreprise ou un utilisateur fédéré effectue un appel vocal vers un utilisateur de routage d’emplacement mobile Skype entreprise. <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Client Skype entreprise ou utilisateur fédéré  <br/> |Un client Skype entreprise ou un utilisateur fédéré utilise un appel VoIP pour un utilisateur mobile Skype entreprise. Chaque partie passe à un utilisateur Skype entreprise ou fédéré supplémentaire.  <br/> |L’appel est réalisé via VoIP.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré est sur le point d’appel vocal d’un utilisateur de routage de l’emplacement mobile de Skype entreprise ; une fête mobile Skype entreprise passe à un utilisateur PSTN.  <br/> |L’appel est bloqué.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré utilise un appel VoIP pour un utilisateur de routage de l’emplacement mobile Skype entreprise ; chaque partie transmet un contact CAA.  <br/> |L’appel escaladé est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Utilisateur fédéré  <br/> |Un utilisateur fédéré utilise un appel VoIP pour un utilisateur de routage de l’emplacement mobile de Skype entreprise, et l’utilisateur fédéré passe à un utilisateur PSTN.  <br/> |La réaffectation sera autorisée ou interdite en fonction du routage sur l’emplacement de l’utilisateur fédéré. L’application de routage basée sur l’emplacement mobile de Skype entreprise ne prend aucune mesure.  <br/> |

### <a name="delegation"></a>Délégation

Les fonctionnalités de délégation de Skype entreprise sont affectées par le routage géolocalisation de la façon suivante :

- Lorsqu’un délégué activé pour le routage géolocalisation place un appel au nom d’un responsable, la stratégie vocale du délégué est utilisée pour autoriser l’appel et la stratégie de routage vocale du délégué est utilisée pour diriger l’appel.

- Pour les appels RTC passés à un responsable, les règles applicables au transfert d’appel ou à la sonnerie simultanée sont utilisées, comme décrit dans les rubriques « Transfert et renvoi des appels » et « Sonnerie simultanée ».

- Lorsqu’un délégué définit un point de terminaison PSTN en tant que cible de sonnerie simultanée pour un appel entrant au responsable, la stratégie de routage de la voix du site associé à la ligne entrante est utilisée pour diriger l’appel vers le point de terminaison RTC du délégué.

- Pour la délégation, il est recommandé que le responsable et ses délégués associés se trouvent généralement sur le même site réseau.

## <a name="other-planning-considerations"></a>Autres considérations de planification

Lors de la planification du routage par emplacement, vous devez prendre en compte l’impact sur les situations suivantes.

### <a name="disaster-recovery"></a>Récupération d’urgence

Lors d’un basculement entre le pool principal et un pool de sauvegarde, ainsi que lors de la restauration d’opérations normales sur le pool principal, le routage de l’emplacement reste appliqué à tout moment dans le cadre d’une procédure de sinistre et de récupération.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configuration de l’acheminement en fonction de l’emplacement a un impact sur la planification de l’endroit où vous déployez les passerelles associées à vos appareils distants. La passerelle associée à votre SBA doit se trouver dans le même site réseau que votre application de succursale Survivable ; dans le cas contraire, les utilisateurs hébergés sur votre unité de branchement Survivable ne sont pas autorisés à effectuer des appels sortants si le routage par emplacement est configuré. Lorsque la connexion WAN entre votre appareil de branchement Survivable et le site central est en panne, des restrictions de routage basées sur l’emplacement ne sont pas appliquées.

## <a name="client-and-server-support-for-location-based-routing"></a>Prise en charge des clients et des serveurs pour le routage géodépendant

Le routage basé sur l’emplacement est appliqué par Skype entreprise Server. Skype entreprise Server peut identifier les sites réseau dans lesquels les utilisateurs se connectent au sein du réseau d’entreprise. Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.

### <a name="server-support"></a>Prise en charge du serveur

Le routage basé sur l’emplacement nécessite le déploiement de Skype entreprise Server ou de Lync Server 2013 CU1 sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée. Si ces versions du serveur ne sont pas installées, les restrictions de routage basées sur l’emplacement ne peuvent pas être entièrement appliquées.

Le tableau suivant identifie la combinaison des rôles de serveur et des versions prises en charge pour le routage par emplacement.

****

|**Version du pool**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Mise à jour cumulative de Skype entreprise Server ou Lync Server 2013 février 2013  <br/> |Mise à jour cumulative de Skype entreprise Server ou Lync Server 2013 février 2013  <br/> |Oui  <br/> |
|Mise à jour cumulative de Skype entreprise Server ou Lync Server 2013 février 2013  <br/> |Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative de Skype entreprise Server ou Lync Server 2013 février 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative de Skype entreprise Server ou Lync Server 2013 février 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Lync Server 2013  <br/> |Quelconque  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Quelconque  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Quelconque  <br/> |Non  <br/> |

### <a name="client-support"></a>Prise en charge des clients

Le tableau suivant identifie les clients pris en charge par le routage de l’emplacement.

****

|**Type de client**|**Prise en charge**|**Détails**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> ||
|Lync 2013  <br/> |Oui  <br/> ||
|Lync 2010  <br/> |Oui  <br/> ||
|Office Communicator 2007 R2  <br/> |Non  <br/> ||
|Lync Phone Edition  <br/> |Oui  <br/> ||
|Lync Attendant  <br/> |Oui  <br/> ||
|Lync pour Windows 8  <br/> |Non  <br/> ||
|2013 mobile Lync  <br/> |Non  <br/> |VoIP doit être désactivée pour les clients 2013 mobiles Lync, s’il est utilisé par les utilisateurs avec le routage par emplacement activé.  <br/> |
|2010 mobile Lync  <br/> |Oui  <br/> ||

> [!NOTE]
> Pour désactiver le VoIP pour les clients Skype entreprise, attribuez une stratégie de mobilité avec le paramètre, audio/vidéo IP désactivé pour tous les utilisateurs activés pour le routage par emplacement. Pour plus d’informations sur la stratégie de mobilité, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Fonctionnalités non prises en charge par le routage géodépendant

Le routage basé sur l’emplacement ne s’applique pas aux types d’interactions suivants. Le routage par emplacement n’est pas appliqué lorsque les points de terminaison Skype entreprise interagissent avec les points de terminaison RTC grâce à ces fonctionnalités.

- Appels RTC entrants pour les conférences

- Appels RTC entrants et sortants via le groupe de réponse

- Parcage d’appel ou récupération des appels via le parcage d’appels

- Appels RTC entrants pour le service d’annonce

- Appels RTC entrants récupérés via la prise d’appel de groupe

Pour appliquer les règles de routage basées sur les emplacements aux types d’interactions dans la liste suivante, vous devez activer le routage par emplacement pour les conférences :

- Appels RTC sortants à partir des conférences

- Escalades à partir de conversations audio d’P2P vers des conférences impliquant des points de terminaison RTC

- Transferts consultatifs impliquant les points de terminaison RTC

Pour activer le routage par emplacement pour les conférences, voir [routage en fonction de l’emplacement pour les conférences](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


