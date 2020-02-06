---
title: Routage basé sur l’emplacement pour les conférences dans Skype entreprise Server
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
description: Planification du routage basé sur l’emplacement pour les conférences dans Skype entreprise Server Voice, y compris les virements de consultation.
ms.openlocfilehash: d03bab835556bf0cea4dffb33bcfbcc48ba7fa42
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802844"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Routage basé sur l’emplacement pour les conférences dans Skype entreprise Server

Planification du routage basé sur l’emplacement pour les conférences dans Skype entreprise Server Voice, y compris les virements de consultation.

Le routage basé sur l’emplacement permet de limiter le routage des appels entre les points de terminaison VoIP et les points de terminaison RTC en fonction de l’emplacement des parties de l’appel. Le routage basé sur l’emplacement pour la Conférence vous permet d’appliquer des règles de routage de géolocalisation pour les réunions (par exemple, des conférences) afin d’éviter un contournement du numéro PSTN. L’application surveille une conférence active et applique des restrictions de routage basées sur l’emplacement en fonction de l’emplacement des utilisateurs qui participent. Par ailleurs, le routage selon l’emplacement de l’application de conférence autorise l’application de restrictions de routage basées sur l’emplacement aux transferts de points de terminaison RTC.

L’application de conférence de routage basée sur des emplacements fournit aux conférences Skype entreprise un mécanisme de prévention du contournement du numéro RTC. L’application surveille les conférences actives et applique les restrictions de routage basées sur les emplacements en fonction de l’emplacement des utilisateurs Skype entreprise participant.

L’application de conférence de routage basée sur l’emplacement détermine si le routage selon l’emplacement doit être appliqué lors d’une réunion Skype entreprise si les critères suivants sont satisfaits :

- L’organisateur de la réunion est activé pour le routage par emplacement. Les restrictions de routage basées sur les emplacements ne s’appliquent qu’aux conférences organisées par des utilisateurs qui sont configurés pour le routage selon l’emplacement.

- Au moins un participant à la réunion est un point de terminaison PSTN. Les restrictions de routage basées sur les emplacements ne s’appliquent qu’aux conférences qui incluent des points de terminaison PSTN.

- Le site réseau sur lequel la passerelle PSTN utilisée pour relier la conférence au réseau téléphonique commuté est localisée, de même que les sites réseau depuis lesquels les organisateurs et les participants se connectent.

Le routage basé sur l’emplacement pour l’application de conférence empêche la participation d’utilisateurs Skype entreprise et de points de terminaison RTC de différents sites réseau à la même conférence. Si l’organisateur d’une réunion est activé pour le routage sur l’emplacement, l’application de conférence applique les restrictions suivantes :

- Les points de terminaison qui peuvent participer à une réunion Skype entreprise dépendent des points de terminaison qui ont déjà participé à la Conférence, et cette restriction s’ajuste en tant que points de terminaison joints et de nouveaux points de terminaison rejoindre la Conférence. Si les organisateurs et les participants participent à une réunion Skype entreprise à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un site réseau différent ou un participant d’un site réseau inconnu sont autorisés à participer.

- Si les organisateurs et les participants rejoignent la réunion à partir d’autres sites réseaux ou de sites réseau inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel PSTN provient d’une jonction SIP pour laquelle le routage géodépendant est activé.

- Si les organisateurs et les participants se connectent à la réunion à partir du même site réseau et qu’il y a des participants qui rejoignent la même réunion à partir du RTC, le point de terminaison Skype entreprise d’un site réseau différent n’est pas autorisé à rejoindre la réunion.

Ces restrictions de routage basées sur l’emplacement des conférences sont résumées dans le tableau suivant.

| |

|**Utilisateur(s) dans une conférence à un moment donné**|**Utilisateur(s) autorisés à rejoindre la conférence**|**Utilisateur(s) non autorisés à rejoindre la conférence**|
|:-----|:-----|:-----|
|Utilisateurs du client VoIP Skype entreprise à partir d’un site réseau unique  <br/> |Utilisateur du client VoIP Skype entreprise du même site réseau  <br/> Utilisateur du client VoIP Skype entreprise sur un site réseau différent  <br/> Utilisateur du client VoIP Skype entreprise sur un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> Utilisateur rejoignant la conférence à partir d’un point de terminaison PSTN  <br/> |Aucune  <br/> |
|Utilisateurs du client VoIP Skype entreprise à partir d’un site réseau inconnu  <br/> |Utilisateur de client VoIP Skype entreprise sur n’importe quel site  <br/> Utilisateur du client VoIP Skype entreprise d’un site inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Utilisateurs du client VoIP Skype entreprise provenant de différents sites réseau  <br/> |Utilisateur de client VoIP Skype entreprise sur n’importe quel site réseau  <br/> Utilisateur du client VoIP Skype entreprise sur un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |Utilisateur rejoignant la conférence via un point de terminaison PSTN  <br/> |
|Utilisateurs du client VoIP Skype entreprise à partir d’un site de réseau unique et utilisateurs qui se connectent à partir d’un point de terminaison RTC  <br/> |Utilisateur du client VoIP Skype entreprise du même site réseau  <br/> |Utilisateur du client VoIP Skype entreprise sur un site réseau différent  <br/> Utilisateur du client VoIP Skype entreprise sur un site réseau inconnu  <br/> Utilisateur de client VoIP Skype entreprise fédéré  <br/> |

Vous trouverez ci-après des caractéristiques supplémentaires du routage selon l’emplacement de l’application de conférence :

- Lorsque l’utilisateur ne peut pas participer à une conférence en fonction de ses restrictions de routage, l’appel de la Conférence est rejeté et le client Skype entreprise signale que l’appel n’a pas abouti ou a pris fin.

- Un point de terminaison RTC rejoignant une conférence avec des mises en application de routage basées sur les emplacements ne sera pas limité à la Conférence, quel que soit son état, si le point de terminaison est joint par le biais d’un Trunk qui n’est pas activé pour le routage sur site.

- Un système PBX connecté à un serveur de médiation par le biais d’un réseau SIP qui ne décharge pas les appels vers le RTC sera le même pour les utilisateurs Skype entreprise situés dans le même site réseau où le Trunk SIP est défini. Par exemple, un point de terminaison PSTN peut participer à une conférence avec un utilisateur PBX et un utilisateur de Skype entreprise s’il se trouve sur le même site réseau. dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à rejoindre la Conférence si l’utilisateur PBX se trouve sur un autre site réseau que l’utilisateur Skype entreprise.

> [!NOTE]
> Avec la mise à jour cumulative 4 de Skype Entreprise, vous devriez observer le comportement décrit dans le tableau suivant :

|**User**|**Autre partie**|**Action**|**Résultat**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Mobile  <br/> |PSTN  <br/> |Skype Entreprise Mobile est en appel RTC. Skype Entreprise Mobile transforme ensuite l'appel en standard automatique des conférences (CAA).  <br/> |L’appel est bloqué, avec un message d’erreur correspondant.  <br/> |
|Skype Entreprise Mobile  <br/> |Client ou utilisateur fédéré Skype Entreprise  <br/> |Le client ou le fournisseur fédéré utilise un appel VoIP pour un utilisateur de routage de l’emplacement mobile de Skype entreprise et chaque partie passe à une CAA.  <br/> |La transformation de l’appel est bloquée, avec un message d’erreur correspondant.  <br/> |

## <a name="consultative-call-transfers"></a>Transferts d’appel consultatifs

En plus d’appliquer le routage sur site aux réunions Skype entreprise, le routage par emplacement pour l’application de conférence applique les restrictions de routage basées sur les emplacements des points de terminaison RTC. Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appel Skype entreprise). Un utilisateur A détermine que l’utilisateur RTC doit être renvoyé à l’utilisateur B (utilisateur Skype entreprise). L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux des transferts d’appel consultatifs**

![Diagramme Routage géodépendant pour les conférences](../../media/LocationBasedRoutingForConferencing.jpg)

Lorsqu’un utilisateur a activé le routage de géolocalisation, le transfert d’appel d’un point de terminaison PSTN (comme illustré dans la figure ci-dessus) entraîne la création de deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur Skype entreprise A, et l’autre entre Skype pour Utilisateur professionnel A et utilisateur Skype entreprise B. le comportement suivant est appliqué par le routage par emplacement pour l’application de conférence :

- Si le routage SIP Trunk est autorisé à rediriger l’appel RTC vers le site du réseau où se trouve l’utilisateur Skype entreprise B (c.-à-d. destination du transfert), le transfert d’appel sera autorisé. dans le cas contraire, le transfert d’appel consultatif sera bloqué. Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée sur le même site réseau que le Trunk SIP qui achemine l’appel actif vers le point de terminaison RTC.

- Si le routage SIP à l’origine de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site du réseau sur lequel la partie transférée (utilisateur Skype entreprise B) est située ou si la partie transférée est située sur un site réseau inconnu, le transfert d’appel vers le point de terminaison PSTN (par exemple, cible de transfert d’appel) sera bloqué.

Le tableau suivant décrit la façon dont les restrictions de routage basées sur les emplacements sont appliquées par le routage basé sur l’emplacement pour l’application de conférence pour les transferts d’appel. Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


|**Site réseau de la partie dont l’appel est transféré**|**Site réseau de la cible de transfert d’appel**|**Comportement**|
|:-----|:-----|:-----|
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise sur le même site réseau (par exemple, site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Utilisation de Skype entreprise sur différents sites réseau (par exemple, site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur Skype entreprise sur un site réseau inconnu  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Utilisateur fédéré Skype entreprise  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans le même site (site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PSTN  <br/> |Point de terminaison PBX dans un autre site (site 2)  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans le même site (site 1)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un autre site (site 2)  <br/> |Point de terminaison PSTN  <br/> |Le transfert consultatif n’est pas autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Utilisateur Skype entreprise sur le même site réseau (par exemple, site 1)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Utilisation de Skype entreprise sur différents sites réseau (par exemple, site 2)  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Utilisateur Skype entreprise sur un site réseau inconnu  <br/> |Le transfert consultatif est autorisé  <br/> |
|Point de terminaison PBX dans un site quelconque  <br/> |Utilisateur fédéré Skype entreprise  <br/> |Le transfert consultatif est autorisé  <br/> |

## <a name="requirements"></a>Configuration requise

Le routage sur la base de l’emplacement de l’application de conférence nécessite que Skype entreprise Server ou Lync Server 2013 cumulative Update 2 soit déployé sur tous les pools front-end et les serveurs Standard Edition dans votre topologie. Si les versions serveur suivantes ne sont pas installées sur certains serveurs de votre topologie, les restrictions de routage par emplacement ne peuvent pas être appliquées entièrement lors des réunions et des transferts d’appels.

Le tableau suivant identifie la combinaison de rôles et de versions du serveur prenant en charge le routage par emplacement.


|**Version de pool frontal**|**Version de serveur de médiation**|**Prise en charge**|
|:-----|:-----|:-----|
|Mise à jour cumulative 2 de Skype entreprise Server ou Lync Server 2013  <br/> |Mise à jour cumulative 2 de Skype entreprise Server ou Lync Server 2013  <br/> |Oui  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Mise à jour cumulative 1 de Lync Server 2013  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Lync Server 2010  <br/> |Non  <br/> |
|Mise à jour cumulative 2 de Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Non  <br/> |
|Mise à jour cumulative 1 de Lync Server 2013  <br/> |Indifférente  <br/> |Non  <br/> |
|Lync Server 2010  <br/> |Indifférente  <br/> |Non  <br/> |
|Office Communications Server 2007 R2  <br/> |Indifférente  <br/> |Non  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuration de l’acheminement en fonction de l’emplacement pour les conférences

Le routage basé sur l’emplacement pour l’application de conférence repose sur la configuration du routage par emplacement. Les configurations principales suivantes sont disponibles :

- L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau. Un site réseau et ses sous-réseaux associés doivent être définis dans Skype entreprise Server pour appliquer le routage géolocalisation.

- Pour appliquer le routage de réunions selon l’emplacement, les participants Skype entreprise doivent être activés pour le routage géolocalisation.

- Pour appliquer le routage de points de terminaison PSTN qui se connecte à l’emplacement de la réunion, le Trunk SIP utilisé pour connecter les points de terminaison PSTN doit être configuré pour le routage basé sur l’emplacement.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Activation du routage par emplacement pour les conférences

Par défaut, le routage sur la base de l’emplacement de l’application de conférence est désactivé. Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Skype entreprise Server Management Shell :

Get-CsServerApplication-Identity service : Registrar<Pool FQDN>: dans cette applet \<de demande\> , le nom de domaine complet (FQDN) du pool est le pool dans lequel l’application de routage basée sur l’emplacement pour la Conférence doit être activée.

Cette applet de demande renvoie la liste des applications hébergées par Skype entreprise Server et la valeur de priorité de chacune d’elles. L’application de routage basée sur l’emplacement pour une application de conférence doit être affectée d’une valeur de priorité supérieure à l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter au routage de l’emplacement de l’application une valeur de priorité qui est un point supérieur à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité de « 2 », l’application « DefaultRouting » a une valeur de priorité de « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 », alors vous devez affecter au routage de l’emplacement de l’application une valeur de priorité de « 3 ». En procédant de la sorte, vous devez placer la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), "UdcAgent" (Priority : 2), application de conférence de routage basée sur l’emplacement (priorité : 3) DefaultRouting "(priorité : 9)," ExumRouting "(priorité : 10) et" OutboundRouting "(priorité : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de routage basée sur l’emplacement de la Conférence, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition sur lequel les utilisateurs ont activé le routage de l’emplacement :

New-CsServerApplication-Identity service : Bureau`<Pool FQDN` d’enregistrement :> \</Lbrouting-\> Priority application $true-$true-URL Critical.<http://www.microsoft.com/LCS/LBRouting> 

Par exemple :

New-CsServerApplication-Identity service :Registrar :LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3 $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting 

Après avoir utilisé cette applet de demande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition dans lesquels l’application de routage basée sur l’emplacement de la Conférence est activée.

> [!IMPORTANT]
> Les application de routage basées sur les emplacements aux conférences ou aux transferts de consultation ne seront pas appliquées tant que tous les serveurs frontaux dans les listes applicables ou les serveurs Standard Edition Server ne sont pas redémarrés. Si vous définissez la valeur **critique** sur **$true** dans les applets de la précédente, vos services Skype entreprise Server seront immédiatement redémarrés. Si vous ne souhaitez pas que ces services ne redémarrent pas immédiatement, définissez **-Critical** sur **$false** pour le moment, puis utilisez **Set-CsServerApplication** pour modifier **les éléments critiques** pour **$true** plus tard, une fois les services redémarrés.

Lorsque l’application de routage basée sur l’emplacement de l’application de conférence est activée et que tous les serveurs concernés ont été redémarrés, toutes les conférences organisées par des utilisateurs Skype entreprise activées pour le routage de l’emplacement seront surveillées pour éviter Contournement du numéro RTC


