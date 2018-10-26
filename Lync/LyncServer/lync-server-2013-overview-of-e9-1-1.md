---
title: 'Lync Server 2013 : Vue d’ensemble du service E9-1-1'
TOCTitle: Vue d’ensemble du service E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412936(v=OCS.15)
ms:contentKeyID: 49298712
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du service E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Microsoft Lync Server 2013 prend en charge les appels Enhanced 9-1-1 (E9-1-1) provenant de clients Lync et de périphériques Lync Phone Edition. Lorsque vous configurez Lync Server pour E9-1-1, les appels d’urgence passés de Lync 2013 ou de Lync Phone Edition comportent des informations d’emplacement d’intervention d’urgence (Emergency Response Location ou ERL) extraites de la base de données du service d’informations sur l’emplacement. Les ERL sont composés d’adresses géographiques et de toute autre information permettant d’identifier plus rapidement et précisément un emplacement dans des immeubles de bureaux et autres bâtiments multilocatifs. Lorsqu’un utilisateur passe un appel d’urgence, Lync Server utilise un serveur de médiation pour acheminer l’appel audio, et ses informations d’emplacement et de rappel associées, vers un fournisseur de services E9-1-1. Le fournisseur de services E9-1-1 se base sur l’adresse géographique de l’appelant pour acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) qui dessert l’emplacement de l’appelant. Il envoie également une clé de requête de service d’urgence (Emergency Service Query Key ou ESQK) qui permet au centre PSAP de rechercher l’ERL de l’appelant.

Lync Server prend en charge deux méthodes de routage des appels d’urgence vers un fournisseur de services E9-1-1 :

  - une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

  - une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (RTC).

Lorsque vous faites appel à un fournisseur de services E9-1-1 de jonction SIP, vous ajoutez des ERL à la base de données du service d’informations sur l’emplacement, puis vous validez les emplacements par rapport à la base de données MSAG (Master Street Address Guide) gérée par le fournisseur de services E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel sans informations d’emplacement ou avec un emplacement non validé par rapport à la base de données MSAG, il achemine l’appel vers un centre national/régional d’intervention en cas d’appels d’urgence (ECRC), où un personnel spécialement formé essaie d’obtenir par téléphone l’emplacement précis de l’appelant, puis achemine manuellement l’appel vers le centre PSAP approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) RTC vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement aux téléphones à multiplexage temporel (TDM) et IP-PBX (Internet Protocol Private Branch Exchange), qui ont des emplacements fixes, un point de terminaison Lync peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Lync Server contribue à garantir, indépendamment de l’emplacement d’un appelant, l’acheminement de l’appel d’urgence vers le centre téléphonique de sécurité publique qui dessert l’emplacement de l’appelant. Par exemple, si un utilisateur travaille habituellement au siège social de sa société situé à Redmond (Washington), mais qu’il effectue un appel d’urgence à partir d’un ordinateur installé dans la succursale de Wichita (Kansas), le fournisseur de services E9-1-1 de réseau RTC ou de jonction SIP achemine l’appel vers le centre téléphonique de sécurité publique de Wichita et non celui de Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également des emplacements ERL à la base de données du service d’informations sur l’emplacement, mais vous devez aussi inclure un numéro d’identification de l’emplacement en cas d’urgence (numéro ELIN) pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

> [!NOTE]  
> Les périphériques analogiques connectés à Lync ne peuvent pas recevoir d’informations d’emplacement du service d’informations sur l’emplacement ni transmettre l’emplacement au fournisseur de services E9-1-1. Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options :
> <ul>
> <li><p><strong>Option PS-ALI classique</strong>   Si vous avez des passerelles RTC locales sur chaque site où des téléphones analogiques sont déployés et que chaque téléphone analogique dispose d’un SDA, vous pouvez configurer l’emplacement du périphérique analogique directement avec un fournisseur de services PS-ALI (Private Switch/Automatic Location Identification). Dans ce cas, vous configurez des stratégies de voix Lync spécialement définies et les affectez aux objets contact du périphérique analogique afin que les appels E9-1-1 de ces téléphones soient directement acheminés, via la passerelle locale, vers le fournisseur RTC qui dessert le site (au lieu d’acheminer les appels vers une jonction SIP de fournisseur de services E9-1-1). Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction RTC mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.</p></li>
> <li><p><strong>Option de fournisseur de services E9-1-1</strong>   Vous pouvez inscrire le numéro SDA des téléphones analogiques et leurs ERL correspondants auprès du fournisseur de services E9-1-1, si celui-ci prend en charge cette option. Si le fournisseur reçoit un appel de Lync Server qui ne comprend pas les données PIDF-LO, il peut déterminer si une correspondance de base de données existe pour le numéro SDA de l’appelant. En utilisant l’URL extrait de la base de données, le fournisseur peut automatiquement acheminer l’appel d’urgence vers le centre PSAP approprié. Le centre reçoit le numéro SDA du périphérique analogique ainsi qu’une clé ESQK qui permet au répartiteur de rechercher l’appelant.</p></li></ul>
> Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.


De la perspective de Lync Server, le processus E9-1-1 peut être séparé en deux étapes :

  - Étape 1 : acquisition d’un emplacement

  - Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options possibles, reportez-vous à [Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

## Dans cette section

  - [Acquisition d’un emplacement dans Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

