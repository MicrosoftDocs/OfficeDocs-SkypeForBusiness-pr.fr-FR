---
title: 'Lync Server 2013 : vue d’ensemble de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345116ebdd353fccf85f05a4a3f3ffc82fab6de2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Vue d’ensemble de E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Microsoft Lync Server 2013 prend en charge l’appel Enhanced 9-1-1 (E9-1-1) à partir des clients Lync et des appareils Lync Phone Edition. Lorsque vous configurez Lync Server pour E9-1-1, les appels d’urgence passés à partir de Lync 2013 ou Lync Phone Edition incluent des informations de l’emplacement de réponse d’urgence (ERL) de la base de données du service informations d’emplacement. ERL se composent d’adresses civiques (c’est-à-dire des rues) et d’autres informations qui permettent d’identifier un emplacement plus précis dans les immeubles de bureau et les autres installations mutualisées. Lorsqu’un utilisateur passe un appel d’urgence, Lync Server achemine l’audio de l’appel, ainsi que les informations d’emplacement et de rappel, via un serveur de médiation vers un fournisseur de services E9-1-1. Le fournisseur de services E9-1-1 utilise l’adresse postale de l’appelant pour acheminer l’appel vers le point de contrôle de sécurité public (PSAPI) qui dessert l’emplacement de l’appelant, et envoie le long d’une clé de requête de service d’urgence (ESQK) que le PSAPI utilise pour rechercher le ERL de l’appelant.

Lync Server prend en charge deux méthodes de routage des appels d’urgence vers un fournisseur de services E9-1-1 :

  - une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

  - une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (PSTN).

Lorsque vous utilisez un fournisseur de services E9-1-1 de jonction SIP, vous ajoutez ERL à la base de données du service informations d’emplacement, puis vous validez les emplacements par rapport à un guide d’adresses de rue (MSAG) géré par le fournisseur de services E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel sans informations d’emplacement ou avec un emplacement non validé par rapport à la base de données MSAG, il achemine l’appel vers un centre national/régional d’intervention en cas d’appels d’urgence (ECRC), où un personnel spécialement formé essaie d’obtenir par téléphone l’emplacement précis de l’appelant, puis achemine manuellement l’appel vers le centre PSAP approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) PSTN vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement aux téléphones à multiplexage temporel (TDM) et PBX (Private Branch Exchange) basés sur IP, qui ont des emplacements fixes, un point de terminaison Lync peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Lync Server vous permet de vous assurer que, quel que soit l’endroit où se trouve un appelant, l’appel d’urgence peut être acheminé vers le PSAPI qui dessert l’emplacement de l’appelant. Par exemple, si un utilisateur travaille habituellement au siège social de sa société situé à Redmond (Washington), mais qu’il effectue un appel d’urgence à partir d’un ordinateur installé dans la succursale de Wichita (Kansas), le fournisseur de services E9-1-1 de réseau PSTN ou de jonction SIP achemine l’appel vers le centre téléphonique de sécurité publique de Wichita et non celui de Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également ERL à la base de données du service informations d’emplacement, mais vous incluez également un numéro de ELIN pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

<div>


> [!NOTE]  
> Les périphériques analogiques connectés à Lync ne peuvent pas recevoir les informations d’emplacement du service d’informations d’emplacement ou transmettre l’emplacement au fournisseur de services E9-1-1. Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options : 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Option&nbsp;PS&nbsp;-Ali traditionnelle si vous avez des passerelles RTC locales sur chaque site où les téléphones analogiques sont déployés et que chaque téléphone analogique a fait, vous pouvez configurer l’emplacement du périphérique analogique directement avec un fournisseur de services PS-Ali (Private Switch/Automatic location identification). Dans ce cas, vous configurez des stratégies de voix Lync spécialement définies et les affectez aux objets contact du périphérique analogique afin que les appels E9-1-1 de ces téléphones soient directement acheminés, via la passerelle locale, vers le fournisseur PSTN qui dessert le site (au lieu d’acheminer les appels vers une jonction SIP de fournisseur de services E9-1-1). Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction PSTN mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Option&nbsp;du&nbsp;fournisseur de services E9-1-1 vous pouvez enregistrer le numéro de téléphone DIDS et les ERL correspondants auprès du fournisseur de services E9-1-1, s’il est pris en charge par le fournisseur de services E9-1-1. Si le fournisseur reçoit un appel de Lync Server qui n’inclut pas de données PIDF-LO, le fournisseur peut voir s’il existe une correspondance de base de données sur le numéro DID de l’appelant. En utilisant le ERL extrait à partir de sa base de données, le fournisseur peut acheminer automatiquement l’appel d’urgence vers le PSAPI correct, et le PSAPI reçoit le DID du périphérique analogique et un enregistrement ESQK qui permet au répartiteur de Rechercher l’emplacement de l’appelant.</P></LI></UL>Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.</div>

Du point de vue de Lync Server, le processus E9-1-1 peut être séparé en deux étapes :

  - Étape 1 : acquisition d’un emplacement

  - Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options possibles, reportez-vous à [la rubrique définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Acquisition d’un emplacement dans Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routage des appels E9-1-1 à l’aide d’une jonction SIP dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Routage des appels E9-1-1 à l’aide d’une passerelle ELIN dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

