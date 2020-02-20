---
title: Routage géodépendant pour les conférences dans Skype entreprise Server
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planification du routage géodépendant pour les conférences dans Skype entreprise Server Voice, y compris les transferts d’appels consultatifs.
ms.openlocfilehash: decfe8117b3b47c5de4db8a7d0963eca587d0da1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42130177"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Routage géodépendant pour les conférences dans Skype entreprise Server

Planification du routage géodépendant pour les conférences dans Skype entreprise Server Voice, y compris les transferts d’appels consultatifs.

Le routage géodépendant permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties dans l’appel. Le routage géodépendant pour les conférences vous permet d’appliquer des règles de routage géodépendant aux réunions (par exemple, des conférences) afin d’empêcher le contournement des appels PSTN. L’application surveille une conférence active et applique des restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs qui y participent. Le routage géodépendant pour l’application de conférence permet également d’appliquer des restrictions de routage géodépendant aux transferts consultatifs impliquant des points de terminaison PSTN.

L’application de conférence de routage basée sur l’emplacement fournit aux conférences Skype entreprise un mécanisme permettant de prévenir le contournement des appels RTC. L’application surveille les conférences actives et applique des restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs de Skype entreprise.

L’application de conférence de routage basée sur l’emplacement détermine si le routage géodépendant doit être appliqué à une réunion Skype entreprise si les critères suivants sont satisfaits :

- L’organisateur de la réunion est activé pour le routage géodépendant. Les restrictions de routage basées sur l’emplacement seront appliquées uniquement aux conférences organisées par des utilisateurs activés pour le routage géodépendant.

- Au moins un participant à la réunion est un point de terminaison PSTN. Les restrictions de routage basées sur l’emplacement sont applicables uniquement pour les conférences qui incluent des points de terminaison PSTN.

- Le site réseau où se trouve la passerelle PSTN servant à relier la Conférence au RTC est disponible, ainsi que les sites réseau à partir desquels les organisateurs et les participants se connectent.

Le routage géodépendant de l’application de conférence empêche la participation des utilisateurs Skype entreprise et des points de terminaison RTC de différents sites réseau à la même conférence. Si l’organisateur d’une réunion est activé pour le routage géodépendant, l’application de conférence applique les restrictions suivantes :

- Les points de terminaison qui peuvent participer à une réunion Skype entreprise dépendent des points de terminaison qui ont déjà rejoint la Conférence, et cette restriction s’ajuste en tant que points de terminaison joints et de nouveaux points de terminaison joignent la Conférence. Si les organisateurs et les participants joignent une réunion Skype entreprise à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un site réseau différent ou un participant d’un site réseau inconnu sont autorisés à rejoindre.

- Si les organisateurs et les participants rejoignent la réunion à partir de sites réseau différents ou inconnus, un point de terminaison PSTN n’est pas autorisé à participer à la réunion si l’appel RTC pénètre à partir d’une jonction SIP activée pour le routage géodépendant.

- Si les organisateurs et les participants rejoignent la réunion à partir du même site réseau et que des participants joignent la même réunion à partir du RTC, un point de terminaison Skype entreprise d’un site réseau différent n’est pas autorisé à participer à la réunion.

Ces restrictions de routage basées sur l’emplacement des conférences sont résumées dans le tableau suivant.

| |

|**Utilisateur (s) dans une conférence à tout moment**|**Utilisateur (s) autorisé à rejoindre la Conférence**|**Utilisateur (s) non autorisé à rejoindre la Conférence**|
|:-----|:-----|:-----|
|Utilisateur (s) de client VoIP Skype entreprise à partir d’un site réseau unique  <br/> |Utilisateur de client VoIP Skype entreprise à partir du même site réseau  <br/> Utilisateur de client VoIP Skype entreprise à partir d’un autre site réseau  <br/> Utilisateur de client VoIP Skype entreprise à partir d’un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> Appartenance d’un utilisateur à partir d’un point de terminaison PSTN  <br/> |Néant  <br/> |
|Utilisateur (s) de client VoIP Skype entreprise à partir d’un site réseau inconnu  <br/> |Utilisateur de client VoIP Skype entreprise à partir de n’importe quel site  <br/> Utilisateur de client VoIP Skype entreprise à partir d’un site inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |Appartenance d’un utilisateur via un point de terminaison PSTN  <br/> |
|Utilisateurs de clients VoIP Skype entreprise provenant de sites réseau différents  <br/> |Utilisateur de client VoIP Skype entreprise à partir de n’importe quel site réseau  <br/> Utilisateur de client VoIP Skype entreprise à partir d’un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |Appartenance d’un utilisateur via un point de terminaison PSTN  <br/> |
|Utilisateurs du client VoIP Skype entreprise à partir d’un site réseau unique et les utilisateurs qui rejoignent un point de terminaison PSTN  <br/> |Utilisateur de client VoIP Skype entreprise à partir du même site réseau  <br/> |Utilisateur de client VoIP Skype entreprise à partir d’un autre site réseau  <br/> Utilisateur de client VoIP Skype entreprise à partir d’un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |

Les caractéristiques supplémentaires du routage géodépendant pour l’application de conférence sont les suivantes :

- Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence des restrictions de routage basées sur l’emplacement, l’appel de la Conférence est rejeté et le client Skype entreprise signale que l’appel n’a pas abouti ou s’est terminé.

- Un point de terminaison PSTN joignant une conférence avec des mises en œuvre de routage géodépendant n’est pas limité à rejoindre la Conférence indépendamment de son état si le point de terminaison se joint via une jonction qui n’est pas activée pour le routage géodépendant.

- Un système PBX connecté à un serveur de médiation par le biais d’une jonction SIP qui ne sort pas les appels vers le RTC aura les mêmes mises en œuvre que les utilisateurs Skype entreprise situés dans le même site réseau où la jonction SIP est définie. Par exemple, un point de terminaison PSTN pourra rejoindre une conférence avec un utilisateur PBX et un utilisateur Skype entreprise s’il se trouve dans le même site réseau ; dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à rejoindre la Conférence si celui-ci se trouve dans un autre site réseau que l’utilisateur de Skype entreprise.

> [!NOTE]
> Avec la mise à jour cumulative 4 de Skype entreprise, le comportement dans le tableau suivant doit être observé :

|**User**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype entreprise mobile  <br/> |RTC  <br/> |Skype entreprise mobile est un appel RTC. Skype entreprise mobile transfère ensuite l’appel vers un standard automatique de conférence (CAA).  <br/> |L’appel est bloqué, avec un message d’erreur approprié.  <br/> |
|Skype entreprise mobile  <br/> |Client Skype entreprise ou utilisateur fédéré  <br/> |Le client ou utilisateur fédéré est sur un appel VoIP à un utilisateur de routage basé sur l’emplacement mobile Skype entreprise, et chaque partie passe à un CAA.  <br/> |L’appel d’escalade est bloqué, avec un message d’erreur approprié.  <br/> |

## <a name="consultative-call-transfers"></a>Transferts d’appel consultatifs

En plus de l’application du routage géodépendant aux réunions Skype entreprise, le routage géodépendant de l’application de conférence applique des restrictions de routage géodépendant sur des transferts d’appel consultatifs qui sont sortants vers des points de terminaison PSTN. Un transfert d’appel consultatif est un appel établi entre deux parties où une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Skype entreprise). L’utilisateur A détermine que l’utilisateur RTC doit être transféré à l’utilisateur B (utilisateur Skype entreprise). L’utilisateur A passe l’appel avec l’utilisateur RTC en conservation et appelle l’utilisateur B. l’utilisateur B accepte de communiquer avec l’utilisateur RTC. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux d’appels consultatifs de transfert d’appel**

![Routage géodépendant pour le diagramme de conférence](../../media/LocationBasedRoutingForConferencing.jpg)

Lorsqu’un utilisateur activé pour le routage géodépendant lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme illustré dans la figure précédente), cela crée deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur Skype entreprise A, et l’autre entre Skype Utilisateur de l’entreprise A et Skype entreprise B. le comportement suivant est appliqué par le routage géodépendant de l’application de conférence :

- Si le routage de jonction SIP est autorisé à réacheminer l’appel RTC vers le site réseau où se trouve l’utilisateur Skype entreprise B (c.-à-d ? cible de transfert), le transfert d’appel sera autorisé ; dans le cas contraire, le transfert consultatif est bloqué. Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée dans le même site réseau que la jonction SIP qui achemine l’appel actif vers le point de terminaison PSTN.

- Si le routage de jonction SIP de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site réseau où la partie transférée (Skype entreprise B) est située ou la partie transférée se trouve dans un site réseau inconnu, le contact consultatif passe à le point de terminaison PSTN (par exemple, destination de transfert d’appel) est bloqué.

Le tableau suivant décrit la façon dont les restrictions de routage basées sur l’emplacement sont appliquées par le routage géodépendant pour l’application de conférence pour les transferts d’appels consultatifs. Bien que les points de terminaison PBX ne soient pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


|**Site réseau de la partie transférée d’appel**|**Site réseau de la cible de transfert d’appel**|**Comportement**|
|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise dans le même site réseau (par exemple, site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise dans différents sites réseau (par exemple, site 2)  <br/> |Le transfert consultatif est interdit  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif est interdit  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise fédéré  <br/> |Le transfert consultatif est interdit  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans le même site (par exemple, site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans différents sites (par exemple, site 2)  <br/> |Le transfert consultatif est interdit  <br/> |
|Point de terminaison PBX dans le même site (par exemple, site 1)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un autre site (par exemple, site 2)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif est interdit  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype entreprise dans le même site réseau (par exemple, site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype entreprise dans différents sites réseau (par exemple, site 2)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype entreprise fédéré  <br/> |Le transfert consultatif est autorisé  <br/> |

## <a name="requirements"></a>Configuration requise

Le routage géodépendant pour l’application de conférence nécessite le déploiement de Skype entreprise Server ou Lync Server 2013 cumulative Update 2 sur tous les pools frontaux et les serveurs Standard Edition de votre topologie. Si ces versions de serveur ne sont pas installées sur certains serveurs de votre topologie, les restrictions de routage géodépendant ne peuvent pas être entièrement appliquées lors des réunions et des transferts d’appel consultatifs.

Le tableau suivant identifie les combinaisons de rôles serveur et de versions qui prennent en charge le routage géodépendant.


|**Version du pool frontal**|**Version du serveur de médiation**|**Pris en charge**|
|:-----|:-----|:-----|
|Mise à jour cumulative 2 pour Skype entreprise Server ou Lync Server 2013  <br/> |Mise à jour cumulative 2 pour Skype entreprise Server ou Lync Server 2013  <br/> |Oui  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Mise à jour cumulative 1 de Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Mise à jour cumulative 1 de Lync Server 2013  <br/> |N'importe lequel  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |N'importe lequel  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |N'importe lequel  <br/> |Non  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuration du routage géodépendant pour les conférences

Le routage géodépendant de l’application de conférence repose sur la configuration du routage géodépendant. Les configurations principales sont les suivantes :

- L’emplacement des participants qui rejoignent une réunion est déterminé en fonction de leur site réseau. Un site réseau et ses sous-réseaux associés doivent être définis dans Skype entreprise Server afin d’appliquer le routage géodépendant.

- Pour appliquer le routage géodépendant des réunions, les participants Skype entreprise doivent être activés pour le routage géodépendant.

- Pour appliquer le routage géodépendant des points de terminaison PSTN joignant des réunions, la jonction SIP utilisée pour connecter les points de terminaison PSTN doit être configurée pour le routage géodépendant.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Activation du routage géodépendant pour les conférences

Le routage géodépendant de l’application de conférence est désactivé par défaut. Avant d’activer cette application, vous devez déterminer la priorité appropriée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Skype entreprise Server Management Shell :

Get-CsServerApplication-Identity service : serveur<Pool FQDN>d’inscriptions : dans \<cette applet\> de commande, le nom de domaine complet du pool est le pool dans lequel le routage géodépendant pour l’application de conférence doit être activé.

Cette applet de commande renvoie la liste des applications hébergées par Skype entreprise Server et la valeur de priorité de chacune d’elles. Le routage géodépendant pour l’application de conférence doit disposer d’une valeur de priorité supérieure à celle de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’attribuer au routage géodépendant une valeur de priorité d’un point supérieur à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité « 2 », l’application « DefaultRouting » a une valeur de priorité « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 », puis vous devez attribuer la valeur de priorité « 3 » au routage géodépendant pour l’application de conférence. Cette opération placerait la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage basée sur l’emplacement (Priority : 3), autres applications (priorités : 4 à 8), " DefaultRouting "(Priority : 9)," ExumRouting "(Priority : 10) et" OutboundRouting "(Priority : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour le routage géodépendant pour l’application de conférence, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition qui héberge les utilisateurs pour lesquels le routage géodépendant est activé :

New-CsServerApplication-Identity service : Registrar`<Pool FQDN` :>/lbrouting- \<priority\> Application Priority $true-Critical $true-URI<https://www.microsoft.com/LCS/LBRouting> 

Par exemple :

New-CsServerApplication-Identity service :Registrar :LS2013CU2LBRPool. contoso. com/LBRouting-Optional 3-enabled $true-URI $true-URIhttps://www.microsoft.com/LCS/LBRouting 

Après avoir utilisé cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition où le routage géodépendant de l’application de conférence a été activé.

> [!IMPORTANT]
> Les conditions de routage géodépendant des conférences ou des transferts consultatifs ne sont pas appliquées tant que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Server ne sont pas redémarrés. Si vous définissez la valeur **-Critical** sur **$true** dans les applets de commande précédentes, vos services Skype entreprise Server seront immédiatement redémarrés. Si vous ne souhaitez pas que ces services redémarrent immédiatement, affectez la valeur Critical à **$false** pour **le** moment, puis utilisez **Set-CsServerApplication** pour modifier la valeur **critique** pour **$true** ultérieurement, après le redémarrage des services.

Une fois que le routage géodépendant de l’application de conférence a été correctement activé et que tous les serveurs concernés ont été redémarrés, toutes les conférences organisées par des utilisateurs Skype entreprise activés pour le routage géodépendant sont surveillées pour empêcher Dérivation de péage PSTN


