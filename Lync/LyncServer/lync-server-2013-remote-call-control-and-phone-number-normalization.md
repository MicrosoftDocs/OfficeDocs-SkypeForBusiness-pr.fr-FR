---
title: 'Lync Server 2013 : Contrôle d’appel distant et normalisation des numéros de téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-22_

Les clients Lync téléchargent les règles de normalisation des numéros de téléphone dans le cadre du téléchargement de fichiers du service de carnet d’adresses (ABS). Dans les scénarios de contrôle d’appel distant, les règles de normalisation des numéros de téléphone du service de carnet d’adresses sont appliquées aux appels de contrôles d’appel distants entrants et sortants. Pour les appels entrants vers un utilisateur prenant en charge le contrôle d’appel distant, le numéro de téléphone de l’appelant est d’abord normalisé au format E. 164 par la passerelle SIP/CSTA ou le protocole PBX (Private Branch Exchange). Lorsque Lync Server 2013 reçoit l’appel de la passerelle, il effectue la recherche de numéro inverse (RNL) sur le numéro de téléphone de l’appelant par rapport au numéro normalisé de la liste de contacts Microsoft Office Outlook du destinataire ou de la liste d’adresses globale qui est stockée dans Service de carnet d’adresses. Si la recherche par numéro inverse trouve une correspondance, l’appelant est identifié par son nom dans la notification de l’appel entrant.

Pour les appels sortants de contrôle d’appel distant, Lync applique les règles de normalisation du numéro de téléphone du service de carnet d’adresses au numéro composé avant de router l’appel vers la passerelle SIP/CSTA.

Pour plus d’informations sur la création de règles de normalisation des numéros de téléphone pour le contrôle d’appel distant, voir [plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migration des règles de normalisation des numéros de téléphone

Si vous migrez des utilisateurs déjà activés pour le contrôle d’appel distant, reportez-vous aux rubriques suivantes dans la documentation relative à la migration:

  - Pour Lync Server 2010, voir [migrer le carnet d’adresses](migrate-address-book.md) dans la documentation relative à la migration.

  - Pour Communications Server 2007 R2, voir [migrer le carnet d’adresses](migrate-address-book_1.md) dans la documentation de migration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

