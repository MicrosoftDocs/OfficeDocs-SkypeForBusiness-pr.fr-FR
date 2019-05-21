---
title: Planifier des services d’urgence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: En savoir plus sur les services 9-1-1 (E9-1-1) dans Skype entreprise Server Voice, y compris l’acquisition d’emplacement et le routage des appels.
ms.openlocfilehash: 20d1a258b022b8369f59aaa74a2b95de45f931e2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276893"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planifier des services d’urgence dans Skype entreprise Server

En savoir plus sur les services 9-1-1 (E9-1-1) dans Skype entreprise Server Voice, y compris l’acquisition d’emplacement et le routage des appels.

Skype entreprise Server prend en charge les services Enhanced 9-1-1 (E9-1-1) aux États-Unis dans le cadre d’un déploiement voix entreprise. E9-1-1 est une fonctionnalité de réponse aux appels d’urgence qui associe un appel au 911 à un emplacement de réponse d’urgence (ERL, Emergency Response Location) qui est constitué d’une adresse (c’est-à-dire, une rue) et d’informations d’emplacement spécifiques, telles qu’un numéro d’étage, pour les appels provenant d’immeubles de bureaux et d’habitation. À l’aide de l’emplacement de réponse d’urgence fourni, un centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) peut immédiatement transférer les appels de détresse aux services d’urgence appropriés sans risquer de leur fournir de mauvaises informations.

> [!NOTE]
> Skype entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Pour plus d’informations, reportez-vous à la rubrique [planification de plusieurs numéros d’urgence dans Skype entreprise Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype entreprise Server comporte trois fonctionnalités avancées de voix entreprise: contrôle d’admission des appels, services d’urgence (E9-1-1) et contournement de média. Pour une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, consultez [la rubrique paramètres réseau pour les fonctionnalités avancées d’entreprise voix dans Skype entreprise Server](network-settings-for-advanced-features.md).

Skype entreprise Server prend en charge les appels 9-1-1 de grande qualité (E9-1-1) à partir des clients Skype entreprise et des appareils Lync Phone Edition. Lorsque vous configurez Skype entreprise Server pour E9-1-1, les appels d’urgence placés dans Skype entreprise ou Lync Phone Edition incluent des informations de lieu de réponse d’urgence de la base de données de service des informations d’emplacement. ERLs se compose d’adresses postales et d’autres informations qui vous permettent d’identifier un emplacement plus précis dans les bâtiments d’Office et dans d’autres installations mutualisées. Lorsqu’un utilisateur effectue un appel d’urgence, Skype entreprise Server route le son de l’appel, ainsi que les informations d’emplacement et de rappel, par le biais d’un serveur de médiation vers un fournisseur de services E9-1-1. Le prestataire de services E9-1-1 utilise l’adresse postale de l’appelant pour acheminer l’appel vers le point d’accès de la sécurité publique (PSAPI) qui répond à l’emplacement de l’appelant, et il envoie une clé de requête de service d’urgence (ESQK), utilisée par le PSAPI pour rechercher le son de l’appelant.

Skype entreprise Server prend en charge deux méthodes de routage des appels d’urgence vers un prestataire de services E9-1-1:

- une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

- une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (RTC).

Lorsque vous utilisez un fournisseur de services SIP Trunk E9-1-1, vous ajoutez ERLs à la base de données de service d’information d’emplacement, puis vous validez les emplacements par rapport au Guide d’adresses du maître d’adresses (MSAG) qui est géré par le fournisseur de service E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel qui ne comporte pas d’informations d’emplacement ou dont l’emplacement n’a pas été validé par rapport au MSAG, le fournisseur de service E9-1-1 route l’appel vers un centre de réponse aux appels nationaux/régionaux d’urgence (ECRC), qui est le personnel ayant reçu un personnel formé et ayant verbalement obtenu l’emplacement de l’appelant, le cas échéant, et le diriger manuellement vers le PSAPI approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) RTC vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement aux numéros de téléphone de type TDM (Time Division Multiplexing) et aux téléphones PBX (PBX) sur IP, qui sont des emplacements fixes, un point de terminaison Skype entreprise peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Skype entreprise Server vous permet de vous assurer qu’il n’y a aucun emplacement où se trouve l’appelant, l’appel d’urgence peut être acheminé vers le PSAPI qui dessert l’emplacement de l’appelant. Par exemple, si le siège social d’un utilisateur se trouve à Redmond, à Lyon, mais qu’il passe un appel d’urgence à partir d’un ordinateur d’une succursale dans Wichita, Kansas, le réseau SIP ou PSTN E9-1-1- et non pour le PSAPI de Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également ERLs à la base de données de service des informations d’emplacement, mais vous incluez également un numéro ELIN pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

> [!NOTE]
> Skype pour les entreprises: les appareils analogiques connectés ne peuvent pas recevoir les informations d’emplacement du service d’information d’emplacement ou transmettre l’emplacement au fournisseur de services E9-1-1.

 Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options :

- **Option PS-Ali classique** Si vous avez des passerelles RTC locales sur chaque site sur lequel les téléphones analogiques sont déployés et que chaque téléphone analogique a été déployé, vous pouvez fournir l’emplacement de l’appareil analogique directement auprès d’un fournisseur de services PS-ALI. Dans ce cas, vous devez configurer des stratégies vocales Skype entreprise spécialement conçues et les affecter aux objets de contact d’appareil analogique de sorte que les appels E9-1-1 à partir de ces téléphones soient acheminés directement par le biais de la passerelle locale vers le fournisseur RTC qui service le site (à la place). du routage de l’appel vers un fournisseur de services SIP E9-1-1. Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction RTC mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.

- **Option de fournisseur de services E9-1-1** Vous pouvez enregistrer le téléphone DIDs et son ERLs correspondant auprès du prestataire de services E9-1-1, s’il est pris en charge par le fournisseur de service E9-1-1. Si le fournisseur reçoit un appel de Skype entreprise Server qui n’inclut pas de données PIDF-Low, le fournisseur peut voir s’il existe une correspondance de base de données sur le numéro DID de la personne qui appelle. En utilisant la propriété ERL Récupérée de sa base de données, le fournisseur peut automatiquement diriger l’appel d’urgence vers le champ PSAPI approprié, et le champ PSAPI reçoit le message de la part de l’appareil analogique et un enregistrement ESQK qui permet au répartiteur de Rechercher l’emplacement de l’appelant.

Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.

Dans le perspective du serveur Skype entreprise, le processus E9-1-1 peut être divisé en deux étapes:

- Étape 1 : acquisition d’un emplacement

- Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options disponibles, voir [définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype entreprise Server](network-location.md).

## <a name="acquiring-a-location"></a>Acquisition d’un emplacement

Dans un déploiement Skype entreprise Server E9-1-1, chaque client Skype entreprise ou Lync Phone Edition connecté en interne acquiert activement son emplacement. Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau qu’il connaît lui-même dans une demande d’emplacement du service d’information d’emplacement, qui est un service Web stocké par une base de données SQL Server répliquée. Chacun d’eux dispose d’un service d’information d’emplacement qui utilise les informations réseau pour rechercher un emplacement correspondant dans ses enregistrements. S’il existe une correspondance, le service d’informations d’emplacement renvoie un emplacement au client. Dans le cas inverse, l’utilisateur peut être invité à entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML normalisé IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le client Skype entreprise inclut les données PIDF-Low dans le cadre d’un appel d’urgence, et ces données sont utilisées par le prestataire de services E9-1-1 pour déterminer le PSAPI approprié et acheminer l’appel vers ce PSAPI avec le bon ESQK, qui permet au répartiteur de PSAPI de Obtenez l’emplacement de l’appelant.

Le diagramme suivant montre comment un client Skype entreprise acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC du client tiers):

![Diagramme : comment le client acquiert un emplacement](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Pour qu’un client acquière un emplacement, les étapes suivantes doivent se produire :

1. L’administrateur remplit la base de données de service informations d’emplacement avec le Network Wiremap (tables qui mappent différents types d’adresses réseau aux emplacements de réponse d’urgence correspondants (ERLs)).

2. Si vous utilisez un fournisseur de service E9-1-1 de jonction SIP, l’administrateur valide les parties d’adresse civile des ERL par rapport à la base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de service E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les ELIN dans la base de données ALI (Automatic Location Identification).

3. Lors de l’inscription ou en cas de modification d’un réseau, un client connecté en interne envoie une demande d’emplacement contenant les adresses réseau découvertes du client au service d’informations d’emplacement.

4. Le service d’informations d’emplacement interroge ses enregistrements publiés pour un emplacement et, si une correspondance est trouvée, renvoie la propriété ERL au client en format PIDF-Low.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routage des appels E9-1-1 avec une jonction SIP

Se connecter à un fournisseur de services E9-1-1 éligible à l’aide d’une jonction SIP vous permet de déployer E9-1-1. Pour plus d’informations sur la connexion à un fournisseur de services E9-1-1 basé sur une ligne du réseau téléphonique commuté (RTC) à l’aide d’une passerelle ELIN, reportez-vous à [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Le diagramme suivant illustre la manière dont un appel d’urgence est acheminé de Skype entreprise Server vers le point d’accès public sécurisé (PSAPI) lors de l’utilisation d’un réseau SIP et d’un fournisseur de services E9-1-1 éligible.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage d’appel d’urgence de Lync Server vers PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Lorsqu’un appel d’urgence est passé à partir d’un client Skype entreprise Server compatible:

1. Une invitation SIP qui contient l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultative) et le numéro de rappel de conférence sont routés vers Skype entreprise Server.

2. Skype entreprise Server correspond au numéro d’urgence et route l’appel (en fonction de la valeur d' **utilisation RTC** définie dans la stratégie d’emplacement applicable) sur un serveur de médiation et à partir de là, sur une ligne SIP pour le prestataire de services E9-1-1.

3. Le fournisseur de services E9-1-1 route l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclut un emplacement de situation d’urgence (ERL) validé dans l’appel d’urgence, le fournisseur route automatiquement l’appel vers le PSAP approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre de réponse aux appels d’urgence vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant de router l’appel d’urgence vers le PSAP.

4. Si vous avez configuré la stratégie d’emplacement pour les notifications, une ou plusieurs des responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Skype entreprise. Ce message s’affiche toujours sur le ou les écrans des responsables de la sécurité et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet aux responsables de la sécurité de répondre rapidement à l’appel d’urgence en utilisant un message instantané ou un message vocal.

5. Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.

6. Si l’appel se termine prématurément, le PSAP utilise le numéro de rappel pour contacter directement l’appelant.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routage des appels E9-1-1 via une passerelle ELIN

Certains partenaires du programme Unified Communications Open Interoperability fournissent des passerelles compatibles avec les numéros ELIN (Emergency Location Identification Number), ce qui peut servir de solution de remplacement pour une connexion de jonction SIP à un fournisseur de services E9-1-1 qualifié. Les passerelles ELIN prennent en charge la connectivité RNIS (réseau numérique à intégration de services) ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basés sur un réseau téléphonique commuté. Pour plus d’informations sur les partenaires qui fournissent des passerelles ELIN et des liens vers leurs documents, voir [infrastructure qualifiée pour Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) et [infrastructure de téléphonie pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Comme pour les connexions SIP Trunk à des fournisseurs de services E9-1-1, les passerelles ELIN fournissent également le moyen de diriger un appel d’urgence vers le point d’accès de l’appelant le plus approprié (PSAPI), mais ces passerelles utilisent un ELIN en tant qu’identificateur d’emplacement. Pour plus d’informations, reportez-vous à la section [gestion des emplacements pour les passerelles Elin dans Skype entreprise Server](elin-gateways.md).

Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure Skype entreprise Server E9-1-1 que vous utiliserez pour une connexion SIP Trunk. Autrement dit, la base de données de service des informations d’emplacement spécifie l’emplacement du client Skype entreprise et la stratégie d’emplacement active la fonctionnalité et définit le routage. Toutefois, avec une passerelle ELIN, vous devez ajouter le ELINs à la base de données de service des informations d’emplacement et faire en sorte que votre opérateur PSTN les charge dans la base de données d’identification d’emplacement automatique (ALI).

Lorsqu’un client Skype entreprise obtient son emplacement auprès du service d’information d’emplacement, l’emplacement inclut le ELIN. Au cours d’un appel d’urgence, le ELIN est inclus avec l’emplacement envoyé à la passerelle ELIN. La passerelle ELIN identifie l’appel en tant qu’appel d’urgence et permute le numéro de l’appelant par le ELIN. La passerelle ELIN route ensuite l’appel vers le RTC avec le ELIN comme numéro d’appel. Le fournisseur RTC E9-1-1 recherche ELIN dans la base de données ALI, qui est une base de données associée à la base de données du Guide de l’adresse principale (MSAG). Le RTC envoie alors l’appel vers le site PSAPI le plus approprié en fonction de la recherche ALI, et le champ PSAPI envoie les premiers répondants à l’emplacement de l’appelant en fonction de la recherche ALI. Le numéro d’appel est mis en cache sur la passerelle ELIN pour une durée prédéfinie pour les rappels. Au cours d’un rappel, le PSAPI atteint la passerelle ELIN, qui permute le ELIN pour le numéro de numérotation direct de l’appelant.

Les passerelles ELIN prennent en charge les appels d’urgence effectués au sein du réseau de votre organisation. Elles ne prennent pas en charge les appels d’urgence effectués hors de votre réseau.

> [!NOTE]
> Pour plus d’informations sur l'utilisation d'une connexion de jonction SIP pour les appels d'urgence, reportez-vous à [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Le diagramme suivant montre comment un appel d’urgence est acheminé de Skype entreprise Server vers le PSAPI lorsque vous utilisez une passerelle ELIN.

**Acheminement d’appels E9-1-1 avec une passerelle ELIN**

![Montre le cheminement d’un appel aux services d’urgence à travers le serveur de médiation jusqu’au fournisseur de services d’urgence. Il peut s’en suivre l’envoi d’un message instantané au service de sécurité sur site et/ou un rappel de l’appelant initial.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Une invitation SIP contenant l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultative) et le numéro de rappel de conférence sont routés vers Skype entreprise Server.

2. Skype entreprise Server correspond au numéro d’urgence, puis route l’appel (en fonction de la valeur d' **utilisation RTC** définie dans la stratégie d’emplacement applicable) sur un serveur de médiation et à partir de là vers une passerelle Elin.

3. La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4. Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI. 

5. Si vous avez configuré la stratégie d’emplacement pour les notifications, une ou plusieurs des responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Skype entreprise. Ce message s’affiche toujours sur le ou les écrans des responsables de la sécurité et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet aux responsables de la sécurité de répondre rapidement à l’appel d’urgence en utilisant un message instantané ou un message vocal.

6. Si l’appel est interrompu prématurément, le centre PSAP utilise le numéro ELIN pour contacter directement l’appelant. La passerelle ELIN remplace le numéro ELIN par le numéro direct de l’appelant.


