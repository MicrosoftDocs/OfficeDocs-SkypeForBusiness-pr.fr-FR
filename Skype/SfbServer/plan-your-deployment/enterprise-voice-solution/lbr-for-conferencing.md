---
title: Location-Based routage des conférences dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planification du routage géolocal pour les conférences dans Skype Entreprise Server Voix Entreprise, y compris les transferts d’appels consultatifs.
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825574"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based routage des conférences dans Skype Entreprise Server

Planification du routage géolocal pour les conférences dans Skype Entreprise Server Voix Entreprise, y compris les transferts d’appels consultatifs.

Location-Based routage permet de restreindre le routage des appels entre les points de terminaison VoIP et les points de terminaison PSTN en fonction de l’emplacement des parties dans l’appel. Location-Based routage pour les conférences vous permet d’appliquer des règles de routage Location-Based aux réunions (c’est-à-dire, les conférences) pour empêcher le contournement de frais RSTN. L’application surveille une conférence active et applique Location-Based restrictions de routage en fonction de l’emplacement des utilisateurs participant. Le Location-Based routage pour l’application de conférence permet également l’application de restrictions de routage Location-Based aux transferts consultatifs impliquant des points de terminaison PSTN.

LLocation-Based'application de conférence de routage fournit aux conférences Skype Entreprise un mécanisme de prévention du contournement de frais PSTN. L’application surveille les conférences actives et applique Location-Based restrictions de routage basées sur l’emplacement des utilisateurs Skype Entreprise participant.

LLocation-Based'application de conférence de routage détermine si le routage Location-Based doit être appliqué à une réunion Skype Entreprise si les critères suivants sont satisfaits :

- L’organisateur de la réunion est activé pour Location-Based routage. Location-Based restrictions de routage seront appliquées uniquement aux conférences organisées par des utilisateurs activés pour le routage Location-Based réseau.

- Au moins un participant à la réunion est un point de terminaison PSTN. Location-Based restrictions de routage sont applicables uniquement pour les conférences qui incluent des points de terminaison PSTN.

- Site réseau où se trouve la passerelle PSTN utilisée pour relier la conférence au réseau PSTN, ainsi que les sites réseau depuis lequel les organisateurs et les participants se connectent.

Le Location-Based pour l’application de conférence empêche la participation des utilisateurs de Skype Entreprise et des points de terminaison PSTN de différents sites réseau à la même conférence. Si l’organisateur d’une réunion est activé pour Location-Based routage, l’application de conférence applique les restrictions suivantes :

- Les points de terminaison qui peuvent participer à une réunion Skype Entreprise dépendent des points de terminaison qui ont déjà rejoint la conférence, et cette restriction s’ajuste au départ des points de terminaison joints et aux nouveaux points de terminaison qui rejoignent la conférence. Si les organisateurs et les participants rejoignent une réunion Skype Entreprise à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un autre site réseau ou un participant d’un site réseau inconnu sont autorisés à participer.

- Si les organisateurs et les participants rejoignent la réunion à partir de sites réseau différents ou inconnus, un point de terminaison PSTN n’est pas autorisé à participer à la réunion si l’appel PSTN s’ingère à partir d’une ligne SIP activée pour le routage Location-Based.

- Si les organisateurs et les participants rejoignent tous la réunion à partir du même site réseau et que des participants rejoignent la même réunion à partir du réseau téléphonique téléphonique public (RST), un point de terminaison Skype Entreprise d’un autre site réseau n’est pas autorisé à participer à la réunion.

Ces restrictions de Location-Based de routage sont résumées dans le tableau suivant.

|Utilisateur(s) d’une conférence à un moment donné|Utilisateurs autorisés à participer à la conférence|Utilisateurs non autorisés à participer à la conférence|
|:-----|:-----|:-----|
|Utilisateurs de client VoIP Skype Entreprise à partir d’un site réseau unique  <br/> |Utilisateur client VoIP Skype Entreprise à partir du même site réseau  <br/> Utilisateur client VoIP Skype Entreprise à partir d’un autre site réseau  <br/> Utilisateur client VoIP Skype Entreprise à partir d’un site réseau inconnu  <br/> Utilisateur du client VoIP Skype Entreprise fédéré  <br/> Utilisateur rejoignant à partir d’un point de terminaison PSTN  <br/> |Aucun  <br/> |
|Utilisateurs de client VoIP Skype Entreprise à partir d’un site réseau inconnu  <br/> |Utilisateur client VoIP Skype Entreprise à partir de n’importe quel site  <br/> Utilisateur client VoIP Skype Entreprise à partir d’un site inconnu  <br/> Utilisateur du client VoIP Skype Entreprise fédéré  <br/> |Utilisateur rejoignant via un point de terminaison PSTN  <br/> |
|Utilisateurs de clients VoIP Skype Entreprise de différents sites réseau  <br/> |Utilisateur client VoIP Skype Entreprise à partir de n’importe quel site réseau  <br/> Utilisateur client VoIP Skype Entreprise à partir d’un site réseau inconnu  <br/> Utilisateur du client VoIP Skype Entreprise fédéré  <br/> |Utilisateur rejoignant via un point de terminaison PSTN  <br/> |
|Utilisateurs client VoIP Skype Entreprise d’un site réseau unique et utilisateurs rejoignant un point de terminaison PSTN  <br/> |Utilisateur client VoIP Skype Entreprise à partir du même site réseau  <br/> |Utilisateur client VoIP Skype Entreprise à partir d’un autre site réseau  <br/> Utilisateur client VoIP Skype Entreprise à partir d’un site réseau inconnu  <br/> Utilisateur du client VoIP Skype Entreprise fédéré  <br/> |

Voici des caractéristiques supplémentaires de l’application Location-Based routage des conférences :

- Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence en raison de restrictions de routage Location-Based, l’appel à la conférence est rejeté et le client Skype Entreprise signale que l’appel n’est pas terminé ou qu’il est terminé.

- Un point de terminaison PSTN rejoignant une conférence avec des mesures d’application du routage Location-Based ne sera pas limité pour participer à la conférence, quel que soit son état, si le point de terminaison rejoint une conférence via une trunk qui n’est pas activée pour le routage Location-Based.

- Un système PBX connecté à un serveur de médiation via une connexion SIP qui ne fait pas l’objet d’appels vers le réseau téléphonique public privé (PSTN) aura les mêmes mesures que les utilisateurs Skype Entreprise situés dans le même site réseau que celui où la connexion SIP est définie. Par exemple, un point de terminaison PSTN peut participer à une conférence avec un utilisateur PBX et un utilisateur Skype Entreprise s’ils se trouvent dans le même site réseau ; Dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à participer à la conférence si l’utilisateur PBX se trouve sur un site réseau différent de l’utilisateur Skype Entreprise.

> [!NOTE]
> Avec la mise à jour cumulative 4 de Skype Entreprise, le comportement indiqué dans le tableau suivant doit être observé :

|Utilisateur|Autre partie|Action|Résultat|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel PSTN. Skype Entreprise Mobile fait ensuite appel à une conférence Standard automatique (CAA).  <br/> |L’appel est bloqué, avec un message d’erreur approprié.  <br/> |
|Skype Entreprise Mobile  <br/> |Client Skype Entreprise ou utilisateur fédéré  <br/> |Le client ou l’utilisateur fédéré est en appel VoIP vers un utilisateur de routage Location-Based Skype Entreprise Mobile, et l’une ou l’autre des parties passe à une caA.  <br/> |L’appel d’escalade est bloqué, avec un message d’erreur approprié.  <br/> |

## <a name="consultative-call-transfers"></a>Transferts d’appels consultatifs

Outre l’application du routage Location-Based aux réunions Skype Entreprise, l’application de routage Location-Based pour les conférences applique des restrictions de routage Location-Based aux transferts d’appels consultatifs qui sortent vers les points de terminaison PSTN. Un transfert d’appel consultatif est un appel établi entre deux parties où l’une des parties transfère l’appel à un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Skype Entreprise). L’utilisateur A détermine que l’utilisateur PSTN doit être transmis à l’utilisateur B (utilisateur Skype Entreprise). L’utilisateur A place l’appel avec l’utilisateur PSTN en attente et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux d’appels de transfert d’appel consultatif**

![Diagramme de routage basé sur l’emplacement pour les conférences](../../media/LocationBasedRoutingForConferencing.jpg)

Lorsqu’un utilisateur activé pour le routage Location-Based lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme illustré dans la figure précédente), cela crée deux appels actifs, l’un entre l’utilisateur PSTN et l’utilisateur Skype Entreprise A, et l’autre entre l’utilisateur A de Skype Entreprise et l’utilisateur Skype Entreprise B. Le comportement suivant est appliqué par l’application de routage Location-Based pour la conférence :

- Si la liaison SIP routage de l’appel PSTN est autorisée à ré-router l’appel PSTN vers le site réseau où se trouve l’utilisateur B de Skype Entreprise (c’est-à-dire, cible de transfert), le transfert d’appel est autorisé . Dans le cas contraire, le transfert d’appel consultatif sera bloqué. Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée qui se trouve sur le même site réseau que la ligne SIP qui route l’appel actif vers le point de terminaison PSTN.

- Si la liaison SIP routant l’appel PSTN entrant n’est pas autorisée à router les appels vers le site réseau où se trouve la partie transférée (utilisateur B de Skype Entreprise) ou si la partie transférée se trouve dans un site réseau inconnu, le transfert d’appel consultatif vers le point de terminaison PSTN (c’est-à-dire, cible de transfert d’appel) sera bloqué.

Le tableau suivant décrit comment les restrictions de routage Location-Based sont appliquées par l’application Location-Based Routage des conférences pour les transferts d’appels consultatifs. Bien que les points de terminaison PBX ne soient pas directement associés à un site réseau, il est possible d’attribuer un site réseau à la ligne SIP à qui le PBX est connecté. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


|Site réseau de la partie transférée d’appel|Site réseau de la cible de transfert d’appel|Comportement|
|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Utilisateur Skype Entreprise dans le même site réseau (site 1)  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype Entreprise dans différents sites réseau (site 2)  <br/> |Le transfert consultatif sera non condentifié  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype Entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif sera non condentifié  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype Entreprise fédéré  <br/> |Le transfert consultatif sera non condentifié  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans le même site (site 1)  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans un autre site (autrement dit, site 2)  <br/> |Le transfert consultatif sera non condentifié  <br/> |
|Point de terminaison PBX dans le même site (site 1)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PBX dans un autre site (autrement dit, site 2)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif sera non condentifié  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype Entreprise dans le même site réseau (site 1)  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype Entreprise dans différents sites réseau (site 2)  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype Entreprise dans un site réseau inconnu  <br/> |Le transfert consultatif sera autorisé  <br/> |
|Point de terminaison PBX dans n’importe quel site  <br/> |Utilisateur Skype Entreprise fédéré  <br/> |Le transfert consultatif sera autorisé  <br/> |

## <a name="requirements"></a>Conditions requises

L’application de routage Location-Based pour la conférence nécessite que la mise à jour cumulative 2 de Skype Entreprise Server ou Lync Server 2013 soit déployée sur tous les pools Front-End et serveurs Standard Edition Server de votre topologie. Si ces versions de serveur ne sont pas installées sur certains serveurs de votre topologie, les restrictions de routage Location-Based ne peuvent pas être entièrement appliquées aux réunions et aux transferts d’appels consultatifs.

Le tableau suivant identifie la combinaison des rôles serveur et des versions qui Location-Based routage.


|Front-End pool|Version du serveur de médiation|Pris en charge|
|:-----|:-----|:-----|
|Mise à jour cumulative 2 de Skype Entreprise Server ou Lync Server 2013  <br/> |Mise à jour cumulative 2 de Skype Entreprise Server ou Lync Server 2013  <br/> |Oui  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Mise à jour cumulative 1 de Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Mise à jour cumulative 1 de Lync Server 2013  <br/> |N’importe lequel  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |N’importe lequel  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |N’importe lequel  <br/> |Non  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuration du Location-Based routage des conférences

Le Location-Based routage pour l’application de conférence repose sur la configuration du Location-Based routage. Les configurations principales sont les suivantes :

- L’emplacement des participants qui rejoignent une réunion est déterminé en fonction de leur site réseau. Un site réseau et ses sous-réseaux associés doivent être définis dans Skype Entreprise Server afin d’appliquer Location-Based routage.

- Pour appliquer Location-Based routage des réunions, les participants Skype Entreprise doivent être activés pour Location-Based routage.

- Pour appliquer Location-Based routage des points de terminaison PSTN rejoignant des réunions, la connexion SIP utilisée pour connecter les points de terminaison PSTN doit être configurée pour le routage Location-Based réseau.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Activation du Location-Based routage des conférences

Le Location-Based routage de l’application de conférence est désactivé par défaut. Avant d’activer cette application, vous devez déterminer la priorité à affecter à l’application. Pour déterminer cette priorité, exécutez la cmdlet suivante dans Skype Entreprise Server Management Shell :

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Dans cette cmdlet, est le pool dans lequel le routage Location-Based pour l’application de conférence \<Pool FQDN\> doit être activé.

Cette cmdlet retourne la liste des applications hébergées par Skype Entreprise Server et la valeur de priorité pour chacune d’entre elles. Le routage Location-Based pour l’application de conférence doit avoir une valeur de priorité supérieure à celle de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter à l’application Location-Based Routage des conférences une valeur de priorité supérieure d’un point à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité « 2 », l’application « DefaultRouting » a une valeur de priorité « 8 », l’application « ExumRouting » a une valeur de priorité « 9 » et l’application « OutboundRouting » a une valeur de priorité « 10 », vous devez affecter à l’application de routage Location-Based pour conférence une valeur de priorité de « 3 ». Cela place la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage Location-Based (priorité : 3), autres applications (priorités : 4 à 8), « DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de routage Location-Based pour la conférence, tapez l’cmdlet suivante pour chaque pool Front-End ou serveur Standard Edition Server qui retent les utilisateurs activés pour Location-Based routage :

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Par exemple :

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Après avoir utilisé cette applet de bord, redémarrez tous les serveurs frontux du pool ou les serveurs Standard Edition Où le routage Location-Based pour l’application de conférence a été activé.

> [!IMPORTANT]
> Location-Based'application du routage vers des conférences ou des transferts consultatifs ne sera pas appliquée tant que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Servers ne seront pas redémarrés. Si vous **définissez -Critical** to **$true** dans les cmdlets précédentes, vos services Skype Entreprise Server seront immédiatement redémarrés. Si vous ne souhaitez pas que ces services redémarrent immédiatement, définissez **-Critical** sur **$false** pour le moment, puis utilisez **Set-CsServerApplication** pour modifier **-Critical** pour **$true** ultérieurement, après le redémarrage des services.

Une fois que le routage Location-Based pour l’application de conférence a été activé avec succès et que tous les serveurs applicables ont été redémarrés, toutes les conférences organisées par les utilisateurs skype entreprise activées pour le routage Location-Based sont surveillées pour empêcher le contournement des frais de réseau téléphonique privé (PSTN).


