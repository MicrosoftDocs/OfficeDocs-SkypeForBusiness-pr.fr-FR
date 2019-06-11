---
title: 'Lync Server 2013 : Vue d’ensemble du service E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Vue d’ensemble du service E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-29_

Microsoft Lync Server 2013 prend en charge les appels Enhanced 9-1-1 (E9-1-1) à partir des clients Lync et des appareils Lync Phone Edition. Lorsque vous configurez Lync Server pour E9-1-1, les appels d’urgence placés dans Lync 2013 ou Lync Phone Edition incluent des informations de lieu de réponse d’urgence de la base de données de service des informations d’emplacement. ERLs se compose d’adresses postales et d’autres informations qui vous permettent d’identifier un emplacement plus précis dans les bâtiments d’Office et dans d’autres installations mutualisées. Lorsqu’un utilisateur effectue un appel d’urgence, Lync Server route le son de l’appel, ainsi que les informations d’emplacement et de rappel, par le biais d’un serveur de médiation vers un fournisseur de services E9-1-1. Le prestataire de services E9-1-1 utilise l’adresse postale de l’appelant pour acheminer l’appel vers le point d’accès de la sécurité publique (PSAPI) qui répond à l’emplacement de l’appelant, et il envoie une clé de requête de service d’urgence (ESQK), utilisée par le PSAPI pour rechercher le son de l’appelant.

Lync Server prend en charge deux méthodes de routage des appels d’urgence vers un fournisseur de services E9-1-1:

  - une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;

  - une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (RTC).

Lorsque vous utilisez un fournisseur de services SIP Trunk E9-1-1, vous ajoutez ERLs à la base de données de service d’information d’emplacement, puis vous validez les emplacements par rapport au Guide d’adresses du maître d’adresses (MSAG) qui est géré par le fournisseur de service E9-1-1. Si un fournisseur de services E9-1-1 reçoit un appel sans informations d’emplacement ou avec un emplacement non validé par rapport à la base de données MSAG, il achemine l’appel vers un centre national/régional d’intervention en cas d’appels d’urgence (ECRC), où un personnel spécialement formé essaie d’obtenir par téléphone l’emplacement précis de l’appelant, puis achemine manuellement l’appel vers le centre PSAP approprié. (Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) RTC vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)

Contrairement aux téléphones PBX (Time Division Multiplexing) et aux téléphones PBX (PBX) sur IP, qui ont des emplacements fixes, un point de terminaison Lync peut être très mobile. Lorsque vous déployez la fonctionnalité E9-1-1, Lync Server vous permet de vérifier qu’il n’y a aucune information sur l’appelant, l’appel d’urgence peut être acheminé vers le PSAPI qui dessert l’emplacement de l’appelant. Par exemple, si un utilisateur travaille habituellement au siège social de sa société situé à Redmond (Washington), mais qu’il effectue un appel d’urgence à partir d’un ordinateur installé dans la succursale de Wichita (Kansas), le fournisseur de services E9-1-1 de réseau RTC ou de jonction SIP achemine l’appel vers le centre téléphonique de sécurité publique de Wichita et non celui de Redmond.

Lorsque vous utilisez une passerelle ELIN, vous ajoutez également ERLs à la base de données de service des informations d’emplacement, mais vous incluez également un numéro ELIN pour chaque emplacement. Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence. Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.

<div>


> [!NOTE]  
> Les appareils analogiques connectés à Lync ne peuvent pas recevoir les informations d’emplacement du service d’information d’emplacement ou transmettre l’emplacement au fournisseur de services E9-1-1. Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options : 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Option&nbsp;PS&nbsp;-Ali classique si vous avez des passerelles RTC locales sur chaque site sur lequel sont déployés les téléphones analogiques et chaque téléphone analogique, vous pouvez configurer la localisation de l’appareil analogique directement avec un commutateur privé/automatique. Fournisseur de services PS-ALI (identification d’emplacement). Dans ce cas, vous devez configurer des stratégies de voix Lync spécialement conçues et les affecter aux objets de contact de l’appareil analogique de sorte que les appels E9-1-1 à partir de ces téléphones soient acheminés directement par l’intermédiaire de la passerelle locale vers le fournisseur RTC qui service le site (au lieu de router le appel vers un E9-1-1 fournisseur de services SIP Trunk). Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction RTC mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP. Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Option&nbsp;de&nbsp;prestataire de services E9-1-1 vous pouvez inscrire le téléphone DIDS et son ERLs correspondant auprès du prestataire de services E9-1-1, s’il est pris en charge par le fournisseur de service E9-1-1. Si le fournisseur reçoit un appel de Lync Server qui n’inclut pas de données PIDF-Low, le fournisseur peut voir s’il existe une correspondance de base de données sur le numéro DID de la personne qui appelle. En utilisant la propriété ERL Récupérée de sa base de données, le fournisseur peut automatiquement diriger l’appel d’urgence vers le champ PSAPI approprié, et le champ PSAPI reçoit le message de la part de l’appareil analogique et un enregistrement ESQK qui permet au répartiteur de Rechercher l’emplacement de l’appelant.</P></LI></UL>Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.</div>

Du point de vue du serveur Lync, le processus E9-1-1 peut être divisé en deux étapes:

  - Étape 1 : acquisition d’un emplacement

  - Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1

Cette section décrit le déroulement de ces deux étapes.

Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements. Pour plus d’informations sur les options disponibles, voir [définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Acquisition d’un emplacement dans Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

