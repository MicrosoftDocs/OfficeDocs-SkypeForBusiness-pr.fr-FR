---
title: Planifier les services d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Découvrez les services Enhanced 9-1-1 (E9-1-1) dans Skype Entreprise Server Voix Entreprise, notamment l’acquisition d’emplacement et le routage des appels.
ms.openlocfilehash: f3efcea6747c27e041e581b5d0461fd4c925eb84
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767612"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planifier les services d’urgence dans Skype Entreprise Server

Découvrez les services Enhanced 9-1-1 (E9-1-1) dans Skype Entreprise Server Voix Entreprise, notamment l’acquisition d’emplacement et le routage des appels.

Skype Entreprise Server prend en charge les services Enhanced 9-1-1 (E9-1-1) aux États-Unis dans le cadre d’un déploiement Voix Entreprise déploiement. E9-1-1 est une fonctionnalité de réponse aux appels d’urgence qui associe un appel au 911 à un emplacement de réponse d’urgence (ERL, Emergency Response Location) qui est constitué d’une adresse (c’est-à-dire, une rue) et d’informations d’emplacement spécifiques, tels qu’un numéro d’étage, pour les appels provenant d’immeubles de bureaux et d’habitation. À l’aide de l’emplacement de réponse d’urgence fourni, un centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) peut immédiatement transférer les appels de détresse aux services d’urgence appropriés sans risquer de leur fournir de mauvaises informations.

> [!NOTE]
> Skype Entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Pour plus d’informations, [voir Planifier plusieurs numéros d’urgence dans Skype Entreprise Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype Entreprise Server offre trois fonctionnalités Voix Entreprise avancées : le contrôle d’admission des appels, les services d’urgence (E9-1-1) et le contournement de média. Pour une vue d’ensemble des informations de planification communes à ces trois [fonctionnalités,](network-settings-for-advanced-features.md)voir Paramètres réseau pour les fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server .

Skype Entreprise Server prend en charge les appels Enhanced 9-1-1 (E9-1-1) depuis des clients Skype Entreprise et des appareils Lync Téléphone Edition. Lorsque vous configurez Skype Entreprise Server pour E9-1-1, les appels d’urgence émis depuis Skype Entreprise ou Lync Téléphone Edition incluent des informations d’emplacement d’intervention d’urgence (ERL) à partir de la base de données du service d’informations sur l’emplacement. Les ERL se composent d’adresses géographiques (c’est-à-dire, de rue) et d’autres informations qui permettent d’identifier un emplacement plus précis dans les immeubles de bureaux et d’autres installations multi-clients. Lorsqu’un utilisateur passe un appel d’urgence, Skype Entreprise Server route l’audio de l’appel, ainsi que les informations d’emplacement et de rappel, via un serveur de médiation vers un fournisseur de services E9-1-1. Le fournisseur de services E9-1-1 utilise l’adresse géographique de l’appelant pour router l’appel vers le centre d’appels de la sécurité publique (PSAP) qui sert l’emplacement de l’appelant et envoie le long d’une clé de requête de service d’urgence (ESQK) que le centre d’appels de sécurité publique utilise pour rechercher l’ERL de l’appelant.

Skype Entreprise Server prend en charge deux méthodes pour le routage des appels d’urgence vers un fournisseur de services E9-1-1 :

- une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

- une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (PSTN).

Lorsque vous utilisez un fournisseur de services E9-1-1 de trunk SIP, vous ajoutez des ERL à la base de données du service Informations d’emplacement, puis vous validez les emplacements par rapport à un MSAG (Master Street Address Guide) qui est maintenu par le fournisseur de services E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel qui ne dispose pas d’informations d’emplacement ou dont l’emplacement n’a pas été validé par rapport au MSAG, le fournisseur de services E9-1-1 route l’appel vers un centre national/régional de réponse aux appels d’urgence (ECRC), qui est formé avec du personnel spécialement formé qui obtient verbalement l’emplacement de l’appelant, si possible,  et routez manuellement l’appel vers le PSAP approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) PSTN vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement aux téléphones TDM (multiplexage de division de temps) et PBX (auto-service privé IP), qui ont des emplacements fixes, un point de terminaison Skype Entreprise peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Skype Entreprise Server permet de s’assurer que, quel que soit l’endroit où se trouve un appelant, l’appel d’urgence peut être acheminé vers le centre téléphonique de sécurité publique qui dessert l’emplacement de l’appelant. Par exemple, si le bureau principal d’un utilisateur est situé à Redmond, Washington, mais que l’utilisateur passe un appel d’urgence à partir d’un ordinateur d’une filiale de Wichita, àPéraïa, la ligne SIP ou le fournisseur de services E9-1-1 basé sur PSTN routera l’appel vers le centre de sécurité publique de Wichita, et non vers le centre de sécurité publique de Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également des ERL à la base de données du service Informations d’emplacement, mais vous incluez également un numéro ELIN pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

> [!NOTE]
> Skype Entreprise analogiques connectés à un système ne peuvent pas recevoir d’informations d’emplacement du service Informations d’emplacement ou transmettre l’emplacement au fournisseur de services E9-1-1.

 Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options :

- **Option PS-ALI traditionnelle** Si vous disposez de passerelles PSTN locales sur chaque site où les téléphones analogiques sont déployés et que chaque téléphone analogique possède un SDA, vous pouvez mettre en service l’emplacement du périphérique analogique directement avec un fournisseur de services PS-ALI (Private Switch/Automatic Location Identification). Dans ce cas, vous configurez des stratégies de voix Skype Entreprise spécialement conçues et les affectez aux objets contact du périphérique analogique afin que les appels E9-1-1 de ces téléphones sont acheminés directement via la passerelle locale vers le fournisseur PSTN qui traite le site (au lieu de router l’appel vers une ligne SIP du fournisseur de services E9-1-1). Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction PSTN mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.

- Option de fournisseur de **services E9-1-1** Vous pouvez enregistrer les DDI de téléphone analogique et leurs ERL correspondants auprès du fournisseur de services E9-1-1, si cela est pris en charge par le fournisseur de services E9-1-1. Si le fournisseur reçoit un appel de Skype Entreprise Server qui n’inclut pas de données PIDF-LO, le fournisseur peut voir s’il existe une correspondance de base de données sur le numéro DID de l’appelant. À l’aide de l’ERL récupéré à partir de sa base de données, le fournisseur peut automatiquement router l’appel d’urgence vers le centre d’appels de la sécurité publique correct, et le centre d’appels de la sécurité publique reçoit le DID du périphérique analogique et un enregistrement ESQK qui permet au répartiteur de rechercher l’emplacement de l’appelant.

Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.

Du point Skype Entreprise Server, le processus E9-1-1 peut être séparé en deux étapes :

- Étape 1 : acquisition d’un emplacement

- Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options possibles, voir [Définir les éléments](network-location.md)réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server .

## <a name="acquiring-a-location"></a>Acquisition d’un emplacement

Dans un déploiement Skype Entreprise Server E9-1-1, chaque client Skype Entreprise ou Lync Téléphone Edition connecté en interne acquiert activement son propre emplacement. Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau qu’il connaît elle-même dans une demande d’emplacement au service Informations d’emplacement, qui est un service web qui est dopé par une base de données SQL Server répliquée. Chaque pool de sites central dispose d’un service Informations sur l’emplacement, qui utilise les informations réseau pour interroger ses enregistrements pour obtenir un emplacement correspondant. S’il existe une correspondance, le service Informations d’emplacement renvoie un emplacement au client. Dans le cas inverse, le système peut demander à l’utilisateur d’entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML au standard IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le client Skype Entreprise inclut les données PIDF-LO dans le cadre d’un appel d’urgence, et ces données sont utilisées par le fournisseur de services E9-1-1 pour déterminer le centre d’appels de la sécurité publique approprié et router l’appel vers ce centre psap, ainsi que le bon ESQK, ce qui permet au répartiteur psap d’obtenir l’emplacement de l’appelant.

Le diagramme suivant montre comment un client Skype Entreprise acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC du client tiers) :

![Comment le client acquiert un diagramme d’emplacement.](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Pour qu’un client acquière un emplacement, les étapes suivantes doivent être effectuées :

1. L’administrateur remplit la base de données du service Informations sur l’emplacement avec le réseau fil de câblage (tableaux qui mappent différents types d’adresses réseau à des emplacements d’intervention d’urgence correspondants).

2. Si vous utilisez un fournisseur de services E9-1-1 de jonction SIP, l’administrateur valide les portions d’adresses géographiques des emplacements d’intervention d’urgence à partir d’une base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de services E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les numéros d’identification d’emplacement d’urgence vers la base de données ALI (Automatic Location Identification).

3. Lors de l’inscription ou chaque fois qu’une modification réseau se produit, un client connecté en interne envoie une demande d’emplacement contenant les adresses réseau découvertes du client au service Informations d’emplacement.

4. Le service Informations sur l’emplacement interroge ses enregistrements publiés pour obtenir un emplacement et, si une correspondance est trouvée, renvoie l’ERL au client au format PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routage des appels E9-1-1 à l’aide d’une trunk SIP

L’utilisation d’une jonction SIP pour se connecter à un fournisseur de services E9-1-1 certifié est une façon de déployer le système E9-1-1. Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un fournisseur de services E9-1-1 PSTN, voir [Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway).

Le diagramme suivant montre comment un appel d’urgence est acheminé de Skype Entreprise Server vers le centre téléphonique de sécurité publique (PUBLIC Safety Answering Point) lorsque vous utilisez une ligne SIP et un fournisseur de services E9-1-1 qualifié.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage des appels d’urgence de Lync Server vers psap.](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Lorsqu’un appel d’urgence est passé à partir d’un client Skype Entreprise Server compatible :

1. Une INVITE SIP qui contient l’emplacement, le numéro de rappel de l’appelant, l’URL de notification (facultative) et le numéro de rappel de conférence est acheminée vers Skype Entreprise Server.

2. Skype Entreprise Server correspond au numéro d’urgence et approvisionnement de l’appel (en fonction de la valeur d’utilisation **PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation, et à partir de là, sur une ligne SIP vers le fournisseur de services E9-1-1.

3. Le fournisseur de services E9-1-1 transfère l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclus un emplacement d’intervention d’urgence avec l’appel d’urgence, le fournisseur achemine automatiquement l’appel vers le centre d’appels de la sécurité publique approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre d’intervention en cas d’appels d’urgence (ECRC) vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant d’acheminer l’appel d’urgence au centre d’appels de la sécurité publique.

4. Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation sont envoyés Skype Entreprise message instantané de notification d’urgence. Ce message apparaît toujours sur l’écran des agents de sécurité et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel de sécurité de répondre rapidement à l’appelant d’urgence à l’aide d’un message instantané ou d’une voix.

5. Si vous avez configuré la stratégie d’emplacement pour la conférence et que celle-ci est prise en charge par le fournisseur de services E9-1-1 PSTN, un service de sécurité interne est mis en conférence dans l’appel avec un son unidirectionnel ou bidirectionnel.

6. Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro de rappel pour contacter l’appelant directement.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routage des appels E9-1-1 à l’aide d’une passerelle ELIN

Certains partenaires dans le programme d’interopérabilité ouverte des communications unifiées fournissent des passerelles ELIN (Emergency Location Identification Number) certifiées, qui peuvent servir d’alternative à une connexion de jonction SIP à un fournisseur de services E9-1-1 certifié. Les passerelles ELIN prennent en charge la connectivité RNIS ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basé sur le réseau téléphonique commuté (RTC). Pour plus d’informations sur les partenaires qui fournissent des passerelles ELIN et des liens vers leur documentation, voir Infrastructure qualifiée pour [Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) et Infrastructure téléphonique pour [Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md).

Tout comme les connexions de liaison SIP aux fournisseurs de services E9-1-1, les passerelles ELIN permettent également de router un appel d’urgence vers le centre téléphonique de sécurité publique (PUBLIC SAFETY Answering Point) le plus approprié de l’appelant, mais ces passerelles utilisent un ELIN comme identificateur d’emplacement. Vous définissez des ELIN pour chaque emplacement d’intervention d’urgence (ERL) de votre organisation (pour plus d’informations, voir Gérer les emplacements des [passerelles ELIN](elin-gateways.md)dans Skype Entreprise Server ).

Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure Skype Entreprise Server E9-1-1 que celle que vous utiliseriez pour une connexion de trunk SIP. Autrement dit, la base de données du service Informations sur l’emplacement fournit l’emplacement au client Skype Entreprise, et la stratégie d’emplacement active la fonctionnalité et définit le routage. Avec une passerelle ELIN, toutefois, vous devez ajouter les numéros d’identification de l’emplacement à la base de données du service Informations d’emplacement et que votre opérateur PSTN les télécharge vers la base de données ALI (Automatic Location Identification).

Lorsqu’Skype Entreprise client obtient son emplacement à partir du service Informations d’emplacement, l’emplacement inclut le ELIN. Lors d’un appel d’urgence, l’ELIN est inclus dans l’emplacement envoyé à la passerelle ELIN. La passerelle ELIN identifie l’appel comme un appel d’urgence et échange le numéro de l’appelant avec le numéro ELIN. La passerelle ELIN route ensuite l’appel vers le PSTN avec le numéro ELIN comme numéro d’appel. Le fournisseur PSTN E9-1-1 recherche le ELIN dans la base de données ALI, qui est une base de données complémentaire de la base de données MSAG (Master Street Address Guide). Le PSTN envoie ensuite l’appel au psap le plus approprié en fonction de la recherche ALI, et le PSAP envoie les premiers répondeurs à l’emplacement de l’appelant en fonction de la recherche ALI. Le numéro appelant est mis en cache sur la passerelle ELIN pendant une durée prédéfinie pour les rappels. Au cours d’un rappel, le centre d’appels de la PSAP atteint la passerelle ELIN, qui remplace le numéro ELIN par le numéro DID (Direct Inward Dialing) de l’appelant.

Les passerelles ELIN prennent en charge les appels d’urgence provenant uniquement du réseau de votre organisation. Elles ne prennent pas en charge ceux passés en dehors de votre réseau.

> [!NOTE]
> Pour plus d’informations sur l’utilisation d’une connexion de jonction SIP pour les appels d’urgence, voir [Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk).

Le diagramme suivant illustre la façon dont un appel d’urgence est acheminé de Skype Entreprise Server vers le centre d’appels de la Psap lorsque vous utilisez une passerelle ELIN.

**Routage des appels E9-1-1 vers une passerelle ELIN**

![Montre comment un appel aux services d’urgence passe par le serveur de médiation, puis vers le fournisseur de services d’urgence. Après cela, un message instantané peut éventuellement être envoyé à la sécurité sur site et/ou un appel à l’appelant d’origine.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Une INVITE SIP contenant l’emplacement, le numéro de rappel de l’appelant, l’URL de notification (facultative) et le numéro de rappel de conférence est acheminée vers Skype Entreprise Server.

2. Skype Entreprise Server correspond au numéro d’urgence, puis approvisionnement de l’appel (en fonction de la valeur d’utilisation **PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation, puis à partir de là vers une passerelle ELIN.

3. La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4. Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI.

5. Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation sont envoyés Skype Entreprise message instantané de notification d’urgence. Ce message apparaît toujours sur l’écran des agents de sécurité et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel de sécurité de répondre rapidement à l’appelant d’urgence à l’aide d’un message instantané ou d’une voix.

6. Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro d’identification de l’emplacement en cas d’urgence pour contacter l’appelant directement. La passerelle ELIN remplace le numéro d’identification de l’emplacement en cas d’urgence par le numéro SDA (sélection directe à l’arrivée).