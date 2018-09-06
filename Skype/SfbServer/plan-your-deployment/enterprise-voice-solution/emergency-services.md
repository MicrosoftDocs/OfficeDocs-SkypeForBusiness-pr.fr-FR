---
title: Planifier les services d’urgence dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: En savoir plus sur les services de Enhanced 9-1-1 (E9-1-1) dans Skype pour Business Server Enterprise Voice, y compris l’acquisition de l’emplacement et le routage des appels.
ms.openlocfilehash: 1e71b232a9c13a223192afd76066b6afc72721d4
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245327"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planifier les services d’urgence dans Skype pour Business Server

En savoir plus sur les services de Enhanced 9-1-1 (E9-1-1) dans Skype pour Business Server Enterprise Voice, y compris l’acquisition de l’emplacement et le routage des appels.

Skype pour Business Server prend en charge les services Enhanced 9-1-1 (E9-1-1) au sein des États-Unis dans le cadre d’un déploiement d’Enterprise Voice. E9-1-1 est une fonctionnalité de réponse aux appels d’urgence qui associe un appel au 911 à un emplacement de réponse d’urgence (ERL, Emergency Response Location) qui est constitué d’une adresse (c’est-à-dire, une rue) et d’informations d’emplacement spécifiques, telles qu’un numéro d’étage, pour les appels provenant d’immeubles de bureaux et d’habitation. À l’aide de l’emplacement de réponse d’urgence fourni, un centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) peut immédiatement transférer les appels de détresse aux services d’urgence appropriés sans risquer de leur fournir de mauvaises informations.

> [!NOTE]
> Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Pour plus d’informations, voir [planifier plusieurs numéros d’urgence dans Skype pour Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype pour Business Server comporte trois fonctionnalités voix entreprise : appeler le contrôle d’admission des appels, les services d’urgence (E9-1-1) et le contournement de média. Pour une vue d’ensemble de la planification des informations qui sont communes aux trois de ces fonctionnalités, voir [paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server](network-settings-for-advanced-features.md).

Skype pour Business Server prend en charge Enhanced 9-1-1 (E9-1-1) l’appel de Skype pour les clients d’entreprise et appareils Lync Phone Edition. Lorsque vous configurez Skype pour Business Server pour E9-1-1, en cas d’urgence les appels émis à partir de Skype pour les entreprises ou Lync Phone Edition contiennent des informations d’emplacement de réponse d’urgence (ERL) à partir de la base de données du service informations d’emplacement. Erl se composent de civiles (autrement dit, rue) adresses et autres informations qui vous aide à identifier un emplacement plus précis de bâtiments et autres fonctionnalités d’une architecture mutualisées. Lorsqu’un utilisateur effectue un appel d’urgence, Skype pour Business Server achemine l’appel audio, ainsi que les informations d’emplacement et de rappel, via un serveur de médiation pour un fournisseur de services E9-1-1. Le fournisseur de services E9-1-1 utilise l’adresse postale de l’appelant pour acheminer l’appel pour le Public Safety Answering Point (PSAP) qui sert d’emplacement de l’appelant et envoie le long d’un Emergency Service requête clé (ESQK) le PSAP utilise pour rechercher ERL l’appelant.

Skype pour Business Server prend en charge deux méthodes pour acheminer les appels d’urgence vers un fournisseur de services E9-1-1 :

- une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

- une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (RTC).

Lorsque vous utilisez un fournisseur de service de E9-1-1 de jonction SIP, vous ajoutez Erl à la base de données du service informations d’emplacement, puis validez les emplacements par rapport à une forme de base rue adresse Guide (MSAG) est assurée par le fournisseur de services E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel qui ne dispose des informations d’emplacement ou un emplacement qui n’a pas été validé par rapport à la MSAG, le fournisseur de services E9-1-1 achemine l’appel d’urgence appel Response Center (ECRC), qui est un nationales/régionales service de personnel formé spécialement oralement obtenir emplacement de l’appelant, si possible et manuellement acheminer l’appel vers le PSAP approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) RTC vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement à temps multiplexage (TDM) et les téléphones PBX (exchange) autocommutateur privé IP-based, qui ont des endroits fixes, un Skype pour le point de terminaison Business peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Skype pour Business Server permet de garantir que, quel que soit l’où se trouve l’appelant, l’appel d’urgence peut être acheminé vers le PSAP qui sert d’emplacement de l’appelant. Par exemple, si office principal d’un utilisateur se trouve dans Redmond, Washington, mais que l’utilisateur passe un appel d’urgence depuis un ordinateur dans une filiale dans Wichita, Kansas, la jonction SIP ou fournisseur de services RTC E9-1-1 achemine l’appel vers le PSAP dans Wichita , pas vers le PSAP à Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également Erl à la base de données du service informations d’emplacement, mais vous incluez également un numéro ELIN pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

> [!NOTE]
> Skype pour les périphériques analogiques connectés d’entreprise ne peut pas recevoir les informations d’emplacement à partir du service d’informations sur l’emplacement ou transmettre l’emplacement pour le fournisseur de services E9-1-1.

 Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options :

- **PS-ALI traditionnel option** Si vous avez des passerelles PSTN locales sur chaque site où les téléphones analogiques sont déployés et chaque téléphone analogique a un DID, vous pouvez configurer l’emplacement du périphérique analogique directement avec un fournisseur de services de commutateur/automatique emplacement d’Identification (PS-ALI). Dans ce cas, vous configurez Skype de spécialement pour les stratégies de voix entreprise et les attribuer au périphérique analogique des objets contact pour pouvoir acheminer les appels E9-1-1 à partir de ces téléphones directement par le biais de la passerelle locale pour le fournisseur PSTN que les services du site (au lieu de cela d’acheminer l’appel vers un fournisseur de services E9-1-1 liaison SIP). Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction RTC mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.

- **Option de fournisseur de services E9-1-1** Vous pouvez inscrire les DIDs téléphonique analogique et leurs Erl correspondante avec le fournisseur de services E9-1-1, si cela est pris en charge par le fournisseur de services E9-1-1. Si le fournisseur reçoit un appel Skype pour Business Server qui n’inclut pas les données format PIDF-LO, le fournisseur peut voir s’il existe une correspondance de base de données sur le nombre d’arrivée de l’appelant. À l’aide de l’ERL automatiquement récupérée à partir de sa base de données, le fournisseur peut acheminer l’appel vers le PSAP correct et le PSAP reçoit l’arrivée du périphérique analogique et un enregistrement ESQK qui permet le répartiteur rechercher l’emplacement de l’appelant.

Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.

À partir d’un Skype pour perspective Business Server, le processus E9-1-1 peut être séparé en deux étapes :

- Étape 1 : acquisition d’un emplacement

- Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options possibles, voir [définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype pour Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Acquisition d’un emplacement

Dans un Skype pour le déploiement de serveur Business E9-1-1, chaque Skype connecté en interne pour Lync Phone Edition ou l’entreprise client acquiert activement son propre emplacement. Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau qu’il connaît lui-même il dans une demande d’emplacement pour le service informations d’emplacement, qui est un service web bénéficient d’une base de données SQL Server répliquée. Chaque site central du pool est un service d’informations sur l’emplacement, qui utilise les informations du réseau pour interroger ses enregistrements d’un emplacement correspondant. S’il existe une correspondance, le service informations d’emplacement renvoie un emplacement pour le client. Dans le cas inverse, l’utilisateur peut être invité à entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement). Les données d’emplacement sont retransmises au client dans un format XML normalisé IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).

Le Skype pour client d’entreprise inclut les données de format PIDF-LO dans le cadre d’un appel d’urgence, et ces données sont utilisées par le fournisseur de services E9-1-1 pour déterminer le PSAP approprié et acheminer l’appel vers ce PSAP ainsi que le ESQK correct, qui permet le répartiteur PSAP obtenir l’emplacement de l’appelant.

Le diagramme suivant illustre comment un Skype pour Business client acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC du client tiers) :

![Diagramme : comment le client acquiert un emplacement](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Pour qu’un client acquière un emplacement, les étapes suivantes doivent se produire :

1. L’administrateur renseigne la base de données du service informations d’emplacement avec le schéma de câblage réseau (tableaux qui mappent différents types d’adresses réseau aux emplacements d’intervention d’urgence (Erl) correspondante).

2. Si vous utilisez un fournisseur de service E9-1-1 de jonction SIP, l’administrateur valide les parties d’adresse civile des ERL par rapport à la base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de service E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les ELIN dans la base de données ALI (Automatic Location Identification).

3. Lors de l’inscription ou chaque fois qu’une modification réseau se produit, un client connecté en interne envoie une demande d’emplacement qui contient le client découvertes du adresses réseau pour le service informations d’emplacement.

4. Le service informations d’emplacement interroge ses enregistrements publiés pour un emplacement et, si une correspondance est trouvée, renvoie l’ERL au client au format PIDF-LO format.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routage des appels E9-1-1 avec une jonction SIP

Se connecter à un fournisseur de services E9-1-1 éligible à l’aide d’une jonction SIP vous permet de déployer E9-1-1. Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un réseau téléphonique commuté (PSTN)-E9-1-1 en fonction de fournisseur de services, voir [Routing E9-1-1 Calls à l’aide d’une passerelle ELIN](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Le diagramme suivant illustre comment un appel d’urgence est acheminé de Skype pour Business Server pour le Public Safety Answering Point (PSAP) lorsque vous utilisez une jonction SIP et un fournisseur de services E9-1-1 certifié.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage d’appel d’urgence de Lync Server vers PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Lorsqu’un appel d’urgence est émis à partir d’un compatible Skype pour client Business Server :

1. Une requête SIP INVITE contenant l’emplacement, numéro de rappel de l’appelant et le numéro de rappel de conférence et les URL de Notification (facultatif) est acheminée vers Skype pour Business Server.

2. Skype pour Business Server correspond au numéro d’urgence et achemine l’appel (basé sur la valeur **D’utilisation PSTN** qui est définie dans la stratégie d’emplacement applicable) vers un serveur de médiation et de là, via une jonction SIP pour le fournisseur de services E9-1-1.

3. Le fournisseur de services E9-1-1 route l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclut un emplacement de situation d’urgence (ERL) validé dans l’appel d’urgence, le fournisseur route automatiquement l’appel vers le PSAP approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre de réponse aux appels d’urgence vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant de router l’appel d’urgence vers le PSAP.

4. Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs des responsables de la sécurité de votre organisation sont envoyées une Skype spéciaux pour la messagerie instantanée de notification d’urgence Business. Ce message s’affiche sur écrans des agents de sécurité toujours et contient l’appelant nom, numéro de téléphone, heure et l’emplacement, l’activation du personnel de sécurité répondre rapidement à l’appelant d’urgence à l’aide d’un message instantané ou la voix.

5. Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.

6. Si l’appel se termine prématurément, le PSAP utilise le numéro de rappel pour contacter directement l’appelant.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routage des appels E9-1-1 via une passerelle ELIN

Certains partenaires du programme Unified Communications Open Interoperability fournissent des passerelles compatibles avec les numéros ELIN (Emergency Location Identification Number), ce qui peut servir de solution de remplacement pour une connexion de jonction SIP à un fournisseur de services E9-1-1 qualifié. Les passerelles ELIN prennent en charge la connectivité RNIS (réseau numérique à intégration de services) ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basés sur un réseau téléphonique commuté. Pour plus d’informations sur les partenaires qui proposent les passerelles ELIN et des liens vers leur documentation, voir [Infrastructure qualifié pour Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) et [l’Infrastructure de téléphonie pour Skype pour les entreprises](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Comme les connexions de jonction SIP aux fournisseurs de services E9-1-1, les passerelles ELIN permettent également de routage d’un appel d’urgence à l’appelant plus approprié Public Safety Answering Point (PSAP), mais ces passerelles utilisent une ELIN en tant que l’identificateur d’emplacement. Vous définissez en cas de chaque emplacement de réponse d’urgence (ERL) dans votre organisation (pour plus d’informations, voir [Gérer les emplacements pour les passerelles ELIN dans Skype pour Business Server](elin-gateways.md)).

Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez le même Skype pour infrastructure Business Server E9-1-1 que vous utiliserez pour une connexion de jonction SIP. Autrement dit, la base de données du service informations d’emplacement fournit l’emplacement du Skype pour client d’entreprise et la stratégie d’emplacement Active la fonctionnalité et définit le routage. Avec une passerelle ELIN, toutefois, vous devez ajouter en les cas pour la base de données du service informations d’emplacement et de votre opérateur RTC Téléchargez-les vers la base de données d’Identification d’emplacement automatique (ALI).

Lorsqu’un Skype pour Business client obtient son emplacement à partir du service informations d’emplacement, l’emplacement inclut le ELIN. Pendant un appel d’urgence, le ELIN est inclus avec l’emplacement envoyés vers la passerelle ELIN. La passerelle ELIN identifie l’appel comme un appel d’urgence et remplace le numéro de l’appelant avec le ELIN. La passerelle ELIN achemine ensuite l’appel vers la passerelle PSTN avec la ELIN en tant que le numéro d’appel. Le fournisseur PSTN E9-1-1 recherche l’ELIN dans la base de données ALI, qui est une base de données associées à la base de données Master Street adresse Guide (MSAG). Le réseau RTC envoie ensuite l’appel vers le PSAP plus approprié en fonction de la recherche ALI et le PSAP envoie les premières à l’emplacement de l’appelant en fonction de la recherche ALI. Le numéro d’appel est mis en cache sur la passerelle ELIN pour une période prédéfinie pour des rappels. Au cours d’un rappel, le PSAP atteint la passerelle ELIN, qui remplace le ELIN par le numéro de l’appelant direct inward (SDA).

Les passerelles ELIN prennent en charge les appels d’urgence effectués au sein du réseau de votre organisation. Elles ne prennent pas en charge les appels d’urgence effectués hors de votre réseau.

> [!NOTE]
> Pour plus d’informations sur l’utilisation d’une connexion de jonction SIP pour les appels d’urgence, voir [Routage des appels E9-1-1 à l’aide d’une jonction SIP](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Le diagramme suivant illustre comment un appel d’urgence est acheminé de Skype pour Business Server vers le PSAP lorsque vous utilisez une passerelle ELIN.

**Acheminement d’appels E9-1-1 avec une passerelle ELIN**

![Montre le cheminement d’un appel aux services d’urgence à travers le serveur de médiation jusqu’au fournisseur de services d’urgence. Il peut s’en suivre l’envoi d’un message instantané au service de sécurité sur site et/ou un rappel de l’appelant initial.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Une requête SIP INVITE contenant l’emplacement, numéro de rappel de l’appelant et le numéro de rappel de conférence et les URL de Notification (facultatif) est acheminée vers Skype pour Business Server.

2. Skype pour Business Server correspond au numéro d’urgence, puis achemine l’appel (basé sur la valeur **d’Utilisation PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation et de là, vers une passerelle ELIN.

3. La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4. Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI. 

5. Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs des responsables de la sécurité de votre organisation sont envoyées une Skype spéciaux pour la messagerie instantanée de notification d’urgence Business. Ce message s’affiche sur écrans des agents de sécurité toujours et contient l’appelant nom, numéro de téléphone, heure et l’emplacement, l’activation du personnel de sécurité répondre rapidement à l’appelant d’urgence à l’aide d’un message instantané ou la voix.

6. Si l’appel est interrompu prématurément, le centre PSAP utilise le numéro ELIN pour contacter directement l’appelant. La passerelle ELIN remplace le numéro ELIN par le numéro direct de l’appelant.


